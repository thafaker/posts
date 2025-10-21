---
title: PCMCIA CF Compact Flash Adapter mit Fat32 CF-Card am Amiga
slug: pcmcia-cf-compact-flash-adapter-mit-fat32-cf-card-am-amiga
date_published: 2024-01-31T11:52:36.000Z
date_updated: 2024-04-19T11:51:35.000Z
tags: vintage computing, amiga, anleitung, howto, how to, pcmcia, cf card
---

Es ist üblich an seinen Amiga 1200/600 einen **PCMCIA-CF-Card** Adapter zu benutzen, um ihn am PC via Cardreader mit Dateien zu befüllen und diese dann als Laufwerk am Amiga zu benutzen. Dies erleichtert den Datenaustausch erheblich. 

In diesem Artikel beschreibe ich, welche Dinge ihr installieren müsst damit ihr CF-Karten lesen könnt. Es ist ganz simple, es sind grundsätzlich zwei Dinge. Wir brauchen dazu den Compact Flash Treiber, den Fat32 Treiber, eventuell einen Card-Patch (optional für Amiga OS vor 3.1.4) und wenn wir wollen noch etwas für CrossDOS, damit wir 720 KB DOS Disketten am Amiga lesen und schreiben können (optional). *Das wars*.

Ein *beispielhafter PCMCIA-Adapter. 
[

CF CARD zu PCMCIA ADAPTER - für Amiga 600/1200 u.a. | eBay

Batterien dürfen nicht über den normalen Hausmüll entsorgt werden. Das chemische Symbol (Cd, Hg oder Pb) wird unter dem Zeichen abgebildet. Mit diesem Adapter können Sie CF Karten als Festplatte in Ihrem Amiga 600/1200 benutzen.Siehaben damit dann eine geräuschlose Festplatte mit deutlich geringeren Zugriffszeiten als einer normalen IDE HDD.

![](https://www.ebay.de/favicon.ico)eBay

![](https://i.ebayimg.com/images/g/0cYAAOSwQcFjf1uC/s-l400.jpg)
](https://www.ebay.de/itm/204162848387?itmmeta=01HVV32HGC286WTN8ME3X7Q8QN&amp;hash=item2f890dd683:g:0cYAAOSwQcFjf1uC&amp;itmprp=enc%3AAQAJAAAA4PcF8qJtlYKRQQ7RpgSPMq%2Fts%2Fxr4zI%2FhgfJNaiGXEf6bBe9DDjvLth%2FDeLfeyHTQwvxtVTRcziJqX8k9ja0Nzg84TuaMcoFfV%2BuyjgvuC0R%2BQm26XtZnwo9Mi3nNhh90%2F5BJ3NibL9uVPrPifFQgQ%2FANxprWh0X2jiOKUPCqocIYRhqlGw4tl0Rma12%2BAQEBIEI3H1LYcA%2FMo3wG%2FRRMkOV8BtYFtMgovlwdN1XeZuMZUzZxN6enZGDOLhHURnzY9G5cgBP6Y9YupmV42Fo9AOB9zvBoVb3SB0egZMHgWwH%7Ctkp%3ABk9SR6aYiuPeYw)*****Dies ist kein Affiliate-Link, wir erhalten für die Nennung kein Geld. Er dient lediglich der Veranschaulichung:

Diese Anleitung funktioniert mit Amiga OS 3.0 bis 3.2 auf Amigas mit PCMCIA-Schnittstelle.
![Notebook mit herausstehender PCMCIA-Karte](__GHOST_URL__/content/images/2024/01/3Com_modem_-_Ethernet_PCMCIA_in_IBM_9547.jpg)Notebook mit herausstehender PCMCIA-Karte (C) [Jim.henderson](https://commons.wikimedia.org/wiki/User:Jim.henderson) CC0
## CFD

Der **CFD** Treiber erlaubt es uns, **Compact Flash** Karten zu benutzen die im **PCMCIA** Slot des Amigas stecken.

- Direkter [Download](http://aminet.net/driver/media/CFD133.lha) vom Aminet oder hier:

[

CFD133

Compact Flash Treiber für Amiga OS

CFD133.lha

153 KB

.a{fill:none;stroke:currentColor;stroke-linecap:round;stroke-linejoin:round;stroke-width:1.5px;}download-circle
](__GHOST_URL__/content/files/2024/01/CFD133.lha)

- Entpackt die herunter geladene Datei **CFD133.lha** (zum Beispiel in die Ram-Disk) und kopiert aus **CFD133/DEVS/compactflash.device** nach **Devs:** auf eurem Amiga:

`copy ram:CFD133/DEVS/compactflash.device Devs:compactflash.device`

Weiterhin kopiert ihr **CFD133/DEVS/CF0** und **CFD133/DEVS/CF0.info** nach **Devs:DosDrivers** auf eurem Amiga, in der Shell würdet ihr ungefähr folgenden Befehl eingeben:

`copy ram:CFD133/DEVS/CF0 Devs:DosDrivers/CF0`

sowie

`copy ram:CFD133/DEVS/CF0.info Devs:DosDrivers/CF0.info`

Das wars, somit ist der PCMCIA Kartenleser installiert. Jetzt brauchen wir den Treiber, um Windows-Partitionen (nicht NTFS) lesen und schreiben zu können.

## FAT95

Der **FAT95** Treiber erlaubt es uns, unter dem Amiga auf **FAT16** oder **FAT32** formatierte Compact Flash Cards zuzugreifen und zu schreiben.

- Direkter [Download](http://aminet.net/disk/misc/fat95.lha) vom Aminet oder hier:

[

fat95

Das FAT-Dateisystem für Amiga OS

fat95.lha

235 KB

.a{fill:none;stroke:currentColor;stroke-linecap:round;stroke-linejoin:round;stroke-width:1.5px;}download-circle
](__GHOST_URL__/content/files/2024/01/fat95-1.lha)

Entpackt die herunter geladene Datei **fat95.lha** (z.B. in die RAM-Disk) und kopiert aus dem entpackten Ordner die Datei **fat95/l/fat95** zu **L:** auf eurem Amiga:

`copy ram:fat95/l/fat95 L:fat95`

Das wars, nach einem Neustart könnt ihr CF-Karten mit Fat32 an eurem Amiga und Windows PC (oder Mac, oder Linux) benutzen und fortan Dateien hin und her kopieren.

## CardReset/CardPatch (A1200, <Kickstart 3.1.4 only)

💡

Dies müsst ihr nur durchführen, wenn euer A1200 mit Kickstarts niedriger als 3.1.4 - i.e. **Kickstart 3.0/3.1/3.X** ausgestattet ist.

Auf dem **Amiga 1200** gibt es einen Hardware Bug im **Gayle-Chip. **Das bedeutet dass das **CC_RESET** Signal nicht an den **PCMCIA** slot gesendet wird. **CardReset** und **CardPatch** lösen das Problem via Software, zum Glück.

Ladet folgende zwei Datetein aus dem Aminet (oder von hier):

[http://aminet.net/util/boot/CardPatch.lha](http://aminet.net/util/boot/CardPatch.lha)

[

CardPatch

CardPatch.lha

3 KB

.a{fill:none;stroke:currentColor;stroke-linecap:round;stroke-linejoin:round;stroke-width:1.5px;}download-circle
](__GHOST_URL__/content/files/2024/01/CardPatch.lha)

[http://aminet.net/util/boot/CardReset.lha](http://aminet.net/util/boot/CardReset.lha)

[

CardReset

CardReset.lha

3 KB

.a{fill:none;stroke:currentColor;stroke-linecap:round;stroke-linejoin:round;stroke-width:1.5px;}download-circle
](__GHOST_URL__/content/files/2024/01/CardReset.lha)

Kopiert die **CardReset **und **CardPatch** Dateien in C:

Die Datei **S:Startup-Sequence** muss mit folgendem Befehl vor**LoadWB** aktualisiert werden:

C:CardPatch

Run >NIL: C:CardReset TICKS 50

## CrossDOS (Workbench 2.0 and above)

💡

Dies ist ebenfalls optional und muss nur durchgeführt werden, wenn ihr 720KB-Disketten vom PC am Amiga lesen und schreiben wollt.

**CrossDOS** erlaubt es **720K PC formatted floppy disks** unter dem Amiga zu benutzen. The driver files can be found in the Workbench (2.0 and above)**EXTRAS** and **STORAGE** disks.

Copy the **EXTRAS:L/CrossDOSFileSystem** file to **L:**

For each drive (DF0, DF1) you want CrossDOS to work on, copy the appropriate DOS Driver file from **STORAGE:DosDrivers** to **Devs:DosDrivers**

For example, for **DF0**, copy:

STORAGE:DosDrivers/PC0

STORAGE:DosDrivers/PC0.info

to

Devs:DosDrivers/PC0

Devs:DosDrivers/PC0.info

For DF1 and DF2, you will have to create the PC1 and PC2 files respectively, using the PC0 or PC1 file as a template.
