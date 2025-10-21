---
title: Netzwerken unter MS-DOS und Derivaten
slug: netzwerken-unter-dos
date_published: 2020-09-25T14:13:56.000Z
date_updated: 2024-01-29T13:58:54.000Z
tags: dos 6.22, freedos, networking, netzwerk, vintage computing, retro computing, retro, ms-dos
---

Da ich mich in meiner Freizeit ja hin und wieder mit alten Computern beschäftige, treten hierbei ab und an auch ein paar neue Erkenntnisse zu Tage, die ich nicht verheimlichen möchte. Neulich war es [USB](__GHOST_URL__/usb-support-unter-ms-dos/), was ich unter DOS einbinden und einen USB-Stick damit ansteuern konnte. Das ist super praktisch, weil man so ganz gut große und kleine Daten mit einem anderen Computer austauschen kann.

Und heute möchte ich beschreiben, wie ich mit diesem Notebook und einer Kabel-Verbindung online gegangen bin. Genutzt habe ich diesmal nicht MS-DOS 6.22, sondern vielmehr dessen neues und freies Pendant, **FreeDOS 1.3 RC 2**, welches man [hier](http://www.ibiblio.org/pub/micro/pc-stuff/freedos/files/distributions/1.3/previews/1.3-rc3/) beziehen kann. FreeDOS bringt neben dem eigentlichen Kernel noch viele weitere coole Dinge mit, aber leider keinen *386 enhanced Mode* ([?](https://www.brainbell.com/tutors/A+/Hardware/Windows_NT.htm)), sodass **Windows 3.11***Windows for Workgroup*s (WfW) nicht läuft. *Schade*. Aber das braucht man für Networking unter DOS ohnehin nicht, bringt es seinen eigenen Stack mit. Ich habe für meine Zwecke die *FD13LGCY.ISO* genutzt. [FreeDOS 1.3 RC3](http://www.ibiblio.org/pub/micro/pc-stuff/freedos/files/distributions/1.3/previews/1.3-rc3/) wird in folgenden Formaten angeboten:

1. FD13FLOP.IMG - Basic FreeDOS installation boot Disketten image. (Minimal)
2. FD13LITE.IMG - Plain DOS system only! USB stick image. (auch für VMWare)
3. FD13FULL.IMG - Plain DOS system und Full install USB stick image. (auch für VMWare)
4. FD13LGCY.ISO -Beinhaltet alle Pakete wie auch FD13-FullUSB. Allerdings ist es das Image für alte Hardware, also genau das richtige für uns.
5. FD13LIVE.ISO - FreeDOS LiveCD

#### Was es braucht?

- Einen echten DOS-Computer, ich habe ein Pentium II Notebook verwendet
- Einen virtuellen PC und ein USB-Diskettenlaufwerk, um wichtige Daten auf Diskette zu bringen und sie aus dem Netz laden zu können
- Eine passende PCMCIA Netzwerk-Karte. Hier gibt es große unterschiede zwischen 16 und 32-Bit Karten. Ich nutze für DOS eine 16-Bit-Karte, und zwar folgende:
- Xircom 10/100 Creditcard Ethernet PCMCIA Netzwerkkarte
- Das passende [Xircom Treiber Paket](ftp://thafaker.crabdance.com/network/xircom/Xircom.zip) (5 MB) mit Treibern von DOS bis Windows 2000.

![Xircom CreditCard Ethernet 10/100 16-Bit PCMCIA Netzwerk Karte](__GHOST_URL__/content/images/2020/09/xircom.jpg)Xircom CreditCard Ethernet 10/100 16-Bit PCMCIA Netzwerk Karte
### Networking with MS-DOS, FreeDOS

Wir gehen von einer funktionierenden Installation von FreeDOS aus. Das System bootet und wir befinden uns im Prompt c:\>

#### Packet-Driver 

Wichtig ist, dass es zur Netzwerkkarte einen sogenannten Paket-Treiber gibt, Packet-Driver. Dies ist meist eine COM-Datei und hat PD im Namen, bei mir ist es der Dateiname XE3PD.COM und befindet sich im oben verlinkten Treiberpaket. Dieser wird beim Booting in der autoexec.bat geladen. Bei Aufruf erkennt der Treiber ohne weiteres zutun die PCMCIA-Netzwerkkarte, gibt ihr einen IRQ und startet sie. Ab jetzt steht sie jeder DOS-Anwendung, die auf einen solchen Treiber zugreifen kann, zur Verfügung. Er residiert meist in einem speziellen Speicherbereich, 0x60 und wird so durch die meisten Programme gefunden.

### WATTCP - Netzwerkstack

Waterloo TCP (WatTCP) wurde von 1990 bis 1992 an der University of Waterloo in Ontario (Kanada) geschrieben. Der Autor ist **Erick Engelke** ([private Website](http://www.erickengelke.com/)), damals Entwickler an der Fakultät für Ingenieurwissenschaften, später Direktor für Ingenieurwesen der Universität, mittlerweile emeritiert. Die Kern-TCP-Engine von WatTCP basierte auf TinyTCP von Geoffrey H. Cooper.

WatTCP können Entwickler in Ihre Software integrieren und so eine Netzwerkschnittstelle bereit stellen, der Endbenutzer muss praktisch nur noch mitteilen, wie seine Konfiguration aussieht. Das einzige was getan werden muss, ist eine Datei namens "`WATTCP.CFG`" anzupassen. Diese liegt meist im Order der gewünschten Software.

So sieht meine `wattcp.cfg` Datei aus:

> --- WATTCP.CFG ---
> my_ip = 192.168.2.2
> netmask = 255.255.255.0
> nameserver = 192.168.178.169
> gateway = 192.168.2.1

Wie ihr seht könnte ihr my_ip auskommentieren um es via DHCP zu konfigurieren. Man kann nun den Pfad zur WATTCP.CFG auch systemweit angeben, in dem man dies über die `Autoexec.bat` kund tut: `WATTCP.CFG=\Pfad\zur\Datei`

Zeit, eine Software zu starten, die WATTCP unterstützt. Hier bietet sich meiner Meinung nach ein großartiger Browser für DOS an, nämlich **Arachne**! Downloaden kann man ihn in der Version *1.97GPL*[[hier](http://glennmcc.org/arachne/)](http://glennmcc.org/). 
![Screenshot of Arachne displaying MediaWiki's home page using VESA 800x600x16 mode.](__GHOST_URL__/content/images/2020/09/Arachne_VESA_Mode.png)Screenshot of [Arachne](https://en.wikipedia.org/wiki/en:Arachne_(web_browser)) displaying [MediaWiki's](https://en.wikipedia.org/wiki/en:MediaWiki) home page using [VESA](https://en.wikipedia.org/wiki/en:VESA) 800x600x16 mode.
Der Browser verfügt auch über eine eigens eingebaute, mächtige Konfiguration, aber diese ist an für unsere Belange nicht notwendig. Wir editieren die wattcp.cfg die wir im Verzeichnis von  Arachne finden, starten Arachne und *there we go…*

Work in progress…
