---
title: [HOW TO] Ghost 1.X auf dem Uberspace
slug: how-to-ghost-1-x-auf-dem-uberspace
date_published: 2017-08-02T15:43:09.000Z
date_updated: 2018-08-22T09:37:42.000Z
tags: howto, how to, anleitung, ghost 1.0, uberspace, fix.it
---

Nachdem ich ja [hier](__GHOST_URL__/ghost-1-0-ist-da/) auf das neue und noch viel tollere **Ghost Version 1.0** (genau genommen ist es schon v1.18.0) hingewiesen habe, möchte ich nunmehr aufzeigen, wie man Ghost auf dem Uberspace installieren kann. Wir gehen in dieser Anleitung davon aus, dass ihr bereits einen Uberspace besitzt. 

![](http://thafaker.de/content/images/2017/07/Bildschirmfoto-2017-07-27-um-17.33.04.png)

[**UPDATE**] [An dieser Stelle](__GHOST_URL__/ghost-update-uberspace/) habe ich in 6 Schritten beschrieben, wie man sein Ghost per Hand auf dem Uberspace aktualisieren kann.

### Datensicherung Ghost 0.11.X

Hier werde ich kurz beschreiben, wie ihr vorgehen solltet. Da Ghost 1.X die Datenbank ändert, ist ein Update nicht möglich. Ihr müsst eure Artikel also exportieren und wieder importieren. DAS A UND O IST IMMER DIE DATENSICHERUNG, ge.

1. Klickt in eurem Ghost auf **Labs**
![](__GHOST_URL__/content/images/2017/08/ghost_1.jpg)
2. Wählt den Knopf **Export**. Euer Browser lädt und müsste mit dem Download der Artikel als *.JSON Datei beginnen. Bei mir ist diese Datei 18,5 MB groß. Hier sind jedoch nur die Artikel und keine Medien beinhaltet. Die Uploads, also eure Bilder etc., liegen woanders und müssen per FTP separat und händisch gesichert werden.
![](__GHOST_URL__/content/images/2017/08/ghost_2-jpg.JPG)
3. Sichert eure Uploads und Medien. Loggt euch dazu per FTP in eurem Uberspace ein. Wechselt nun in das Verzeichnis `~/ghost/content/` und sichert mit dem Ordner `images` all eure Bilder. Genau so tut ihr das für die anderen Ordner.
![](__GHOST_URL__/content/images/2017/08/Bildschirmfoto-2017-08-02-um-17.41.13.png)
4. Genau dort hin muss der Kram später auch wieder hoch geladen werden.
5. Leider ist mir derzeit nicht bekannt, wie sich das mit der Kompatibilität von Themes verhält. Ob mein altes 0.11. Theme auch unter 1.X läuft, ist unklar.**UPDATE**[[1]](#fn1)
6. Jetzt habt ihr zumindest euer Ghost gesichert.
7. …

### How To Installation Ghost 1.0 auf dem Uberspace

Wie ich vorhin per Twitter erfahren habe, sind die Jungs von Uberspace wieder besonders schnell gewesen und haben ihr bisheriges HowTo zur Installation von Ghost 0.X auf die neue Version 1.X angepasst. Grundlegend scheint sich am Setup gar nichts geändert zu haben. Der Weg, den Uberspace vorzubereiten und Ghost als Dienst zu installieren, ist quasi gleich geblieben.

> Ja, wir haben unsere Anleitung im Wiki angepasst: [https://t.co/th5yIEwytx](https://t.co/th5yIEwytx)
> &mdash; Uberspace.de (@ubernauten) [1. August 2017](https://twitter.com/ubernauten/status/892360923112976384)

Ihr könnt also ganz beruhigt der [**Anleitung dort folgen**](https://wiki.uberspace.de/cool:ghost). Leider gibt es keine Updatemöglichkeit, da Ghost 1 sozusagen eine neue Software ist. Ihr müsst also eure Daten sichern, das alte Ghost löschen und das neue Ghost installieren. Dann müsst ihr die Daten wieder importieren. Ghost hat mit 1.X den Wechsel der Datenbank auf MySQL vollzogen, zuvor war das über eine sqlite-Datenbank bewerkstelligt.

## Migration Ghost 0.11.X nach Ghost 1.X Uberspace

Wenn ihr also eure alten Daten gesichert habt, dann ist der wichtigste Schritt vollzogen. Nun geht es darum das alte Ghost zu löschen, das neue Ghost zu installieren und die Daten die gesichert wurden, zurück zu spielen. Ich lege mir testweise einen zweiten Uberspace-Account an auf dem ich Ghost 1.0 installiere, um das zu testen.

![](__GHOST_URL__/content/images/2017/08/Bildschirmfoto-2017-08-02-um-18.32.21.png)

1. Loggt euch via SSH in euren Uberspace ein und wechselt ins Homeverzeichnis.

    cd ~
    

1. Beendet den Dienst Ghost:

    svc -d ~/service/ghost
    

1. Installiert den KMEX-Migrator:

    npm install -g knex-migrator
    

1. Ghost ist in nodejs geschrieben, daher brauchst du erstmal eine aktuelle Version von nodejs. Uberspace legt die nodejs-Version 6 ans Herz denn aktuell ist dies die letzte LTS-Version.

    [lisbeth@amnesia ~]$ echo 'export PATH=/package/host/localhost/nodejs-6/bin:$PATH' >> ~/.bash_profile
    

    [lisbeth@amnesia ~]$ source ~/.bash_profile
    

    [lisbeth@amnesia ~]$ node -v
    

1. Vorausgesetzt ihr habt Ghost nach Anleitung von Uberspace installiert, macht ihr ein mv

    mv ghost ghost-0.11.X
    

Das verschiebt euer Ghost in den Ordner ghost-0.11.X, das ist nun die alte Installation, die bei Bedarf zurück verschoben werden kann.

1. Ladet euch das aktuellste Ghost herunter und entpackt es. Führt folgende Befehle nacheinander aus:

    curl -L https://ghost.org/zip/ghost-latest.zip -o ghost-latest.zip
    

    unzip ghost-latest.zip -d ghost && cd ghost
    

1. Installiert Ghost

    npm install --python="/usr/local/bin/python2.7" --production
    

1. Legt euch eine Konfigurationsdatei an. Da Ghost nun mit MySQL läuft, müsst ihr dazu eine MySQL Datenbank in eurem Uberspace anlegen und diese in der Konfigurationsdatei entsprechend eintragen ([hier](https://wiki.uberspace.de/cool:ghost) beschrieben). Wechselt in euer Ghost-Verzeichnis und legt die Datei an. `nano config.production.json`

Kopiert folgenden Text hinein, ganz so, wie auch bei [Uberspace](https://wiki.uberspace.de/cool:ghost) beschrieben.

    {
        "url": "EURE DOMAIN",
        "database": {
            "client": "mysql",
            "connection": {
                "host"     : "localhost",
                "user"     : "EUER GHOST USER",
                "password" : "EUER MYSQL PW",
                "database" : "DER NAME DER DATENBANK",
                "charset"  : "utf8"
            }
        },
        "server": {
            "host": "127.0.0.1",
            "port": "EUER GHOSTPORT"
        },
        "auth": {
            "type": "password"
        },
        "paths": {
            "contentPath": "content/"
        },
        "logging": {
            "level": "info",
            "rotation": {
                "enabled": true
            },
            "transports": ["file", "stdout"]
        }
    }
    
    

Ihr müsst alle Bereiche ausfüllen, die **GROß** geschrieben sind. Das MySQL-Passwort findet ihr in der [.my.cnf](https://wiki.uberspace.de/database:mysql#zugangsdaten). Dazu gebt ihr folgenden Befehl in euer Terminal ein: `[thafaker@menkar ~]$ cat ~/.my.cnf`

7. Jetzt führt ihr folgenden Befehl aus, damit die Datenbank initialisiert werden kann bzw. die Tabellen angelegt werden können.

    NODE_ENV=production knex-migrator init
    

1. Ihr könnte Ghost als Service wieder starten, dies tut ihr nach alter Manier folgendermaßen: `svc -u ~/service/ghost/`
2. Check bitte mit folgendem Befehl, ob alles rund läuft: `tail -F ~/service/ghost/log/main/current`

[**UPDATE**] [An dieser Stelle](__GHOST_URL__/ghost-update-uberspace/) habe ich in 6 Schritten beschrieben, wie man sein Ghost per Hand auf dem Uberspace aktualisieren kann.

---

1. 
Mittlerweile ist klar, dass alle alten Themes portiert werden müssen. Ghost.org hat dazu eine Anleitung bereit gestellt. [↩︎](#fnref1)
