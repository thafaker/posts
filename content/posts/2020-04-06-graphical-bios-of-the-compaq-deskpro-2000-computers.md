---
title: Graphical BIOS of the vintage Compaq Deskpro 2000 Computers
slug: graphical-bios-of-the-compaq-deskpro-2000-computers
date_published: 2020-04-06T11:13:00.000Z
date_updated: 2024-05-10T18:40:33.000Z
tags: vintage computing, vintage-pc, windows 95, dos 6.22, hardware, bios, compaq deskpro 2000
---

Mein *Vintage Computer* aus der PC-Ära ist ein **Compaq Deskpro 2000**. Der Prozessor ist lüfterlos und auch sonst strotzt der Rechner nur so vom Stand der Business-Technik in den 90er Jahren. Der Pentium ist noch der Vorgänger vom MMX, also der **P54CS** mit 150 Mhz, ziemlich potent also :-) Deskpro 2000 liefen mit Pentium 1, Pentium Pro oder Pentium 2.

Eine Besonderheit dieser Compaqs stellt deren BIOS dar, auf das ich mit diesem kleinen Beitrag kurz eingehen möchte. Es ist nämlich sicher gar nicht so bekannt, dass es in den 90ern solche (benutzerfreundlichen) Lösungen gab. Genau genommen gibt es bei diesen Rechnern kein BIOS-Setup wie man das etwa von AMI oder AWARD her kennt

![Award Bios](https://www.winhistory.de/more/486/bilder/award0.jpg)1990er Jahre Award Bios; ([Link](https://www.winhistory.de/more/486/bilder/award0.jpg))

sondern eine Kombination aus einem festen Teil und einer grafischen Oberfläche. Per Default ist die verbaute Festplatte partitioniert. In einer 6 MB großen NON-DOS Parititon residiert der grafische BIOS Teil, mit welchem man die Einstellungen des Computers, Hardware, IRQ Settings, Festplatten, Bootoptionen einstellen kann. Und der restliche Teil ist eben normales FAT 16 DOS oder vielleicht auch schon FAT 32, je nachdem. Sollte man die kleine Partition löschen so hat man folgich auch keine Möglichkeit mehr, die Einstellungen vorzunehmen. Das BIOS kann dann noch automatisch beim Boot erkennen ob Hardware geändert wurde, beispielsweise bei Einbau einer neuen Festplatte und diese Konfiguration auch speichern, aber viel mehr geht ohne der Partition nicht mehr.

![](__GHOST_URL__/content/images/2020/04/IMG_2335.JPG)

Allerdings stellt Compaq für diesen Fall zwei Disketten zur Verfügung, mit deren Hilfe man die Partition wieder erstellen und die grafische BIOS-Oberfläche wieder installieren kann. Diese Disketten funkgieren praktischerweise als Boot-Disk und bieten auch die BIOS Oberfläche von Diskette an, ganz ohne Installation. So kann man von diesen Disketten booten und folglich doch noch Einstellungen vornehmen, auch wenn die Partition aus irgend einem Grund gelöscht worden sind.

![IMG_2324](__GHOST_URL__/content/images/2020/04/IMG_2324.JPG)

Hier der Download dieser beiden Disketten Images (*.ima):

- [Compaq Diskette 1 SETUP cmpq_setup.IMA.zip](http://thafaker.crabdance.com/grav/news/das-bios-der-compaq-deskpro-computer/cmpq_setup.IMA.zip)
- [Compaq Diskette 2 DIAG cmpq_diag.IMA.zip](http://thafaker.crabdance.com/grav/news/das-bios-der-compaq-deskpro-computer/cmpq_diag.IMA.zip)
- [Diskettensatz für Compaq Deskrpo 2000, 3 Disketten Files](__GHOST_URL__/content/files/2024/05/sp15674.exe)

Um die Dateien wieder zurück auf Diskette schreiben zu können, benötigt man neben einem Diskettenlaufwerk [[1]](#fn1) auch eine Software, die das kann. Ich persönlich nutze **WinImage in der Version 9.0** ([Download Link](http://www.winimage.com/download.htm)) und führe diese in einem alten Windows 2000 in einer VM-Ware aus. Das funktioniert absolut problemlos. Hat man sich diese Disketten erstellt, kann man seinen Compaq wieder richtig in Betrieb nehmen. So sieht das "grafische BIOS" übrigens aus:

![IMG_2324](__GHOST_URL__/content/images/2020/04/IMG_2324.JPG)

![IMG_2325](__GHOST_URL__/content/images/2020/04/IMG_2325.JPG)

![IMG_2326](__GHOST_URL__/content/images/2020/04/IMG_2326.JPG)

![IMG_2327](__GHOST_URL__/content/images/2020/04/IMG_2327.JPG)

![IMG_2328](__GHOST_URL__/content/images/2020/04/IMG_2328.JPG)

![IMG_2329](__GHOST_URL__/content/images/2020/04/IMG_2329.JPG)

![IMG_2330](__GHOST_URL__/content/images/2020/04/IMG_2330.JPG)

![IMG_2331](__GHOST_URL__/content/images/2020/04/IMG_2331.JPG)

![IMG_2332](__GHOST_URL__/content/images/2020/04/IMG_2332.JPG)

![IMG_2335](__GHOST_URL__/content/images/2020/04/IMG_2335.JPG)

Höchst unkonventionell, aber doch auch tatsächlich recht benutzbar. Startet man beim Boot mit F10 dieses Bios, dann lädt zunächst ein DOS Maustreiber bevor dann die Win 3.1 grafische Benutzeroberfläche startet.

![c00327708](__GHOST_URL__/content/images/2020/04/c00327708.jpg)

Es folgen technische Informationen über den **Compaq Deskpro 2000** Computer.
**Prozessoren**Pentium Units100 or 200 MHz Intel Pentium ; Supports 50, 60, and 66 MHz bus frequenciesPentium Pro Units180 or 200 MHz Intel Pentium Pro (P6); Bus speeds: 50, 60, and 66 MHzP55C MMX UnitsPentium MMX 166/200/233MHzPentium II UnitsPentium II 233/266/300MHz Processors**CPU Cache Memory**Pentium UnitsWrite-Back cache; 256KB cache size-select models ; Only supports Pipeline Burst SRAMsPentium Pro UnitsPentium Pro internal L2 cache: 256 KBP55C MMX Units256k L2 down, 256k upgrade to 512k maxPentium II Units512k integrated on Processor Module**Arbeitsspeicher**PentiumEDO and fast page mode DRAMs (60 & 70ns).; 128Mbytes Max Memory; All system memory resides in the 4 SIMM sockets, J3-J6.; Base memory should be placed in the SIMM socket pair J3-J4.Pentium Pro192 MBs Maximum; FPM (Fast Page Mode) or EDO, 60 ns or 70 ns, 72-pin SIMMs; 6 SIMM sockets; 32 bit (non-parity) or 36-bit (parity); ECC (using 36-bit SIMMs); 2 sockets (SIMMs must be installed in pairs)Pentium MMX16 MB to 384 MB, 168pin, unbuffered, SDRAM DIMMsPentium II16 MB to 384 MB, 168pin, unbuffered, SDRAM DIMMs**Grafikkarten**PentiumController: Cirrus Logic 5436 Graphics controller with 1 MByte Video Memory; Memory: 1 MByte standard, Upgrade connector for additional 1MByte; VESA Feature Connector;
[Treiber Download Win95 (archiviert)](http://web.archive.org/web/20170923154038/http://treiber.de/download-treiber/Cirrus%20Logic/CL-GD-5436/)Pentium Pro(PCI Card) Matrox MGA 2064w; (PCI Card) CL-5446Pentium MMMS3 Enhanced 64-bit Graphics (integrated) w/1MB 66MHz SGRAMPentium IIMatrox Performance Graphics (Integrated) w/2MB of 100Mhz SGRAM
[Quelle](https://support.hp.com/in-en/document/c00327707)

---

Dieser Artikel erschien zuerst auf [thafaker.crabdance.com](http://thafaker.crabdance.com/grav/news/das-bios-der-compaq-deskpro-computer)

---

1. 
Ich persönlich habe sehr gute Erfahrungen mit dem [NEC USB UF0002](https://www.google.com/search?q=NEC-USB-Diskettenlaufwerk-UF0002&amp;tbm=isch&amp;hl=de&amp;ved=2ahUKEwjP866Ins_oAhWEuKQKHYLvBDAQBXoECAEQIA&amp;biw=1259&amp;bih=987) Diskettenlaufwerk gemacht, was es auf eBay regelmäßig zu sehr günstigen Preisen gibt. Damit schreibe ich problemlos alle Images, selbst die für den Atari ST. [↩︎](#fnref1)

## Ressourcen

[

sp15674

Diskettensatz für Compaq Deskpro 2000, 3 Disketten Files

sp15674.exe

3 MB

.a{fill:none;stroke:currentColor;stroke-linecap:round;stroke-linejoin:round;stroke-width:1.5px;}download-circle
](__GHOST_URL__/content/files/2024/05/sp15674.exe)
