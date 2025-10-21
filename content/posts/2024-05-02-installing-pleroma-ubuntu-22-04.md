---
title: Installiere Pleroma Mastodon auf Ubuntu 22.04
slug: installing-pleroma-ubuntu-22-04
date_published: 2024-05-02T18:31:45.000Z
date_updated: 2024-11-02T09:37:30.000Z
tags: anleitung, how to, howto, pleroma, fediverse, mastodon, linux, ubuntu
---

In diesem Artikel beschreiben wir, wie ihr auf einem Ubuntu 22.04 einen eigenen "Mastodon" Server installieren könnt und am großen **Fediverse** teilhabt. Allerdings installieren wir nicht *Mastodon* sondern **Pleroma**. Pleroma verbraucht weniger Ressourcen und ist schneller, läuft also auch auf kleinen respektive *Always Free Cloud *Instanzen annehmbar freundlich. [Hier](__GHOST_URL__/wie-man-sich-kostenlos-zwei-virtuelle-server-instanzen-mit-ubuntu-22-04-klickt-und-betreibt/) habe ich übrigens beschrieben, wie man sich eine Always Free Oracle Cloud Instanz aufsetzt und dort am Beispiel ein Ghost CMS Weblog installiert. Falls ihr also noch auf der Suche nach einem Server seid, dann nutzt [jenen Artikel](__GHOST_URL__/wie-man-sich-kostenlos-zwei-virtuelle-server-instanzen-mit-ubuntu-22-04-klickt-und-betreibt/).

**Pleroma** ist also ein leichter Server, der am sogenannten Fediverse (das Fediverse ist ein Zusammenschluss unabhängiger sozialer Netzwerke, die es den Benutzern ermöglichen, ähnlich wie auf einer einzigen Plattform miteinander zu interagieren) teilnimmt. Pleroma ist eine Alternative zur sehr bekannten Mastodon-Serversoftware. Mastodon ist hierbei aber genauso wie auch Pleroma nur ein Teilnehmer im Fediverse, der das ActivityPub-Protokoll unterstützt. Im Vergleich zu Mastodon benötigt Pleroma für eine ähnliche Installation aber wie schon erwähnt nicht so viel Prozessor oder RAM. Dieses Tutorial dokumentiert die Installationsschritte für einen Pleroma-Server. Der Server kann die Heimatinstanz einer Einzelperson für das Fediverse oder eine große Instanz zum Teilen mit Freunden, Familie oder Interessengemeinschaften sein.

## Voraussetzung

- Ein frisches Ubuntu 22.04 LTS. (Eine Single-User-Instanz von Pleroma funktioniert problemlos mit 1 GB RAM. Der Hostname sollte ein *fully qualified domain name* (FQDN) sein, sowas wie `pleroma.example.com` 
Pleroma und Ubuntu nutzen insgesamt ca. 8.2 GB Festplatte.)
- Wir brauchen einen Nicht-Root-Nutzer mit SUDO Rechten. 
- Ihr braucht eine Domain die mit eurem Server verbunden ist. Ich selbst benutze in der Realität tatsächlich *pleroma.apfelhammer.de* 😄

## Beispiele

Diese Anleitung nutzt folgende Beispiele:

- Server hostname: **pleroma**
- Server Fully Qualified Domain Name (FQDN): **pleroma.example.com**
- IP Adresse: **192.0.2.1**

## Grundlegende Schritte

### Geht sicher dass euer System up-to-date ist 

Für optimale Leistung und Sicherheit sollte auf dem System die aktuellste Software ausgeführt werden.

    $ sudo apt update
    $ sudo apt -y full-upgrade

Löscht unbenutzte Software-Pakete:

    $ sudo apt autoremove

### Installiert Postgres und benötigte Software

    $ sudo apt -y install git build-essential postgresql postgresql-contrib cmake libmagic-dev

### Installiert Elixir und Erlang

    $ sudo apt -y install elixir erlang-dev erlang-nox

### Installiert die image manipulation tools

Die sind für die Medien-Uploads der User wichtig.

    $ sudo apt -y install imagemagick ffmpeg libimage-exiftool-perl

## Installation von Pleroma

Legt einen neuen Benutzer an, unter dem Pleroma (Username: pleroma) läuft:

    $ sudo useradd -r -s /bin/false -m -d /var/lib/pleroma -U pleroma

Erstellt das Pleroma Arbeitsverzeichnis unter /opt und vergebt die Schreibrechte an den Pleroma-User:

    $ sudo mkdir -p /opt/pleroma
    $ sudo chown -R pleroma:pleroma /opt/pleroma

Cloned das Pleroma git repository als der neu angelegte Pleroma Benutzer. Ihr loggt euch hierbei nicht als pleroma ein, sondern führt die Schritte via sudo durch:

    $ sudo -Hu pleroma git clone -b stable https://git.pleroma.social/pleroma/pleroma /opt/pleroma

Wechselt in das pleroma Verzeichnis:

    $ cd /opt/pleroma

installiert Pleroma's unterstützende Pakete. antwortet mit **Y**es falls ihr gefragt werdet, ob ihr **Hex** installieren wollt.

    $ sudo -Hu pleroma mix deps.get

Erstellt die pleroma Konfiguration. Dieser Schritt dauert insgesamt einige Minuten, weil er die ganzen Pakete kompiliert. Antwortet mit **Y**es wenn ihr gefragt werdet, ob ihr **rebar3** installieren wollt.

    $ sudo -Hu pleroma MIX_ENV=prod mix pleroma.instance gen

Das Konfigurationsprogramm stellt euch während des Prozesses einige Fragen. Beantwortet sie wie folgt:

---

> What domain will your instance use? (e.g pleroma.soykaf.com) []  **put FQDN here** ENTER
> What is the name of your instance? (e.g. The Corndog Emporium) [] **name for server** ENTER What is your admin email address? []  **email address** ENTER
> What email address do you want to use for sending email notifications? [] **email address** ENTER
> Do you want search engines to index your site? (y/n) [y] ENTER Do you want to store the configuration in the database (allows controlling it from admin-fe)? (y/n) [n]  Y ENTER
> What is the hostname of your database? [localhost] ENTER What is the name of your database? [pleroma] ENTER What is the user used to connect to your database? [pleroma] ENTER What is the password used to connect to your database? [autogenerated] ENTER
> Would you like to use RUM indices? [n] ENTER
> What port will the app listen to (leave it if you are using the default setup with nginx)? [4000] ENTER
> What ip will the app listen to (leave it if you are using the default setup with nginx)? [127.0.0.1] ENTER What directory should media uploads go in (when using the local uploader)? [uploads] ENTER
> What directory should custom public files be read from (custom emojis, frontend bundle overrides, robots.txt, etc.)? [instance/static/] ENTER
> Do you want to strip location (GPS) data from uploaded images? This requires exiftool, it was detected as installed. (y/n) [y] ENTER
> Do you want to anonymize the filenames of uploads? (y/n) [n]  Y ENTER Do you want to deduplicate uploaded files? (y/n) [n] Y ENTER
> Writing config to config/generated_config.exs. Writing the postgres script to config/setup_db.psql. Writing /opt/pleroma/instance/static/robots.txt.
> 
> All files successfully written! Refer to the installation instructions for your platform for next steps.
> Please transfer your config to the database after running database migrations. Refer to "Transfering the config to/from the database" section of the docs for more information.

---

### Kopiert die Konfigurationsdateien an ihre richtige Stelle:

    $ sudo -Hu pleroma mv config/{generated_config.exs,prod.secret.exs}

## Verbessert die Sicherheit

Setzt das `secure_cookie_flag` auf *true* damit die [cookies](https://owasp.org/www-community/controls/SecureCookieAttribute) über eine sichere Verbindung gesendet werden.

    $ sudo sed -i 's/secure_cookie_flag: false/secure_cookie_flag: true/g' config/config.exs

Aktiviert die *strict transport security* damit ein Angreifer eure HTTPS Verbindung nicht auf HTTP zurück setzen kann.

    $ sudo sed -i 's/ sts: false/ sts: true/g' config/config.exs

### Aktualisiert die ca-certificates.crt Dateien und fügt sie zur pleroma Konfiguration hinzu:

Bei **path/to/file** müsst ihr euer Verzeichnis mit den Zertifikaten auf eurem Server nutzen, bei mir ist das /etc/letsencrypt/archive und der Ordner der Domain. Ich habe nämlich bereits meine Domain mit meinem Server verbunden und bei mir läuft auch schon NGINX, der Webserver. Ich habe also schon HTTPS also SSL-Zertifikate installiert und zeige auf diese, weil die schon existierende Domain durch pleroma genutzt wird.

    $ sudo update-ca-certificates --fresh
    $ sudo sed -i 's,path/to/file/with/PEM/cacerts,/etc/ssl/certs/ca-certificates.crt,' config/description.exs

### Erstellt die Postgres Datenbank:

Ihr befindet euch im Verzeichnis **/opt/pleroma/**

    $ sudo -Hu postgres psql -f config/setup_db.psql

### Startet die Datenbank Migration:

    $ sudo -Hu pleroma MIX_ENV=prod mix ecto.migrate

## Installiert Nginx, falls noch nicht vorhanden:

Ich habe Nginx bereits installiert und er funktioniert auch korrekt. Falls ihr euch ein frisches Ubuntu aufgesetzt habt, falls ihr eure Domain noch nicht mit einem SSL-Zertifkat versehen habt, müsst ihr das jetzt tun:

Nginx agiert hierbei als reverse proxy vor Pleroma, kümmert sich um TLS und das Session-Managament.

    $ sudo apt -y install nginx

### stoppt Nginx damit der Certbot Port 80 benutzen kann:

Und noch mal, falls ihr schon NGINX nebst Domain eingerichtet habt, läuft das alles schon und ihr braucht diesen Schritt nicht durchführen.

    $ sudo service nginx stop

### Konfiguriert die Firewall (ufw oder iptables) und erlaubt eingehende TCP Verbindungen auf Port 80 und 443 (SSL):

    $ sudo ufw allow http
    $ sudo ufw allow https

Die Konfiguration für **iptables** lautet folgendermaßen:

    # HTTP: 80
    sudo iptables -I INPUT 6 -m state --state NEW -p tcp --dport 80 -j ACCEPT
    
    # HTTPS: 443
    sudo iptables -I INPUT 6 -m state --state NEW -p tcp --dport 443 -j ACCEPT
    
    # Speichert die Einstellungen dauerhaft
    sudo netfilter-persistent save

## Installiert Certbot und fordert ein TLS Zertifikat für eure Domain an:

    $ sudo apt -y install certbot
    $ sudo mkdir -p /var/lib/letsencrypt/

Certbot bittet um Zustimmung zu den (obligatorischen) Nutzungsbedingungen von Let's Encrypt und bietet ein Abonnement für eine (optionale) Mailingliste an. Certbot konfiguriert sich so, dass das TLS-Zertifikat automatisch aktualisiert wird.

Für Email setzt ihr eure Mail und FQDN ist eure Domain

    $ sudo certbot certonly --email $EMAIL -d $FQDN --standalone

### Installiert die Pleroma Nginx Konfiguration

    $ sudo cp /opt/pleroma/installation/pleroma.nginx /etc/nginx/sites-available/pleroma.nginx
    $ sudo ln -s /etc/nginx/sites-available/pleroma.nginx /etc/nginx/sites-enabled/pleroma.nginx

### Fügt eure Domainzur eben kopierten Nginx Konfiguration

    $ sudo sed -i "s,example.tld,$FQDN," /etc/nginx/sites-available/pleroma.nginx

### Aktiviert Nginx damit es beim Neustart automatisch gestartet wird:

    $ sudo systemctl enable --now nginx.service

### Installiert die systemd Servicedatei:

    $ sudo cp /opt/pleroma/installation/pleroma.service /etc/systemd/system/pleroma.service

### Aktiviert auch Pleroma damit es beim Neustart automatisch startet:

    $ sudo systemctl enable --now pleroma.service

### Erstellt einen Pleroma Administrator:

    $ sudo -Hu pleroma MIX_ENV=prod mix pleroma.user new $USER $EMAIL --admin

Das System zeigt euch am Ende eine URL die ihr im Browser aufrufen könnt, damit ihr euer Passwort für den Admin User setzen könnt.

## Letzte Schritte

Wenn ihr das Passwort für euren Admin gesetzt habt, klickt ihr auf "Homepage" und landet auf der Startseite eures neuen Pleroma Mastodon Fediverse Servers.

Loggt euch mit dem sername/password ein und klickt das "Administration" Menü indem ihr auf das Tacho-Symbol rechts oben klickt. 
![Pleroma Login Seite](__GHOST_URL__/content/images/2024/05/Bildschirmfoto-2024-05-02-um-20.28.47.png)Pleroma Login Seite
Wählen Sie im linken Bereich „Einstellungen“ und dann „Instanz“. Scrollen Sie nach unten und ändern Sie die Einstellung „Registrierungen geöffnet“, um öffentliche Benutzerregistrierungen und Statusbeiträge zuzulassen (die Standardauswahl) oder abzulehnen, und legen Sie die anderen Optionen entsprechend fest. Ändern Sie die Einstellung „Föderieren“, um Verbindungen zu anderen Servern im Fediverse zuzulassen (Standard) oder abzulehnen. 

## Weiteres

Weiterreichende Informationen wie man einen Pleroma server administriert findet ihr im [in der offiziellen Dokumentation](https://docs.pleroma.social/backend/).

---

## Glossar

- **Erlang** ist eine Programmiersprache, die bei Ericsson von Joe Armstrong und anderen entwickelt wurde. Es handelt sich dabei um eine Middleware für den Bau verteilter, hochverfügbarer Systeme. Hervorzuheben sind z. B. die verteilten Datenbanken Mnesia und CouchDB.
