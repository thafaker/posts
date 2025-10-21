---
title: Ein GHOST 5 Weblog kostenlos cloudhosten
slug: ghost-5-fly-io-kostenlos-free
date_published: 2024-01-16T08:57:57.000Z
date_updated: 2024-01-18T10:04:25.000Z
tags: ghost, fly.io, anleitung, how to, howto, uberspace, mysql 8
excerpt: Wie installiere ich Ghost 5 kostenlos im Production Mode auf fly.io mit MySQL 8 Datenbank. Free Tier. Eine Anleitung.
---

Hallo meine Freunde, diese Anleitung wird nicht ganz so einfach und setzt ein paar Kenntnisse in der Kommandozeile voraus, aber wenn ihr damit ein bisschen firm seid, solltet ihr in 3 Minuten ein cloudbasiertes, kostenloses Ghost 5 Weblog laufen haben.

Ich habe mich mit diesem Thema beschäftigt, weil Uberspace seinen Support für Ghost entfernt hat. Es ist also nicht mehr möglich, Ghost auf dem Uberspace zu betreiben und dementsprechend hat Uberspace auch seine Anleitung für Ghost entfernt.

Das originale Script habe ich von [hier](https://forum.ghost.org/t/tutorial-host-ghost-5-mysql-8-on-fly-io-free-tier/33095), jedoch habe ich es auf unsere *deutschen* Verhältnisse angepasst. Wir gehen folgendermaßen vor, um das kurz *belletristisch* zu beschreiben. Wir nutzen für unser Vorhaben den Cloudhosting-Dienst fly.io. Wir installieren uns das fly commandline-Interface, das läuft unter allem was unixartig ist, also Linux oder BSD oder auch auf dem Mac mit **brew**, so wie bei mir. Dann erstellen wir uns einen Server mit einem Ghost 5.75.3, hosted in Amsterdam, ebenso eine MySQL 8 Datenbank. Das ganze packen wir zusammen, laden es hoch und lassen es laufen. Das wars schon, kurze Zeit später können wir uns im neuen Weblog einloggen. 

Falls ihr den Artikel später lest, schaut am besten bei Docker nach, welche aktuelle Version es von [Ghost als Docker-Image](https://hub.docker.com/_/ghost?ref=blixt-dev) gibt und passt dies im Script an. Zum Zeitpunkt der Entstehung ist die aktuelle Version **Ghost Version 5.75.3**.

Fly.io bietet diesen kostenlosen Tier explizit an, zum ausprobieren, um schnell mal eine Entwicklungsumgebung zu haben und generell im *personal use. *Wenn sich euer Projekt also irgendwann entwickelt ist es kein Problem, zu einem bezahlten fly.io überzugehen.

### Vorgehensweise

In diesem Artikel werden wir also die folgenden Schritte durchlaufen:

- Installation der Fly command-line tools
- Erstellung eines kostenlosen Fly.io Accounts
- Erstellung von zwei Server-Instanzen, eine Ghost, eine MySQL
- Deploy der app mit einem vorinstallierten (Docker)Image der Ghost Blogging Platform
- Deploy der Datenbank-Instanz mit MySQL 8.
- Einstellung und Konfiguration des Speichers für Ghost und die Speicherung der Daten in der MySQL 8 Datenbank
- Deploying unserer Apps!
- *Das wars*.

Das schöne ist: all das läuft automatisch mit einem Script ab. Ich habe das Script übertragen, angepasst und in eine install.sh Datei gepackt, die einzelne Schritte sind kommentiert.

## Anleitung Ghost 5 auf kostenlosem fly.io

Los gehts.

### 1. Install the Fly.io Command-Line Tools

Der erste Schritt besteht darin, die **fly commandline tools** zu installieren. Tut dies mit:

    curl -L https://fly.io/install.sh | sh

Linux

unter Linux, **oder** wenn ihr wie ich auf einem Mac arbeitet, mit [Brew](https://brew.sh):

    brew install flyctl

mac OS

Auf dem Mac arbeitet das Tool SED anders als auf anderen Unices, wir müssen den Befehl also für Linux oder macOS anpassen, das steht allerdings im Script.

Wechselt jetzt in einer Verzeichnis, in dem ihr die Konfigurationsdateien ablegen wollt. Ich habe das in Dokumente in meinem Homeverzeichnis getan.

    cd ~/Documents

### 2. Ladet euch das Script zur Installation (quasi One Click Hosting) herunter

Das Script findet ihr fortfolgend. Kopiert es und speichert es in einer Datei "install.sh". Dies könnt ihr im Terminal mit dem Editor *nano* oder *vi* tun.

    nano install.sh

Terminal

Vorab: Fly.io möchte eure Kreditkartendaten, um Misbrauch zu verhindern. Es wird jedoch nichts abgebucht, weil wir uns im "free" Bereich befinden. Das heißt, während das Script läuft, startet euer Browser und legt euch einen fly.io Account an, ihr müsst im Webinterface die Kreditkartendaten hinterlegen. Dann wechselt ihr zurück zum Terminal, denn dort laufen die eigentlichen Schritte ab, fly.io wird explizit über sein Commandline-Interface in der Shell bedient (bietet aber auch ein Webinterface)

Mein Script:

    #!/bin/bash
    
    # app Bezeichnung etc. 
    echo -n "App Namen eingeben: " && \
    read appname && \
    echo -n "Neues MYSQL Password eingeben: " && \
    read mysqlpassword && \
    echo -n "Neues MYSQL Root Password eingeben: " && \
    read mysqlrootpassword && \
    
    # Heredoc
    bash << EOF
    
    # Folgendes dient nur dem Debugging, weil jeder Befehl einzeln ausgegeben wird, könnte man auch auskommentieren
    set -x
    
    # Prüfe, ob Fly CLI installiert ist, installiere bei Bedarf 
    # Die CLI haben wir aber schon installiert, via brew für macos oder linux, deshalb auskommentiert an dieser Stelle.
    # command -v flyctl >/dev/null 2>&1 || { echo >&2 "Fly CLI required and not found. Installing..."; curl -L https://fly.io/install.sh | sh; }
    
    # Fly.io Account erstellen oder einloggen. Browser öffnet sich
    flyctl auth signup
    
    # Erstelle Arbeitsverzeichnis in dem die erstellten Config-Dateien liegen
    mkdir ghost-flyio && cd ghost-flyio
    
    # Erstelle eine App -- Ghost Docker Image, Smsterdam als Region, und app Name der zu Beginn eingetragen wurde -- aber noch kein deploy zu fly.io
    flyctl launch --name $appname --image=ghost:5.75.3 --region ams --no-deploy --org personal
    
    # Daten-Speicher für Ghost's content erstellen
    # Größe kann bis zu 3GB im free plan sein; Region wieder AMS
    flyctl volumes create ghost_data --region ams --size 3 --auto-confirm
    
    # Installiere sed (stream editor), falls nicht installiert; Auskommentiert, SED gibt es eigentlich immer. Falls er hier stoppt, brew install sed oder apt install sed rpm install sed etc. pp.
    #command -v sed >/dev/null 2>&1 || { echo >&2 "sed (Stream EDitor) required and not found. Installing..."; sudo apt install sed; }
    
    # Update port zu Ghost's default (2368)
    ## folgende Zeile für macOS
    sed -i'' -e 's/internal_port = 8080/internal_port = 2368/g' fly.toml
    #Folgende Zeile auskommentieren für Linux
    #sed -i 's/internal_port = 8080/internal_port = 2368/g' fly.toml 
    
    # Append info about where to find the persistent storage to fly.toml
    cat >> fly.toml << BLOCK
    [mounts]
    source="ghost_data"
    destination="/var/lib/ghost/content"
    BLOCK
    
    # Set Ghost url 
    flyctl secrets set url=https://$appname.fly.dev
    
    # Zweite Instanz für Datenbank Server anlegen
    mkdir ghost-flyio-mysql && cd ghost-flyio-mysql
    
    # Erstelle app für mysql 
    flyctl launch --name ${appname}-mysql --image=mysql:8 --region ams --no-deploy --org personal
    
    # If you aren't trying to stay within the free tier, uncomment this to give the MYSQL VM 2GB of ram
    # fly scale memory 2048 
    
    # Create a persistent volume for our MYSQL data 
    fly volumes create mysql_data --size 1 --region ams --auto-confirm
    fly secrets set MYSQL_PASSWORD=$mysqlpassword MYSQL_ROOT_PASSWORD=$mysqlrootpassword
    
    # Add our database credentials to the Ghost instance 
    fly secrets set database__client=mysql
    fly secrets set database__connection__host=${appname}-mysql.internal -a $appname
    fly secrets set database__connection__user=ghost -a $appname
    fly secrets set database__connection__password=$mysqlpassword -a $appname
    fly secrets set database__connection__database=ghost -a $appname
    fly secrets set database__connection__port=3306 -a $appname
    fly secrets set NODE_ENV=production
    cat > fly.toml << BLOCK2
    app = "$appname-mysql"
    kill_signal = "SIGINT"
    kill_timeout = 5
    processes = []
    [build]
    image = "mysql:8.0.32"
    [mounts]
    source="mysql_data"
    destination="/data"
    [env]
    MYSQL_DATABASE = "ghost"
    MYSQL_USER = "ghost"
    [processes]
    app = "--datadir /data/mysql --default-authentication-plugin mysql_native_password --performance-schema=OFF --innodb-buffer-pool-size 64M"
    BLOCK2
    
    # Note: if you aren't trying to stay within the free tier, you might want to remove the performance schema and buffer pool size flags above. 
    
    # Deploy MySQL server. 
    flyctl deploy
    cd ../
    
    # Deploy Ghost application server 
    flyctl deploy
    
    EOF

install.sh

Ich hatte vorhin bereits auf SED hingewiesen. Dieses funktioniert unter Linux anders als unter BSD (also auch unter macOS). Folgende Zeile müsst ihr für Linux anpassen, in meinem Script ist sie für macOS optimiert. Kommentiert die Zeile aus falls ihr Linux nutzt, falls ihr auf macOS seid passt schon alles:

    sed -i 's/internal_port = 8080/internal_port = 2368/g' fly.toml 

Befehl für Linux

### 3. Startet das One-Click-Script und erstellt Ghost 5 auf fly.io

Macht das Script ausführbar, damit ihr es starten könnt:

    chmod a+x install.sh

Terminal

Wenn ihr das Script nun startet, sollte er euch nach den verschiedenen Punkten fragen, die er für den Setup-Prozess benötigt. App Name, MySQL Passwort (ihr denkt euch hier ein neues Passwort aus, für den User und für Root, es gibt ja noch kein MySQL) etc. pp., tragt sie im Terminal ein. Diese Variablen nutzt er dann, um die Instanzen (Ghost und MySQL) zu erstellen und bei fly.io zu deployen, natürlich verschlüsselt.

    sh install.sh

Terminal

*Das wars. Viel Spaß am Gerät.*

### 4. Optional: Domain einbinden

Wenn ihr genügend getestet habt, oder generell, dann könnt ihr auch eure eigene Domain hinzufügen. Das tut ihr mit dem folgenden Befehl:

    fly domains add hostname.com
    fly certs add hostname.com

Nachdem ihr das Zertifikat geadded habt, solltet ihr in etwas folgendes lesen:

    You are creating a certificate for xxxxxxxxxxxx.com
    We are using lets_encrypt for this certificate.
    
    You can direct traffic to xxxxxxxxxxxx.com by:
    
    1: Adding an A record to your DNS service which reads
    
    A @ XX.XX.XX.XX
    
    You can validate your ownership of xxxxxxxxxxxx.com by:
    
    2: Adding an AAAA record to your DNS service which reads:
    
    AAAA @ XXXX:XXXX:X::X:XXXX

Tut dies, geht zu eurem Domain-Hoster und tragt die DNS-Records für A und AAAA nach. 

Der Status des CERT kann mit folgendem Befehl überprüft werden: `fly certs list` and `fly certs show **hostname.com**`.

### 5. Anderes

- Mit folgendem Befehl könnt ihr eine App wieder löschen: 

    fly apps delete appname

## Ressourcen
[

Deploy app servers close to your users · Fly

![](https://fly.io/phx/ui/images/favicon/apple-touch-icon-3e4c9ce127b5cd6f5516638d4bbf1dd5.png?vsn=d)

![](https://fly.io/phx/ui/images/party-on-ebccc27902940939ca1e2bf7a097c2a9.webp?vsn=d)
](https://fly.io)[

How to Host a Ghost Blog for Free on Fly.io

Ghost is an amazing platform for content creators with tons of features to enable blogging, newsletters and subscriptions. Most importantly, it’s a pleasure to use. If you’ve ever felt the urge to gouge our your own eyeballs after trying to use WordPress, you should definitely give Ghost a

![](https://blixtdev.com/favicon.ico)⚡️ Blixt Dev ⚡️Jonathan

![](https://images.unsplash.com/photo-1604013527955-f310df076541?crop=entropy&amp;cs=tinysrgb&amp;fit=max&amp;fm=jpg&amp;ixid=MnwxMTc3M3wwfDF8c2VhcmNofDZ8fGdob3N0fGVufDB8fHx8MTY2NTY1ODgzNg&amp;ixlib=rb-1.2.1&amp;q=80&amp;w=2000)
](https://blixtdev.com/how-to-host-a-ghost-blog-for-free-on-fly-io/)[

Tutorial: Host Ghost 5 + MySQL 8 on Fly.io Free Tier

After a lot of tinkering, I have found a way of running Ghost 5 in production with MySQL 8 on Fly’s free tier! Here is a tutorial with the script I used: Let me know if you run into any issues following the tutorial; it’s brand new so there may still be bugs that need to be worked out 🙂

![](https://global.discourse-cdn.com/business4/uploads/ghost2/optimized/2X/f/f381b3b952df5ad42fe691a8b14aa7f0c96c461a_2_180x180.png)Ghost Forumcuriositry

![](https://global.discourse-cdn.com/business4/uploads/ghost2/original/2X/8/8d4e1be1543b3ed506f105953a0d062b84797e42.png)
](https://forum.ghost.org/t/tutorial-host-ghost-5-mysql-8-on-fly-io-free-tier/33095)
---
