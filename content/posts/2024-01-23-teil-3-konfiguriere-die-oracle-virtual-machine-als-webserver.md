---
title: Teil 3 - Konfiguriere die Oracle Virtual Machine als Webserver
slug: teil-3-konfiguriere-die-oracle-virtual-machine-als-webserver
date_published: 2024-01-23T06:19:58.000Z
date_updated: 2024-02-01T20:18:02.000Z
tags: nginx, lubuntu, oracle cloud, ghost, anleitung, how to, howto
excerpt: Teil 3 - Ich werde in dieser Blogreihe darüber berichten wie man sich bei Oracle Cloud registriert, eine kostenlose Instanz klickt, die Virtuelle Maschine startet, diese Maschine als Webserver konfiguriert und letztendlich Ghost nebst Datenbank installiert.
---

Ich werde in dieser **Blogreihe** darüber berichten wie man sich bei Oracle Cloud registriert, eine kostenlose Instanz klickt, die Virtuelle Maschine startet, diese Maschine als Webserver konfiguriert und letztendlich Ghost nebst Datenbank installiert.

## Table of Contents

- [Teil 1 - Einrichten eines Accounts bei Oracle Cloud](__GHOST_URL__/wie-man-sich-kostenlos-zwei-virtuelle-server-instanzen-mit-ubuntu-22-04-klickt-und-betreibt/)
- [Teil 2 - Hochfahren einer Oracle Virtual Machine](__GHOST_URL__/teil-2-hochfahren-einer-oracle-virtual-machine/)
- **Teil 3 - Konfiguriere die Oracle Virtual Machine als Webserver**
- [Teil 4 - Installiere Ghost CMS](__GHOST_URL__/teil-4-installiere-ghost-cms-auf-oracle-cloud-always-free-instanz/)

---

**Teil 3 - Konfiguriere die Oracle Virtual Machine als Webserver**

SSH in eure Oracle Virtual Machine und lasst uns NGINX, MySQL und Node.js installieren. Für das aktuelle Ghost benötigen wir ein neueres NodeJS als es Ubuntu in 22.04 zur Verfügung stellt, deshalb binden wir eine externe Paketquelle ein und installieren 18.X:

    # Install NGINX
    sudo apt-get install nginx
    
    # Install MySQL
    sudo apt-get install mysql-server
    
    # Add the NodeSource APT repository for Node 18
    curl -sL https://deb.nodesource.com/setup_18.x | sudo -E bash
    
    # Install Node.js
    sudo apt-get install -y nodejs
    

---

Im nächsten Schritt öffnen wir in unserer Firewall die Ports nach draußen (IPTables), der letzte Befehl speichert die temporären Einstellen Einstellungen dauerhaft (den Port für Mail brauchen wir eigentlich nicht, wir können ohne Konfiguration eines Mailservers so ohnehin keine Mails versenden):

    # HTTP :80
    sudo iptables -I INPUT 6 -m state --state NEW -p tcp --dport 80 -j ACCEPT
    
    # HTTPS : 443
    sudo iptables -I INPUT 6 -m state --state NEW -p tcp --dport 443 -j ACCEPT
    
    # MAIL :587
    sudo iptables -I INPUT 6 -m state --state NEW -p tcp --dport 587 -j ACCEPT
    
    # Save the settings
    sudo netfilter-persistent save
    

---

💡

**Jetzt müssen wir zurück in unser Oracle Cloud Dashboard um dort eine INGRESS-Regel zu erstellen, welche den Verkehr in unserem virtuellen Netzwerk (VCN) in der Cloud Instanz erlaubt!**

Gehe zum **Cloud-Dashboard** zurück auf cloud.oracle.com, öffne „Netzwerk“ und wähle dann „Virtuelle Cloud-Netzwerke“ aus.
![Oracle Cloud Dashboard Virtuelle Netzwerke](__GHOST_URL__/content/images/2024/02/Bildschirmfoto-2024-02-01-um-21.17.12.png)Oracle Cloud Dashboard Virtuelle Netzwerke
- Wähle das „Virtual Cloud Network Name“ (meiner ist vcn-20240117-0841). Anklicken.
- Wählen den „Subnetznamen“ (subnet-324234). Anklicken.
- Wähle die „Sicherheitsliste“ (Default Security List for…) aus. 
- Von hier aus können wir unsere VCN Eingangs-/Ausgangsregeln verwalten. 
- Wähle die Schaltfläche „Ingress-Regeln hinzufügen“.

![](__GHOST_URL__/content/images/2024/01/Bildschirmfoto-2024-01-22-um-16.48.24.png)
Wir müssen **drei** neue Ingress-Regeln hinzufügen, weil wir drei Ports öffnen wollen.

1. HTTP port 80
2. HTTPS port 443
3. MAIL port 587

Das ganze wiederholen wir für die anderen beiden Ports ebenfalls. Quell-CIDR lautet: 0.0.0.0/0 (im Screenshot habe ich mich vertippt) und öffnen den Port komplett. Quellport / Zielport ist der Port der Anwendung, also 80, 443 oder 587.
![Innres Regel 1: Port 80 wird geöffnet](__GHOST_URL__/content/images/2024/01/Bildschirmfoto-2024-01-22-um-16.50.36.png)Innres Regel 1: Port 80 wird geöffnet
---

**Überprüfen wir, ob die NGINX-Platzhalterseite aktiv ist**

Öffne einen Browser und lade die Seite http://{YourVMPublicIP}. Daraufhin sollte „Welcome to nginx!“ angezeigt werden. Unser NGINX-Server läuft also.

Herzlichen Glückwunsch, wir haben jetzt einen für immer kostenlosen Ubuntu-Webserver in der Oracle Cloud, auf dem wir mit 200 GB kostenloser Festplatte alles was unter Ubuntu läuft, auch hosten können! z.B. Ghost.

---

*Hier geht es nun weiter*...

[**Teil 4 - Installiere Ghost CMS**](__GHOST_URL__/teil-4-installiere-ghost-cms-auf-oracle-cloud-always-free-instanz/)
[

Teil 4 - Installiere Ghost CMS auf Oracle Cloud always Free Instanz

Teil 4 - Ich werde in dieser Blogreihe darüber berichten wie man sich bei Oracle Cloud registriert, eine kostenlose Instanz klickt, die Virtuelle Maschine startet, diese Maschine als Webserver konfiguriert und letztendlich Ghost nebst Datenbank installiert.

![](__GHOST_URL__/content/images/size/w256h256/2019/06/logo.png)thahipster.deHerr Montag

![](__GHOST_URL__/content/images/2024/01/Bildschirmfoto-2024-01-16-um-09.56.55-1.png)
](__GHOST_URL__/teil-4-installiere-ghost-cms-auf-oracle-cloud-always-free-instanz/)
