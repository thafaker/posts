---
title: Streaming Server für eigene MP3s betreiben
slug: streaming-server-fur-eigene-mp3
date_published: 2023-06-29T11:14:42.000Z
date_updated: 2023-06-29T11:34:04.000Z
tags: ampache, lubuntu, linux, ubuntu 20.04, mp3, Musik-Streaming-Dienst, anleitung, how to, howto
---

Angenommen, wir möchten eine App ähnlich wie Spotify verwenden, um unsere eigene Musik zu streamen. Ich finde das cool. Volle Kontrolle und meine Musiksammlung liegt ja schon vor. Ich mag diese. Natürlich habe ich dann keine "Spotify Magic ähnliche Songs" aber das ist okay. 

In diesem Fall gibt es einige Musik-Streaming-Plattformen, die wir auf unserem Linux-Server einrichten können, um unsere eigene Musiksammlung zu organisieren und über das Internet zu streamen. Hier sind zwei beliebte Optionen:

1. **[Subsonic](http://www.subsonic.org/pages/index.jsp)**: Subsonic ist eine Open-Source-Plattform, mit der Sie Ihre Musiksammlung auf einem Server hosten und von überall aus darauf zugreifen können. Sie können Subsonic auf Ihrem Linux-Computer installieren und dann eine entsprechende Subsonic-App auf Ihrem Smartphone verwenden, um Ihre Musik zu streamen. Subsonic bietet Funktionen wie das Erstellen von Wiedergabelisten, das Durchsuchen von Künstlern und Alben sowie das Offline-Hören.
2. **[Ampache](https://ampache.org/)**: Ampache ist eine weitere Open-Source-Software, mit der Sie Ihre eigene Musiksammlung streamen können. Sie können Ampache auf Ihrem Linux-Computer installieren und dann eine Ampache-kompatible App auf Ihrem Smartphone verwenden, um auf Ihre Musik zuzugreifen. Ampache bietet ähnliche Funktionen wie Subsonic, einschließlich Wiedergabelisten, Künstler- und Album-Browsing sowie Offline-Hören.

Weil Subsonic JAVA braucht um zu laufen und ich auf diesen bloat-overhead im Moment keine Lust habe, habe ich mich für das gut abgehangene Ampache entschieden, was mittlerweile in Version 5.X vorliegt. Mein Setup besteht aus einem *Ubunutu 20.04.06* Server mit *Apache *und der soll nun ein Ampache oben drauf bekommen.

## How To Install Ampache on Ubuntu 20.04.

Um unsere eigenen MP3s übers Internet via App auf dem Smartphone hören zu können, gehen wir also folgendermaßen vor. Wir installieren Apache, PHP, MySQL und letztendlich Ampache. In MySQL erstellen wir uns eine Datenbank mit Nutzer und Kennwort um sie in Ampache nutzen zu können. Dann konfigurieren wir den Rest per Webinterface.

1. Öffne das Terminal auf Ubuntu 20.04.
2. Aktualisiere zunächst die Paketliste, indem du den Befehl ausführst:

`sudo apt update`

1. Installiere die erforderlichen Abhängigkeiten, einschließlich des Webservers Apache, der PHP-Erweiterungen und der Datenbank (MySQL):

    sudo apt install apache2 libapache2-mod-php mariadb-server php php-mysql php-xm

1. Starte den Apache-Webserver und aktiviere die erforderlichen Apache-Module:

`sudo systemctl start apache2 sudo systemctl enable apache2 sudo a2enmod rewrite`

1. Öffne den MySQL-Server-Sicherheitsassistenten, um die grundlegende MySQL-Konfiguration durchzuführen:

`sudo mysql_secure_installation`

Folge den Anweisungen, um ein Root-Passwort festzulegen und andere Sicherheitsmaßnahmen zu ergreifen.

1. Erstelle eine neue Datenbank und einen Datenbankbenutzer für Ampache: Jeder Befehl ist eine Zeile, ENTER danach drücken:

`sudo mysql -u root -p `
`CREATE DATABASE ampachedb; `
`CREATE USER 'ampacheuser'@'localhost' IDENTIFIED BY 'ampachepassword'; GRANT ALL PRIVILEGES ON ampachedb.* TO 'ampacheuser'@'localhost'; FLUSH PRIVILEGES; EXIT;`

**ACHTUNG** Stelle sicher, dass du 'ampachedb', 'ampacheuser' und 'ampachepassword' durch die gewünschten Werte ersetzt.

1. Wechsle in das Verzeichnis "/var/www/html" (oder das entsprechende Verzeichnis des Apache-Webservers):

`cd /var/www/html`

1. Lade die neueste Version von Ampache von der offiziellen Website herunter und entpacke sie (Jede Zeile ein Befehl, danach ENTER drücken):

`sudo wget https://github.com/ampache/ampache/archive/master.zip `
`sudo unzip master.zip `
`sudo rm master.zip `
`sudo mv ampache-master ampache`

1. Gib dem Webserver Schreibzugriff auf das Ampache-Verzeichnis:

`sudo chown -R www-data:www-data ampache`

1. Gib dem Ampache die erforderlichen Berechtigungen:

`sudo chmod -R 755 ampache`

1. Konfiguriere Ampache, indem du den Webbrowser öffnest und die URL "[http://localhost/ampache](http://localhost/ampache)" (oder die entsprechende URL Ihres Webservers) aufrufst.
2. Befolge die Anweisungen im Ampache-Installationsassistenten, um die erforderlichen Einstellungen vorzunehmen, einschließlich der Datenbankinformationen (Datenbanktyp: MySQL, Datenbankserver: localhost, Datenbankname: ampachedb, Benutzername: ampacheuser, Passwort: ampachepassword).
3. Nach Abschluss der Installation kann man sich mit den Ampache-Anmeldeinformationen anmelden und die Musiksammlung hinzufügen, indem man auf "Catalog" klickt und den Anweisungen folgt.
4. Jetzt brauchen wir noch eine passende App (z.B. [Amperfy](https://apps.apple.com/us/app/amperfy-music/id1530145038)*) auf dem Handy, verbinden uns zu unserem Server und schwupps können wir unsere Musik genießen. Mega gut.

*Viele Grüße*
*Das ist kein Affiliate-Link sondern nur ein Beispiel zu einer App
