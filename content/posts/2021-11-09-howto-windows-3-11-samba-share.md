---
title: HowTo Windows 3.11 with actual Samba 4 Share - Vintage Computing
slug: howto-windows-3-11-samba-share
date_published: 2021-11-09T17:41:39.000Z
date_updated: 2023-01-21T13:43:31.000Z
tags: vintage computing, anleitung, howto, how to
excerpt: HowTo Windows 3.11 with actual Samba 4 Share - Vintage Computing
---

Ich betreibe gern [Vintage Computing](__GHOST_URL__/tag/vintage-computing/) und so trug es sich zu, dass ich einen schönen **Compaq 486er** mit 32 MB-Ram und einer ISA-Netzwerkkarte, einer Soundkarte und natürlich einer IDE-CF-Karte versehen habe und diesen mit DOS-Spielen *retrogame*. Weiterhin habe ich Windows 3.11 (WfW) installiert und dort sämtliche Rafinessen betrieben, ihn online zu kriegen. Das klappt sogar sehr gut. Neben Netscape tummelt sich auch ein Internet Explorer 5 und ein Opera 3.62 für das Interwebs, aber auch FTP und selbstverständlich mIRC :) 

Grund genug also eine Urtugend von Windows, nämlich Netzwerkfreigaben, zu nutzen. Ich habe einen kleinen ARM-Server (Utilite Pro, 7-Watt Device) auf dem ein Ubuntu 20.04 LTS läuft und viele Dienste für den Retro-Rechner im netzwerk verfügbar macht. Warum also nicht auch Samba? Genau!
![Original Screenshot: Win 3.11 with Samba Share Dateimanager und verbundenem Samba-Share](__GHOST_URL__/content/images/2021/11/NETZ4-1.JPG)Original Screenshot: Win 3.11 with Samba Share Dateimanager und verbundenem Samba-Share
Aber das ist gar nicht so einfach, denn natürlich sprechen aktuelle Windowsen und auch das aktuelle Samba eine ganz andere technische Sprache mit ausgereifteren Sicherheitsmechanismen die ein Windows 3.11, ein Windows 95/98 und selbst ein XP ausschließen. Man muss also etwas umbiegen um das Sicherheitsniveau seines Samba-Servers soweit herunter zu schrauben, dass er eine so unsichere Verbindung wie die von Windows 3.11 akzeptiert. Nach diversen unterschiedlichen Probeläufen und wenig Erfolg ist es folgende Samba.config, die mich nun zum Ziel führte.

## HowTo Samba Windows 3.11 WfW

Wir bearbeiten also die **smb.conf** unseres Linux-Servers und fügen folgende Konfigurationszeilen oben unter GLOBAL ein:

*sudo nano /etc/samba/smb.conf*

    [global]
    
       	workgroup = WORKGROUP
       	client min protocol = NT1
       	server string = Samba
       	netbios name = utilite
    	lanman auth = yes
    	client lanman auth = yes
    	ntlm auth = yes
    	client min protocol = core
    	server min protocol = core
    	client plaintext auth = Yes

Das sorgt dafür dass ich mich connecten kann und die Shares im [Dateimanager](https://de.wikipedia.org/wiki/Datei-Manager_(Windows)) unter *Netzlaufwerk einbinden* in Windows 3.11 auftauchen. Wichtig ist nun, ein Verzeichnis auf dem Server freizugeben. Folgend mein Share, es ist das Public-Verzeichnis auf dem Server.

    [public]
       path = /path/to/share
       public = yes
       only guest = yes
       writable = yes
       printable = no
       case sensitive = no
       default case = upper
       preserve case = no
       short preserve case = no
    #  mangle case = yes
    #  mangled names= yes
       valid users = compaq

Damit konnte ich das Netzlaufwerk unter Windows 3.11 einbinden und fortan darauf zugreifen, wie man das eben so kennt. Es steht im Dateimanager zur Verfügung und ich kann prima Daten austauschen. Die Screenshots habe ich auf dem Vintage PC direkt gemacht, via Paint Shop Pro als *.jpg gespeichert und mir per Mail gesendet - und selbstverständlich auch auf dem Netzlaufwerk abgelegt - weils geht :)
![Original Screenshot: Win 3.11 with Samba Share Dateimanager](__GHOST_URL__/content/images/2021/11/NETZ1.JPG)Original Screenshot: Win 3.11 with Samba Share Dateimanager
**Was noch wichtig ist**:

- Samba Benutzer auf dem Linux-Server anlegen, er braucht zugriff auf das Public Verzeichnis, identisch zum Win3.11 Nutzer, Kennwort nicht länger als 8 Zeichen
- Windows 3.11 netzwerkfähig machen, also TCP/IP installieren ([hier ein HowTo](__GHOST_URL__/netzwerken-unter-dos/) aber nur für Networking unter DOS)

![Original Screenshot: Win 3.11 with Samba Share Dateimanager](__GHOST_URL__/content/images/2021/11/NETZ2.JPG)Original Screenshot: Win 3.11 with Samba Share Dateimanager
Diese Anleitung ist nicht sonderlich gut und erst recht nicht korrekt, aber ich hoffe sie hilft auf die Sprünge wenn eine Verbindung mit Windows 3.11 und Samba nicht zustande kommen will und meine smb.conf hilft. Anregungen gern in die Kommentare.

*Viel Spaß am Gerät.*
