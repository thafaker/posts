---
title: Boot Powermac G5 from USB [UPDATE]
slug: boot-powermac-from-usb
date_published: 2024-11-09T08:21:11.000Z
date_updated: 2025-09-11T20:15:24.000Z
tags: usb, open firmware, Powermac G5, anleitung, howto, how to, vintage computing, updated
---

💡

**HINWEIS**
Auf Apfelhammer.de habe ich einen ausführlichen Artikel geschrieben, wie man einen Powermac mit OpenFirmware von USB starten kann. Das funktioniert vom G3 bis zum G5.
[How To Boot Powermac from USB](https://apfelhammer.de/how-to-boot-powermac-from-usb.html)

[**UPDATE** 27.12.2024] Ich habe nun erfolgreich mit Mac OS X und Linux Images via USB gebootet, sodass ich beides bestätigen kann. Sehr wahrscheinlich wird man auch ein BSD booten können, aber das hat mich bisher noch nicht interessiert, sodass ich das Proof-Of-Concept offen lassen muss.

Schreibt eure herunter geladene LINUX Iso auf einen USB-Stick. Schaut vorher nach, welche Disk euer USB Stick hat. Dies tut ihr mit dem Befehl **diskutil list** im Terminal eures macOS. Mein Stick hat 16 GB und ist Disk8.

Mit folgendem Befehl kopiere ich das Image von Adelie Linux PPC64 auf den Stick:

    sudo dd if=/Downloads/adelie-live-lxqt-ppc64-1.0-beta6-20241214.iso of=/dev/disk8 bs=1m status=progress

Das dauert nicht lang, dann entferne ich den Stick und stecke ihn an den USB-Anschluss meines Powermacs. Dann boote ich in die OpenFirmware. Ich halte dazu die ALT-Taste gedrückt damit der OF-Bootmaneger erscheint. Dort drücke ich STRG+Z (oder Y) und er startet OpenFirmware. Dort gebe ich folgenden Befehl ein, und er bootet Linux vom USB-Stick:

    # to boot Adelie Linux from usb on powermac g5
    boot ud:,\boot\grubcore.img
    
    # to boot Mac OS X from usb on powermac g5
    boot ud:,\:tbxi

---

[**ORIGINAL**] Ich habe mich heute ein wenig intensiver mit Open Firmware ([dem offenen Bootstandard](https://de.wikipedia.org/wiki/Open_Firmware), z.B. von New World Macs oder Sun SPARCStations etc. pp.) beschäftigt, weil mein [Powermac G5](__GHOST_URL__/tag/powermac-g5/) einfach nicht von DVD booten wollte. Ich habe natürlich erst mal eine Weile gebraucht um zu erkennen, dass es am DVD-Laufwerk liegt - und bin dann durch ein wenig Recherche im Netz auf die Idee gekommen, von USB zu booten. 

Auf heutigen Computern ist das recht einfach und unterscheidet sich faktisch nicht von einer internen Festplatte, auf einem aktuellen Intel oder ARM Mac muss man beim Einschalten einfach nur die Wahltaste gedrückt halten und es werden alle bootfähigen Geräte angezeigt, egal ob USB, CD, Thunderbolt, Firewire, Netzwerk, mehrere Festplatten etc. pp. 

Aber der Power Mac G5 kann das grundsätzlich nicht *so*. Und wenn ich "*so*" schreibe, meine ich das auch **so**. Denn über OpenFirmware ist es dennoch möglich einen USB-Stick anzusprechen und zu booten, so als würde man von einer Installation-DVD starten. (Was ich übrigens gerade tue: ich installiere 10.5 Leopard PPC von USB-Stick auf eine 256 GB SSD. Upper)

💡

Im Netz kursiert die weitreichende Meinung, dass man Power Macs nicht von USB booten könne. *Das stimmt nicht*! Man kann faktisch jeden Powermac G3, G4 oder G5 von USB booten.

Voraussetzung für den Boot von USB ist jedoch ein entsprechend vorbereitetes Medium.

### Vorbereitung des USB-Sticks

Für den Bootvorgang ist es wichtig, dass man eine vorhandene ISO-Datei (ich habe eine Mac OS X 10.5.4 Leopard DVD ISO) z.B. via **dd** command auf den USB Stick schreibt. Dazu bedienen wir uns wie gesagt des Unix Tools dd, das zum blockorientierten Kopieren oder Konvertieren beliebiger Dateien dient, welches Teil von jedem Linux und auch macOS ist. Dies rufen wir über das Terminal auf. Der Befehl lautet folgendermaßen und erfordert Root-Rechte:

    sudo dd if=/path/to/mac-osx-10.5.iso of=/dev/diskN bs=1m

Befehl fürs Terminal von macOS oder Linux um ein Image auf einen Datenträger zu schreiben, via dem Befehl dd

Ihr müsst /**path/to/Mac…** an eure ISO-Datei anpassen und vor allem mit dem Befehl **diskutil list** (unter macOS) vorher euren Stick identifizieren, damit ihr **/dev/diskN**  (diskN war bei mir disk4) korrekt eingeben könnt. Das ist euer Stick. Das ist wichtig! Ansonsten überschreibt ihr womöglich eure Festplatte mit der ISO Datei, alle Daten sind weg. Ich habe einen alten USB 2.0 16 GB Stick genutzt, der für die 8,7 GB Leopard völlig ausreichend ist. Der Befehl **dd** dauert eine ganze Weile, irgendwann ist der Befehl im Terminal abgeschlossen und wir sehen wieder den Prompt.

💡

Ihr müsst /**path/to/Mac** an eure ISO-Datei anpassen und vor allem mit dem Befehl **diskutil list** (unter macOS) vorher euren Stick identifizieren, damit ihr **/dev/diskN** (diskN war bei mir disk4) korrekt eingeben könnt. Das ist euer Stick. Das ist wichtig! Ansonsten überschreibt ihr womöglich eure Festplatte mit der ISO Datei, alle Daten sind weg.

![Powermac G5 mit angeschlossenem CRUZER USB Stick am Front USB (C) Herr Montag](__GHOST_URL__/content/images/2024/11/powermacg_g5_usb_front.jpg)Mein Powermac G5 mit angeschlossenem CRUZER Contour USB Stick am Front USB (C) Herr Montag
**Jetzt kommen wir ans Eingemachte**! Wir stecken den frischen USB-Stick an unseren Powermac G5 an (ich empfehle vorn, aber das ist Geschmacksache und meinen Rücken betreffend) und booten in die Open Firmware. Dazu halten wir beim Einschalten des Macs die Tasten **Option + Apfel-Taste + O + F** gleichzeitig gedrückt. Also die 4 Tasten. Dann sollte uns der Mac mit einem freundlichen Open Firmware prompt begrüßen.

💡

Wichtig ist: der USB Stick muss *vor* dem Einschalten angesteckt werden, OF ist hier nicht hotplugging-fähig. 

Wenn ihr Bock habt dann könnt ihr jetzt mit dem Befehl** dev / ls** die Hardware des G5 und daran angeschlossene Geräte ausgeben, müsst ihr aber nicht. Wenn der USB Stick vorn an den Front-USB unterhalb des Einschaltknopfs angeschlossen ist, dann ist das Device USB3.

USB3 gilt für den Powermac,11,2 (late 2005); ich weiß nicht, ob es hier große Unterschiede innerhalb der G5-Reihe, aber mit Sicherheit innerhalb anderer Powermacs, gibt.

Folgender Befehl in der Open Firmware bootet den *Mac OS X 10.5 Installer* von USB:

    boot usb3/disk@1:3,\System\Library\CoreServices\BootX

Befehl um Power Mac G5 von USB Stick zu booten

💡

Die Open Firmware geht immer von einem us-amerikanischen Layout der Tastatur aus: 
@ ist Shift+2
Doppelpunkt ist Shift+Ö
Backslash ist die Raute-Taste.

Andere Macs haben eventuell andere USB-Schnittstellen, dort könnte USB3 auch USB1 oder 2 oder 5 sein. Passt es entsprechend an. Wenn ihr Euer ISO Image allerdings wie im oberen Schritt beschrieben auf den Stick *gebrannt* habt, dann sollte auf dem Stick die 3 Partition die mit den Daten sein, die ihr in der Open Firmware so aufruft. 

Nach Eingabe des Befehls wird der Bildschirm grau, ihr seht den Apfel, ihr seht den drehenden Kreis und dann startet der Installer von Mac OS X 10.5, so als ob ihr von DVD gebootet hättet. Jetz könnt ihr eure Festplatte partitionieren, formatieren, reparieren und einfach Mac OS X installieren.

Ich werde später ausprobieren, ob das mit einer LINUX Distribution ähnlich funktionieren kann. Wichtig ist dieses BootX File, was über ein **tbxi** Attribut verfügen muss.

---

### Ressources

- [https://lifedigital2010.wordpress.com/2011/04/03/how-to-install-mac-osx-from-usb-on-powerbook-g4/](https://lifedigital2010.wordpress.com/2011/04/03/how-to-install-mac-osx-from-usb-on-powerbook-g4/)

[

Open Firmware

Open Firmware, now also known as OpenBIOS, is hardware-independent firmware (computer software which loads the operating system) initially developed by Sun Microsystems for use in their SPARC-based workstations and servers. It was described in IEEE 1275 and adopted by PowerPC-based systems such as PegasosPPC. However, IEEE 1275-1994 was not affirmed by the Open Firmware Working Group in 1998 and has since been withdrawn.[1][2] Open Firmware may be accessed through its command-line interface, whi

![](__GHOST_URL__/content/images/icon/latest)Fandom, Inc.Contributors to Apple Wiki

![](__GHOST_URL__/content/images/thumbnail/latest)
](https://apple.fandom.com/wiki/Open_Firmware)
