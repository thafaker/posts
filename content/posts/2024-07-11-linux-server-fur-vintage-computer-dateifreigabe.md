---
title: Dateifreigaben und Netzlaufwerke für Vintage Computer
slug: linux-server-fur-vintage-computer-dateifreigabe
date_published: 2024-07-11T09:51:05.000Z
date_updated: 2024-08-16T05:56:27.000Z
tags: anleitung, how to, howto, retronas, linux, vintage computing
---

Ich betreibe in meinem kleinen Vintage Computer Park neben einem Amiga 1200 und Amiga 500+ auch einen PC mit MS-DOS 6.22 (und Windows 3.11) sowie aktuell auch einen iMac G3 Fruit Color (333 MHz), den ich sehr mag. Die letzten beiden Geräte können prima auch Dateifreigaben, allerdings in sehr alter Form. Heutige Windows Versionen kommen mit den unverschlüsselten Freigaben nicht mehr zurecht und so gibt es hier keinen Weg.

![](__GHOST_URL__/content/images/2024/07/IMG_2022.jpg)

![](__GHOST_URL__/content/images/2024/07/s-l1600-10.jpg)

![](__GHOST_URL__/content/images/2024/07/photo-1661793422654-95210ec02652.jpeg)

![](__GHOST_URL__/content/images/2024/07/photo-1661793422829-e1f648ab4a15.jpeg)

Verschiedene Vintage Computer. o.l.: Compaq ProLinea 433; WISE Terminal; Amiga 1200; Amiga 1200

Allerdings gibt es mit Samba und verschiedenen Projekten doch Möglichkeiten, die alten Netzwerk-Funktionen zu nutzen, was neben dem spielerischen Aspekt oft sehr hilfreich sein kann. **RetroNAS **ist also eine Software, die es ermöglicht, alte Computer mit modernen Netzwerken zu verbinden und Retro-Computing zu erleichtern. In dieser Anleitung lege ich Ubuntu 22.04 zu Grunde, aber das funktioniert mit etwas Änderung so auch auf jedem anderen Unices.

## How To RetroNAS Ubuntu Vintage Networking Retro Networking

### Schritt 1: System vorbereiten

1. Aktualisiere dein System:

    sudo apt update
    sudo apt upgrade -y

1. Installiere benötigte Pakete:

    sudo apt install git build-essential python3 python3-pip samba cifs-utils
    

### Schritt 2: RetroNAS herunterladen und installieren

1. Clone das RetroNAS Repository:

    git clone https://github.com/danmons/RetroNAS.git

1. Wechsel in das RetroNAS-Verzeichnis:

    cd RetroNAS

1. Installiere RetroNAS mit dem Installer-Script

    ./install.sh
    
    oder
    
    sh install.sh

Dieser Schritt kann einige Zeit in Anspruch nehmen, da er alle notwendigen Abhängigkeiten installiert und konfiguriert.

### Schritt 3: Konfiguration von RetroNAS

1. Starte das RetroNAS Setup Script:

    sudo ./retronas-setup.sh
    

Folge den Anweisungen auf dem Bildschirm, um die Konfiguration abzuschließen. Hier kannst du verschiedene Optionen wählen, um RetroNAS an deine Bedürfnisse anzupassen.

#### 2. Menüoptionen im Setup-Skript

Das Setup-Skript bietet verschiedene Optionen zur Konfiguration. Dieses Skript startet ein interaktives Setup-Tool. Du wirst durch eine Reihe von Menüs und Optionen geführt, die dir helfen, RetroNAS zu konfigurieren.

Hier sind die wichtigsten Menüpunkte, die du durchgehen solltest:

##### a. **Netzwerkfreigaben konfigurieren**

- **SMB/CIFS (Samba):** Damit kannst du Netzwerkfreigaben für Windows und macOS erstellen.
- **NFS:** Einrichten von NFS-Freigaben für UNIX/Linux-Systeme.
- **FTP:** Konfigurieren eines FTP-Servers für den Zugriff auf deine Dateien.
- **RSYNC:** Einrichten von RSYNC für Dateiübertragungen und Backups.

##### b. **Benutzer und Berechtigungen**

- Erstelle und verwalte Benutzerkonten, um den Zugriff auf deine Freigaben zu steuern.
- Setze Berechtigungen für die verschiedenen Freigaben, um sicherzustellen, dass nur autorisierte Benutzer Zugriff haben.

##### c. **Dateisysteme und Speicherorte**

- Wähle die Verzeichnisse und Dateisysteme aus, die du freigeben möchtest.
- Konfiguriere Speicherorte für RetroNAS-Daten und -Backups.

##### d. **Dienstkonfiguration**

- Aktiviere oder deaktiviere verschiedene Dienste (SMB, NFS, FTP, RSYNC) je nach deinen Bedürfnissen.
- Konfiguriere spezifische Einstellungen für jeden Dienst (z.B. Portnummern, Verzeichnisse, etc.).

##### e. **Systemeinstellungen**

- Konfiguriere allgemeine Systemeinstellungen wie Netzwerkverbindungen, Hostnamen und Firewall-Regeln.

### Schritt 4: Netzwerkfreigabe einrichten

1. Konfiguriere Samba für die Netzwerkfreigabe:Öffne die Samba-Konfigurationsdatei:

    sudo nano /etc/samba/smb.conf

Füge am Ende der Datei die folgende Konfiguration hinzu, um einen neuen Freigabeordner zu erstellen, ich hatte an [dieser Stelle schon mal asführlicher über Samba und Windows 3.11 Netzwerkfreigaben](__GHOST_URL__/howto-windows-3-11-samba-share/) berichtet:

    [RetroNAS]
    path = /path/to/retronas
    available = yes
    valid users = @users
    read only = no
    browsable = yes
    public = yes
    writable = yes

Ersetze `/path/to/retronas` durch den Pfad zu deinem RetroNAS-Verzeichnis.

1. Erstelle den Freigabeordner:

    sudo mkdir -p /path/to/retronas
    sudo chown -R nobody:nogroup /path/to/retronas
    sudo chmod -R 0777 /path/to/retronas

1. Samba neu starten

    sudo systemctl restart smbd

### Schritt 5: Verbindung zum Netzwerk herstellen

1. **Verbinde deinen iMac G3 oder PC mit Windows 3.11 mit dem Netzwerk. **
Auf dem iMac G3 kannst du das Netzwerk über die Systemeinstellungen konfigurieren. Bei Windows 3.11 musst du den Netzwerk-Client installieren und konfigurieren.
2. **Greife auf die RetroNAS-Freigabe zu:**
Verwende die Netzwerkfunktionalität des jeweiligen Systems, um auf die freigegebenen Ordner zuzugreifen. Beispielsweise kannst du bei Windows 3.11 die Netzwerkumgebung verwenden oder beim iMac G3 das Netzwerk-Laufwerk verbinden.

### Optional: Weitere Dienste einrichten

RetroNAS unterstützt auch andere Protokolle und Dienste wie FTP, NFS, oder RSYNC, um die Kompatibilität mit verschiedenen Retro-Computern zu verbessern. Diese kannst du über das RetroNAS Setup Script konfigurieren.

Ihr solltet jetzt ein funktionierenden Dateiserver haben, der fast alle alten Protokolle und Einstellungen untersützt, um auch die alten Geräte anbinden zu können. Ich finde es ziemlich praktisch weil ich so ganz einfach Dateien auf den alten Rechner bekomme oder austauschen kann.

*Viel Spaß am Gerät.*
