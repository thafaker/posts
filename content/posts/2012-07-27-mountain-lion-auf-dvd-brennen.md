---
title: macos ISO auf DVD brennen
slug: mountain-lion-auf-dvd-brennen
date_published: 2012-07-26T22:00:00.000Z
date_updated: 2024-10-29T08:15:41.000Z
tags: macos, iso, dvd, usb, brennen, image, howto, anleitung, how to
---

[**UPDATE II**] Diese Anleitung gilt für jedes OS X bis hin zu macOS, so lange der Rohling groß genug ist. Aber heutzutage erstellt man sich einen USB-Stick, was ich unten ausgeführt habe. 

---

Nachdem ja nun gestern Apples neuester Streich, OS X 10.8 alias Mountain Lion veröffentlich worden ist, fragen sich sicher einige, wie man diesen Geniestreich auf ein Medium wie USB Stick oder DVD bringen kann. Apple liefert sein neues OS nämlich nur noch direkt über den Mac App Store aus und von diesem startet es den Installier und legt los.

[**UPDATE**] Unten an diesen Artikel habe ich ein Update angefügt, was euch beschreibt, wie ihr Mountain Lion auch auf eine 4,7 GB DVD bekommt und somit keine Dual Layer verballern müsst - oder wenn ihr sowieso keine zur Hand habt, so wie ich.

### Mountain Lion auf DVD

Hier also beschreibe ich nun die Vorgehensweise, wie man Mountain Lion auf einen Stick oder eine DVD bekommt.

1. Kauft euch Mountain Lion im Mac App Store für euren 10.8 kompatiblen Mac, der mindestens auf 10.6 oder 10.7 läuft.
2. Rechtsklick auf “Install Mac OS X Mountain Lion.app” und wählt *Paketinhalt anzeigen* aus. Die App liegt nach dem Kauf und Download im Programme-Order.
3. In diesem Ordner der dann erscheint, gibt es einen *SharedSupport* Ordner und in diesem findet man die Datei InstallESD.dmg”. Dies ist das eigentliche Mountain Lion Installations-Boot-Image.
4. Kopiert diese Datei “InstallESD.dmg” auf euren Desktop.
5. Startet nun das *Festplattendienstprogramm* und klickt auf *Brennen*.
6. Wählt das kopierte “InstallESD.dmg” vom Desktop aus und legt eine Dual Layer DVD ein, damit die knapp 5 GB auch ihren Platz haben. Single Layer gehen leider nicht :-(
7. Wartet bis die DVD fertig ist, *Bumsfallera* #done
8. *Viel Spaß*.

Das war einfach und jetzt habt ihr ein Mountain Lion auf DVD dass ihr überall installieren könnt, solange der Recher nur euch gehört. Das ist nämlich die vertragsbedingte Voraussetzung seitens Apple, man darf sein ML auf allen eigenen Macs installieren. Cool eigentlich.

### Mountain Lion auf USB Stick

Hier die Anleitung, wie man Mountain Lion auf einen USB-Stick bringt.

1. Kauft euch Mountain Lion im Mac App Store für euren 10.8 kompatiblen Mac, der mindestens auf 10.6 oder 10.7 läuft.
2. Rechtsklick auf “Install Mac OS X Mountain Lion.app” und wählt *Paketinhalt anzeigen* aus. Die App liegt nach dem Kauf und Download im Programme-Order.
3. In diesem Ordner der dann erscheint, gibt es einen *SharedSupport* Ordner und in diesem findet man die Datei InstallESD.dmg”. Dies ist das eigentliche Mountain Lion Installations-Boot-Image.
4. Kopiert diese Datei “InstallESD.dmg” auf euren Desktop.
5. Startet nun das *Festplattendienstprogramm* und klickt auf den “Wiederherstellen”-Tab[https://web.archive.org/web/20120807161050/http://thafaker.hydra.uberspace.de/octopress/images/articles/fdp.png](https://web.archive.org/web/20120807161050/http://thafaker.hydra.uberspace.de/octopress/images/articles/fdp.png)
6. Zieht das “InstallESD.dmg” auf die *Quelle* und bei Zielmedium wählt ihr euren mindestens 8 GB großen USB-Stick aus. Wenn der Stick kleiner ist, wird es leider nicht funktionieren.
7. Klickt auf “Wiederherstellen”, lasst den Stick löschen falls ihr danach gefragt werdet und je nach Geschwindigkeit, 7. Minuten bei mir, habt ihr einen **Stick mit Mountain Lion** drauf.
8. *Viel Spaß*.

Jetzt hat man also die Möglichkeit, eine Clean Install durchzuführen, denn dazu benötigt man natürlich immer ein externes Medium.

### Mountain Lion auf eine 4,7 GB DVD brennen

Funktioniert natürlich auch wieder übers Terminal. Wir öffnen *Terminal.app* und wechseln mit `cd Desktop` auf den Desktop, da wir ja vorhin bereits das Image *InstallESD.dmg* auf eben jenen kopiert hatten.

Nun geben wir folgenden Befehl ein, der aus dem DMG Format eine ISO macht. Das dauert eine Weile…

    1

    hdiutil makehybrid -o InstallESD.iso InstallESD.dmg
    

Jetzt kann man eine leere 4.7GB DVD in den DVD-Brenner einlegen und führt im Terminal folgenden Befehl aus:

    1

    hdiutil burn InstallESD.iso
    

Nun wird das zuvor umgewandelte ISO Image von Mountain Lion auf eine 4.7GB DVD gebrannt. Wenn alles funktioniert hat, war es das schon und ihr seid fertig. *Easy*.

---

Das ganze sieht im Terminal dann etwa so aus:

    12345

    [thafaker@iMac-SSD Desktop]$ hdiutil makehybrid -o InstallESD.iso InstallESD.dmg
    Creating hybrid image...
    ..............................................................................................................
    [thafaker@iMac-SSD Desktop]$

Wenn man nun den Befehl `ll` ausführt, sieht man beide Images:

    123456

    [thafaker@iMac-SSD Desktop]$ ll
    total 17000136
    drwxr-xr-x@  4 thafaker  staff         136 27 Jul 18:48 .
    drwxr-xr-x@ 20 thafaker  staff         680 26 Jul 10:18 ..
    -rw-r--r--@  1 thafaker  staff  4348218934 26 Jul 10:18 InstallESD.dmg
    -rw-r--r--   1 thafaker  staff  4355850240 27 Jul 18:45 InstallESD.iso
    

Der Brennvorgang sieht in etwa so aus:

    123456789101112131415161718

    [thafaker@iMac-SSD Desktop]$ hdiutil burn InstallESD.iso
    Please insert a disc:
    Daten für den Brennvorgang vorbereiten
    Session öffnen
    Spur öffnen
    Spur schreiben
    ..............................................................................................................
    Spur schließen
    ..............................................................................................................
    Session schließen
    ..............................................................................................................
    Brennvorgang abschließen
    Brennergebnis überprüfen …
    Überprüfen
    ...............................................................................................................
    Der Brennvorgang wurde erfolgreich abgeschlossen
    ...............................................................................................................
    hdiutil: burn: completed
    

*Viel Spaß*
