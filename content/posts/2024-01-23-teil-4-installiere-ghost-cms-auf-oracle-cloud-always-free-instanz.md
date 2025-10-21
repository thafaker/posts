---
title: Teil 4 - Installiere Ghost CMS auf Oracle Cloud always Free Instanz
slug: teil-4-installiere-ghost-cms-auf-oracle-cloud-always-free-instanz
date_published: 2024-01-23T06:20:02.000Z
date_updated: 2025-06-10T10:01:29.000Z
tags: mysql 8, ghost, nginx, oracle cloud, anleitung, how to, howto, linux swap
excerpt: Teil 4 - Ich werde in dieser Blogreihe darüber berichten wie man sich bei Oracle Cloud registriert, eine kostenlose Instanz klickt, die Virtuelle Maschine startet, diese Maschine als Webserver konfiguriert und letztendlich Ghost nebst Datenbank installiert.
---

Ich werde in dieser **Blogreihe** darüber berichten wie man sich bei Oracle Cloud registriert, eine kostenlose Instanz klickt, die Virtuelle Maschine startet, diese Maschine als Webserver konfiguriert und letztendlich Ghost nebst Datenbank installiert.

## Table of Contents

- [Teil 1 - Einrichten eines Accounts bei Oracle Cloud](__GHOST_URL__/wie-man-sich-kostenlos-zwei-virtuelle-server-instanzen-mit-ubuntu-22-04-klickt-und-betreibt/)
- [Teil 2 - Hochfahren einer Oracle Virtual Machine](__GHOST_URL__/teil-2-hochfahren-einer-oracle-virtual-machine/)
- [Teil 3 - Konfiguriere die Oracle Virtual Machine als Webserver](__GHOST_URL__/teil-3-konfiguriere-die-oracle-virtual-machine-als-webserver/)
- **Teil 4 - Installiere Ghost CMS**

---

💡

Bevor wir nun anfangen unsere Domain zu verbinden, müssen wir noch etwas an unserer Maschine *tunen*. Bei mir lief der Prozess der Ghost-Installation wegen mangelndem Arbeitsspeicher nicht durch. Ghost blieb an unterschiedlichen Stellen hängen und so fügte ich ein SWAP-Drive hinzu: Problem behoben.

### Swap Speicher zur VM hinzufügen (Auslagerungsdatei)

**N**eues Swapfile von 1 GB Größe im Root-Verzeichnis erstellen:

    sudo fallocate -l 1G /swapfile 

Dateizugriff ändern:

    sudo chmod 600 /swapfile 

Die erstellte Datei in Swap umwandeln:

    sudo mkswap /swapfile 

**D**as neu erstellte Swapfile aktivieren und in das System einbinden. Es steht danach direkt zur Verfügung:

    sudo swapon /swapfile 

**N**ach einem Neustart soll unser Swapfile automatisch eingebunden werden. Dazu editieren wie etc/fstab und tragen folgende Zeile genau so ein:

    /swapfile   swap   swap     defaults    0 0

Speichern und fertig. Jetzt und nach einem Neustart stehen uns 1 GB Swap zur Verfügung. Bei mir sind 266 MB des Swaps bereits in Benutzung.
![HTop auf meiner VM, Swap 1024 MB](__GHOST_URL__/content/images/2024/01/Bildschirmfoto-2024-01-23-um-07.42.41.png)HTop auf meiner VM, Swap 1024 MB
---

### Verbinde deine Domain mit der VM

Verbinden wir unsere Domain thahipster.de mit der VM. Dies geschieht über A-Records und weitere Einträge, die beim Registrar eingetragen werden müssen. Ich verwende INWX.de. Am Ende verweist unsere Domain auf auf unsere Oracle Cloud Virtual Machine. Das theoretische Vorgehen ist immer gleich. Wir müssen zwei Einstellungen managen: einmal die Domain mit www und einmal muss sie ohne www auf unsere VM zeigen. A ist der IPv4 Record, AAAA ist der IPv6 Record, den wir aber nicht haben.
![DNS Settings für die Domain auf inwx.de](__GHOST_URL__/content/images/2024/02/Bildschirmfoto-2024-02-01-um-21.19.19.png)DNS Settings für die Domain auf inwx.de
Nachdem die Änderungen gespeichert sind, dauert es eine kleine Weile bis die Domain funktioniert, die Veränderungen im DNS müssen sich durchsetzen. Dann sollte der NGINX-Placeholder auch über die Domain erreichbar sein.

---

## VM Setup

Wir sollten NGINX, MySQL & Nodejs installiert haben. Jetzt geht es ums Eingemachte. Da Ghost nur noch sehr reduziert und fokussiert mit seinen Entwickler-Ressourcen umgeht, unterstützen sie offiziell ausschließlich Ubuntu Linux, MySQL 8 und Nginx X. 

**Datenbank Setup**
Wir konfigurieren einen Datenbankbenutzer unter MySQL für Ghost. Gebt diese Befehle wieder nacheinander ein. Ändert die Dinge wie Password1234 nach eurem Wunsch.

    # MySQL starten
    sudo mysql
    
    # Datenbankbenutzer mit Passwort erstellen
    create user 'ghost'@'localhost' identified by 'Password1234';
    
    # Volle Rechte für den neuen Benutzer
    grant all privileges on *.* to 'ghost'@'localhost';
    
    # Ghost Datenbank erstellen
    create database ghost;
    
    # MySql beenden
    exit
    
    # Neustart des MySQL Server
    sudo service mysql restart

**Install Ghost-CLI**
Jetzt installieren wir das Ghost Command Line Interface, damit installieren, aktualisieren und konfigurieren wir Ghost.

    # Installation der Ghost CLI
    sudo npm install ghost-cli@latest -g

**Install Ghost**
Wir erstellen einen neuen Ordner in unserem Webserver und installieren Ghost.

    # Create directory ghost
    sudo mkdir -p /var/www/ghost
    
    # Set directory owner
    sudo chown ubuntu:ubuntu /var/www/ghost
    
    # Set the correct permissions
    sudo chmod 775 /var/www/ghost
    
    # Then navigate into it
    cd /var/www/ghost
    
    # initiate the install cmd
    ghost install

### Installationsfragen

Während der Installation wird uns Ghost einige Fragen stellen:

- Blog URL
Das ist die Domain die wir mit unserer VM verbunden haben https://thahipster.de 
*- Machen Sie sich keine Sorgen, wir konfigurieren SSL/https später. Überspringen Sie das Hinzufügen von www, wir richten dies ebenfalls später ein.*
- MySQL hostname
MySQL läuft lokal, belasst es also bei: localhost - wenn man sich eine zweite VM nur für MySQL einrichtet, könnte man hier den Datenbankserver einrichten. Tatsächlich sind im always free plan zwei VMs enthalten.
- MySQL username / password
Das sind Benutzer und Passwort was wir vorhin im Terminal erstellt haben.
- Ghost database name
Das ist der Name der Datenbank den wir vorher eingerichtet haben.
- Set up NGINX?
Ja, lass Ghost den Nginx für uns konfigurieren. Man kann das auch manuell tun, aber hier funktioniert das automatisch sehr gut
- Set up SSL?
Ja, Ghost kümmert sich um unser *Letsencrypt*-Zertifikat und stellt https SSL korrekt ein, das hat bei mir alles nahtlos funktioniert.
- Set up systemd?
Ja, es ist der Dienst auf unserem Linux, der für Start/Stop der Dienste zuständig ist.
- Start Ghost?
Ja, starte Ghost für uns. 

💡

Falls der Installationsprozess abstürzt oder die Verbindung zur VM beendet wird, kann man den Prozess der Installation jederzeit wieder starten.

💡

z.B. wenn es ein Problem bei SSL gab, kann man ghost später mit`ghost setup ssl` an der Stelle weiter machen lassen.

---

## Funktioniert www nicht?

www wird als sekundäre Domäne betrachtet und nicht im Rahmen der Installation eingerichtet – also lasst uns mit der Einrichtung fortfahren.

Fügen Sie in Ihrem Terminal Folgendes hinzu und ersetzen Sie mydomain durch Ihre kanonische Basisdomäne, die Sie für Ghost definiert haben **www.thahipster.de**:

    # Determine your secondary URL (primary domain with www.)
    ghost config url https://www.mydomain.com
    
    # Get Ghost-CLI to generate an SSL setup for you:
    ghost setup nginx ssl
    
    # Change your config back to your canonical domain
    ghost config url https://mydomain.com
    
    # Fertig, jetzt wechseln wir zu Nginx:
    cd /etc/nginx/sites-available/

Aktualisiert die beiden www-Dateien und fügt folgenden Block ein in

- www.mydomain.com.conf
- www.mydomain.com-ssl.conf

ein:

    location / {
        return 301 https://mydomain.com$request_uri;
    

So sieht die Datei dann komplett aus:

    server {
        listen 80;
        listen [::]:80;
    
        server_name www.mydomain.com;
        root /var/www/ghost/nginx-root; # Used for acme.sh SSL verification (https://acme.sh)
    
        location / {
            return 301 https://mydomain.com$request_uri;

Example nginx conf with return in location block

Wenn wir damit fertig sind, prüfen wir, ob die Syntax unserer Konfigurationsdateien korrekt ist, mit folgendem Befehl:

    # Get nginx to verify your config
    sudo nginx -t
    
    # Ergebnis sollte ungefäht sein:
    nginx: the configuration file /etc/nginx/nginx.conf syntax is ok
    nginx: configuration file /etc/nginx/nginx.conf test is successful
    
    # Dann starten wir nginx mit der neuen Konfiguration neu:
    sudo nginx -s reload

Das ist genau der Weg wie thahipster.de jetzt läuft und funktioniert.

---

## **Gratulation. Ghost und NginX laufen**

Wenn wir nun auf unsere Domain zugreifen, sollte die Basis-Ghost-Site angezeigt werden! Um das CMS einzurichten, einen Benutzer anzulegen und den ersten Artikel zu schreiben, rufen wir https://mydomain.com/ghost/ auf

![](__GHOST_URL__/content/images/2024/09/Bildschirmfoto-2024-09-17-um-18.00.25.png)

![](__GHOST_URL__/content/images/2024/09/Bildschirmfoto-2024-09-17-um-18.03.40.png)

ghost cms right after installation as seen on my domain apfelhammer.de

**Das wars. Bei Fragen könnt gern kommentieren.**
