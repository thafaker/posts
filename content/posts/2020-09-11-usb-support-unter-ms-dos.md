---
title: [UPDATE] USB Support unter MS-DOS
slug: usb-support-unter-ms-dos
date_published: 2020-09-11T06:36:11.000Z
date_updated: 2025-08-07T08:24:06.000Z
tags: anleitung, howto, how to, dos 6.22, vintage computing, netzwerk, sicherheitsupdate
excerpt: In diesem Artikel beschreiben wir die Vorgehensweise, um unter MS-DOS einen USB Treiber zu laden um einen USB-Stick einzubinden.
---

Ich beschäftige mich gerade wieder einmal mit alter Hardware, da mir ein **Pentium II 366 MHz 64 MB-Ram**, ein *Toshiba Satellite 4080*, untergekommen ist. Und natürlich kann man auf diesem Computer auch noch prima DOS installieren, da er über ein Diskettenlaufwerk verfügt und nicht zu schnell ist. Aber Netzwerk über **PCMCIA**, es gestaltet sich unter *Windows for Workgroups* schwierig. Also wäre es cool, viele Daten schnell austauschen zu können. Das Gerät verfügt immerhin bereits über einen USB 1.1 Anschluss.

![Vintage Notebook unter DOS mit USB-Treibern und Zugriff auf einen USB-Stick](__GHOST_URL__/content/images/2020/09/dos.jpg)Vintage Notebook unter DOS mit USB-Treibern und Zugriff auf einen USB-Stick

Die gute Nachricht: es gibt tatsächlich einen nativen DOS USB-Treiber von Panasonic, der aktuellste aus dem Jahr 2004. Dies wurde zwar ursprünglich nur für deren eigene Geräte entwickelt, allerdings hat er sich als ziemlich Allgemein erwiesen und funktioniert auch mit vielen anderen Geräten.

### Downloads:

Wir haben hier vier verschiedene ZIP-Dateien, die wir in unterschiedlicher Art und Weise einsetzen.

- [MHAIRUDOS.zip](__GHOST_URL__/content/files/2024/01/MHAIRUDOS.zip) - Das Paket enthält schon alles, was wir brauchen. Aus dieser ZIP benötigen wir die beiden Dateien DI1000DD.SYS und USBASPI.SYS. Die zweite Datei ist der eigentliche Chipsatztreiber, die DI1000DD.SYS ist ein Treiber für Massenspeicher, mit dieser können wir also den USB-Stick als Laufwerk unter DOS ansprechen. Beide Dateien werden in der CONFIG.SYS geladen. Ich habe die benötigten Dateien einfach unter c: gelassen. In eure bestehende CONFIG.SYS müssen eigentlich nur zwei Zeilen hinzugefügt werden:

---

[**config.sys**]

DEVICEHIGH=USBASPI.SYS

DEVICEHIGH=DI1000DD.SYS

---

[**Mögliche Schalter hinter der USBASPI.SYS**]

usbaspi1.sys - Panasonic Communications Co. ASPI Manager for USB mass-storage (Universal Driver)

device=usbaspi1.sys /V [/E (EHCI USB 2.0) /O (OHCI USB 1.1 Add-on) /U (UHCI USB 1.1 Integrated)]

usbaspi2.sys - Novac ASPI Manager for UHCI/OHCI USB mass-storage

device=usbaspi2.sys

usbaspi3.sys - Medialogic ASPI Manager for USB mass-storage

device=usbaspi3.sys

usbaspi4.sys - Iomega ASPI USB-OHCI 1.1

device=usbaspi4.sys

usbaspi5.sys - Iomega ASPI USB-UHCI 1.0

device=usbaspi5.sys

Dann wird der Rechner neu gestartet und USB sollte automatisch geladen werden. Wenn ihr einen Stick anschließt, sollte dieser via DI1000DD.SYS eingebunden und mit einem Laufwerksbuchstaben versehen werden. Es emfpiehlt sicht, den Stick wie eine Festplatte unter FDISK.EXE mit FAT 16 und 2047 MB Partitionsgröße zu formatieren, so gewährleistet man die beste Kompatibilität.

Sollten die Einträge in der CONFIG.SYS nicht zum Ziel führen und z.B. der Treiber nicht geladen werden, so kommt die nachfolgende ZIP-Datei zum Zuge. Bei meinem Notebook wurde der ursprüngliche Treiber (kein USB-Chipset erkannt) nicht geladen, und ich wählte einen anderen aus der ZIP-Datei USBASPIS.ZIP aus, mit diesem gelang die EInbindung problemlos. Das ganze funktioniert und MS-DOS 6.22 genau so wie unter *FreeDOS 1.3 RC 2*. *Für Sie getestet*.

**Die Downloads findet ihr unten bei *Ressourcen*.**

- USBASPIS.zip - In diesem File befinden sich 5 verschiedene USB-Treiber, die man einfach durchtesten kann, indem man sie in der CONFIG.SYS lädt. Mit meinem Notebook funktioniert beispielsweise nur der Treiber von IOMEGA.
- USBASPI.zip - Das ist die ursprüngliche USBASPI in einer älteren Version, hier zur der Vollständigkeit aufgelistet.
- MHAIRUWIN.zip - Der Vollständigkit halber, wird an dieser Stelle nicht benötigt.

*Danke PANASONIC*.

## Ressourcen

[

usbaspi-v2.20

Das ist die ursprüngliche USBASPI in einer älteren Version, hier zur der Vollständigkeit aufgelistet

usbaspi-v2.20.zip

21 KB

.a{fill:none;stroke:currentColor;stroke-linecap:round;stroke-linejoin:round;stroke-width:1.5px;}download-circle
](__GHOST_URL__/content/files/2024/01/usbaspi-v2.20.zip)

[

USBASPIS

In diesem File befinden sich 5 verschiedene USB-Treiber, die man einfach durchtesten kann, indem man

USBASPIS.zip

84 KB

.a{fill:none;stroke:currentColor;stroke-linecap:round;stroke-linejoin:round;stroke-width:1.5px;}download-circle
](__GHOST_URL__/content/files/2024/01/USBASPIS.zip)

[

MHAIRUDOS

MHAIRUDOS.zip

25 KB

.a{fill:none;stroke:currentColor;stroke-linecap:round;stroke-linejoin:round;stroke-width:1.5px;}download-circle
](__GHOST_URL__/content/files/2024/01/MHAIRUDOS.zip)

[

MHAIRUWIN

Der Vollständigkit halber, wird an dieser Stelle nicht benötigt.

MHAIRUWIN.zip

60 KB

.a{fill:none;stroke:currentColor;stroke-linecap:round;stroke-linejoin:round;stroke-width:1.5px;}download-circle
](__GHOST_URL__/content/files/2024/01/MHAIRUWIN.zip)
