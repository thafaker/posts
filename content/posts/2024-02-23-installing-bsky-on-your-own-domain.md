---
title: "Installing BSKY on your own Domain - Selfhosting: eigene Bluesky Instanz betreiben"
slug: installing-bsky-on-your-own-domain
date_published: 2024-02-23T07:40:02.000Z
date_updated: 2024-03-27T12:34:36.000Z
tags: bsky, bluesky, social media, anleitung, howto, how to, update
excerpt: Wie installiere ich mir eine eigene offizielle Bluesky Instanz (PDS) auf Ubuntu 22.04 mit eigener Domain und nehme am föderierten Netzwerk Bluesky teil.
---

In diesem Schnipsel möchte ich kurz umreißen, wie ihr die seid gestern verfügbare Option, eine eigene Bluskey-Instanz zu betreiben, angehen könnt. Dazu erstellen wir uns einen PDS mit eigener Domain. PDS bedeutet *Personal Data Server*.
[

Bluesky: An Open Social Web - Bluesky

We’re excited to announce that the Bluesky network is federating and opening up in a way that allows you to host your own data.

![](https://bsky.social/about/images/apple-touch-icon.png)Bluesky

![](https://bsky.social/about/images/social-card-default-gradient.png)
](https://bsky.social/about/blog/02-22-2024-open-social-web)
### Was brauchen wir?

Die BSKY Developer haben sehr viel Vorarbeit geleistet, allerdings bezieht sich deren offizielle Dokumentation nur auf Ubuntu 22.04., was ich aus ressourcensicht sehr gut verstehen kann. Sicher funktioniert das auf anderen Linux-Distributionen ähnlich, aber muss angepasst werden. 

Was wir für unsere BSKY Instanz benötigen
AnforderungInhaltOperating SystemUbuntu 22.04Memory (RAM)2+ GB RAMCPU Cores2+ KerneSpeicher40+ GB schnelle SSDArchitekturamd64, arm64
Ich habe auf meinem Server nur 1 GB Ram (1GB Swap) und es funktioniert dennoch problemlos.

Die Jungs stellen ein Installer-Script zur Verfügung, was im besten Falle einfach ausgeführt werden muss - fertig 😄

#### Voraussetzungen

- Linux Server mit Ubuntu 22.04 und Root Access (Liste oben)
- Domain mit gültigem DNS die zu diesem Server führt, Port 443 und Port 80 offen
- Das wars auch schon

### How To Anleitung BSKY als eigene Instanz (PDS)

💡

Wir gehen davon aus dass ihr eure Domain bereits mit eurem Server verbunden habt. Aktuell ist ein wichtiger erster Schritt nötig, ihr müsst eure Domain auf dem [Discord-Kanal von BSKY](https://discord.gg/UWS6FFdhMe) anmelden, damit das funktioniert. Es sind keine großen Server mit mehreren Tausend Usern erlaubt, sondern die Zugriffe und Verbindungen sind beschränkt. 

- Meldet euch also beim [Discord-Server](https://discord.gg/UWS6FFdhMe) an und eröffnet bei BSKY ein Ticket, dort tragt ihr eure Domain ein. Dadurch meldet ihr, dass ihr eine eigene Instanz betreiben wollt und dürft föderieren.

![Domain eintragen BSKY für PDS Request](__GHOST_URL__/content/images/2024/02/Bildschirmfoto-2024-02-23-um-08.15.48.png)Domain eintragen BSKY für PDS Request![](__GHOST_URL__/content/images/2024/02/Bildschirmfoto-2024-02-23-um-19.46.10.png)Ticket accepted
Wenn ihr das erledigt habt, können wir uns auf unseren Linux-Server verbinden und BSKY installieren. Das ganze Ding kommt in einem Docker-Image. Alles was nötig ist, wird durch das Installer-Script installiert.

1. Loggt euch auf eurem Linux-Server via SHH ein
2. Im nächsten Schritt öffnen wir in unserer Firewall die Ports nach draußen (IPTables), der letzte Befehl speichert die temporären Einstellen Einstellungen dauerhaft. (Achtet darauf, dass ihr auch die Ports in eurer Cloud-Instanz zulassen müsst, bei mir Oracle in seiner Management-Console. Das ist aber von Anbieter zu Anbieter unterschiedlich):

    # HTTP :80
    sudo iptables -I INPUT 6 -m state --state NEW -p tcp --dport 80 -j ACCEPT
    
    # HTTPS : 443
    sudo iptables -I INPUT 6 -m state --state NEW -p tcp --dport 443 -j ACCEPT
    
    # Speichert die Settings mit folgendem Befehl
    sudo netfilter-persistent save

1. Nutzt ihr die andere große Firewall, **UFW**, dann lauten die Befehle folgendermaßen:

    # HTTP: 80
    sudo ufw allow 80
    
    # HTTPS: 443
    sudo ufw allow 443
    
    # Nachdem man einen Port in UFW geöffnet hat, sollte man sicher gehen, dass UFW auch an ist:
    sudo ufw enable

1. Wechselt in euer Home-Verzeichnis (oder /tmp) und ladet euch den BSKY Installer herunter:

    wget https://raw.githubusercontent.com/bluesky-social/pds/main/installer.sh

1. Startet den Installer, dafür benötigt ihr Root-Rechte:

    sudo bash installer.sh

1. Der Installer fragt euch nach eurer Domain und nach eurer Mail und beginnt dann mit der Installation. Er aktualisiert zunächst via APT das System und installiert ggf. benötigte Komponenten, dann lädt er das Docker-Image und startet es:

    ~/bsky$ sudo bash installer.sh
    * Detected supported distribution Ubuntu 22.04 LTS
    
    ---------------------------------------
         Add DNS Record for Public IP
    ---------------------------------------
    
      From your DNS provider's control panel, create the required
      DNS record with the value of your server's public IP address.
    
      + Any DNS name that can be resolved on the public internet will work.
      + Replace example.com below with any valid domain name you control.
      + A TTL of 600 seconds (10 minutes) is recommended.
    
      Example DNS record:
    
        NAME                TYPE   VALUE
        ----                ----   -----
        example.com         A      Server's IP
        *.example.com       A      Server's IP
    
      **IMPORTANT**
      It's recommended to wait 3-5 minutes after creating a new DNS record
      before attempting to use it. This will allow time for the DNS record
      to be fully updated.
    
    Enter your public DNS address (e.g. example.com): WurstGesicht.de

1. Danach solltet ihr folgendes sehen:

    ========================================================================
    PDS installation successful!
    ------------------------------------------------------------------------
    
    Check service status      : sudo systemctl status pds
    Watch service logs        : sudo docker logs -f pds
    Backup service data       : /pds
    PDS Admin command         : pdsadmin
    
    Required Firewall Ports
    ------------------------------------------------------------------------
    Service                Direction  Port   Protocol  Source
    -------                ---------  ----   --------  ----------------------
    HTTP TLS verification  Inbound    80     TCP       Any
    HTTP Control Panel     Inbound    443    TCP       Any
    
    Required DNS entries
    ------------------------------------------------------------------------
    Name                         Type       Value
    -------                      ---------  ---------------
    WurstGesicht.de              A          Server's IP
    *.Wurstgesicht.de            A          Server's IP
    
    Detected public IP of this server: Server's IP
    
    To see pdsadmin commands, run "pdsadmin help"
    
    ========================================================================
    Create a PDS user account? (y/N): y
    Enter an email address (e.g. alice@WurstGesicht.de): th@WurstGesicht.de
    Enter a handle (e.g. alice.Wurstgesicht.de): thahipster.Wurstgesicht.de

1. Das wars schon, der Server ist installiert und sofern ihr eure Domain verbunden habt, bereits erreichbar. 
2. Ihr habt einen Account angelegt, könnt aber einen weiteren Account mit folgendem Befehl erstellen:

    sudo pdsadmin account create

1. Nun müsst ihr noch euren DNS-Record veryfien, wie das geht sagt euch die folgende Seite. Kurzum, ihr müsst eurem DNS Record noch einen Eintrag hinzufügen, damit die Domain von BSKY federated werden kann.
[https://bsky-debug.app/handle (archiviert)](http://web.archive.org/web/20240229223500/https://bsky-debug.app/handle)
2. Ende

### Benutzt Bluesky

Ihr könnt die bekannten Wege nutzen, um euch mit eurer Bluesky Instanz (PDS) zu verbinden.

1. Verbindet euch über die folgenden Wege:
- Auf der [Bluesky Webseite (archiviert)](http://web.archive.org/web/20240224000532/https://bsky.app/) einloggen
- App iPhone laden: [Bluesky für iPhone](https://apps.apple.com/us/app/bluesky-social/id6444370199)
- App Android laden: [Bluesky für Android](https://play.google.com/store/apps/details?id=xyz.blueskyweb.app)

2. Gebt in der Konfiguration die URL eurer Instanz ein (z.B. `https://WurstGesicht.de/`)
3. Ende

*Easy, oder*?

### Update eures PDS

Falls ihr aktualisieren wollt, gebt ihr im Terminal eurer Linux-Instanz folgenden Befehl ein:

    sudo pdsadmin update

### Ressourcen
[

GitHub - bluesky-social/pds: Bluesky PDS (Personal Data Server) container image, compose file, and documentation

Bluesky PDS (Personal Data Server) container image, compose file, and documentation - bluesky-social/pds

![](https://github.githubassets.com/assets/pinned-octocat-093da3e6fa40.svg)GitHubbluesky-social

![](https://opengraph.githubassets.com/ac28d3a7d0af0fde79e8095d0c81a2a2cdcf48b2b2f6293c7ac1d5acadc538ba/bluesky-social/pds)
](https://github.com/bluesky-social/pds?tab=readme-ov-file)[

Bluesky Guide (@bluesky-tipps.bsky.social)

Das ist übrigens auch ein wichtiger Unterschied zwischen Bluesky und Mastodon: Wenn man auf einen anderen Personal Data Server (PDS) umzieht, kann man sein Handle behalten. Und man kann sein Handle ändern, ohne dass sich das auf den eigenen sozialen Graphen auswirkt.

![](https://bsky.app/static/apple-touch-icon.png)Bluesky Social

](https://bsky.app/profile/bluesky-tipps.bsky.social/post/3kkvmvvt6zn2u)
