---
title: iTunes Restore Fehler 6 und 1600
slug: itunes-restore-fehler-6-und-1600
date_published: 2009-07-01T20:34:23.000Z
date_updated: 2018-08-22T09:39:01.000Z
---

Für alle mit den iTunes Fehlern 6, 1600, 1601, 1602, 1603, 1604, 1605, 1606, 1607, 1608, 1609 kann folgende Problemlösung etwaig hilfreich sein.

Die Anleitungen sind bereits etwas älter, heute sollten solche Fehler nicht mehr auftauchen.

**Variante 1:**

Fehler 6:

- Falscher Mode! Nicht Restore sondern DFU-Mode! Anleitung gibts [**hier**](__GHOST_URL__/30/wie-komme-ich-in-den-dfu-mode-iphone-ipod-touch).

Fehler 160* (* steht für 0 bis 9):

- Laded die folgende File runter: x12220000_4_Recovery.ipsw
- Öffnet den Folder unter:XP: **C:/Dokumente und Einstellungen/BENUTZERNAME/Anwendungsdaten/Apple Computer/iTunes/Device Support/**
VISTA unter Start in das Suchfeld:** %appdata%\Apple Computer\iTunes\Device Support eingeben**OS X:** …users/username/Library/iTunes/**
- Sollten diese Ordner nicht gefunden werden, müsst ihr in euren Ordneroptionen “Versteckte Dateien und Ordner anzeigen” aktivieren.
- Sollte diese “Recovery File” bereits vorhanden sein, einfach ersetzen!
- Im Anschluss mit iTunes die Custom Firmware auf das Gerät aufspielen.

**Variante 2**
- Öffnet den Folder unter:XP: **C:/Dokumente und Einstellungen/BENUTZERNAME/Anwendungsdaten/Apple Computer/iTunes/Device Support/**
VISTA unter Start in das Suchfeld:** %appdata%\Apple Computer\iTunes\Device Support eingeben**
OS X:** …users/username/Library/iTunes/**
- **Löscht die darin befindliche File heraus (Backupt sie irgendwo hin)**
- **Versucht erneut eine Gejailbreakte Firmware aufzuspiele**

**Variante 3 (Getestet und erfolgreich bei Firmware >2.0
**
- Sollte immernoch der Fehler 1600 aufscheinen
- Die Datei in Variante 2 rauslöschen wenn nicht schon rausgelöscht
- einen originale Firmware 2.1 auf das Device installieren (**nicht die Firmware 2.2!!**; diese Firmware 2.1 sollte wenn möglich nicht im DFU Mode installiert werden => Fehler 1600)
- Gerät ist jetzt etwaig im Activation Screen
- wenn es auf einen Betreiber gelockt ist, der aber nicht verwendet wird (unlock wird benötigt), das Gerät jetzt mit Quickpwn Jailbreaken
- nach dem Jailbreak eine gejailbreakte neue Firmware 2.2 installieren (muss gejailbreakt sein wenn ein unlock gewünscht wird; original Vertrags-iPhones können auch im nachhinein jailbreaken mit Quickpwn)

**Variante 4 (am besten mit PC):**
1. iTunes 7.5 & iPhone Firmware 1.1.4 downloaden
2. iTunes 7.7.* bzw iTunes 8 komplett deinstallieren
3. Computer neu starten
4. iTunes 7.5 installieren
5. iPhone in den DFU-Modus bringen ([**Anleitung**](__GHOST_URL__/30/wie-komme-ich-in-den-dfu-mode-iphone-ipod-touch))
6. via SHIFT+KLICK (Windows) bzw. ALT+KLICK (OSX) die originale, nicht gejailbreakte Firmware 1.1.4 installieren

Danach kann auf Wunsch iTunes wieder auf die neuste Version upgedatet werden. Im Anschluss kann man sein iPhone ebenfalls wieder auf die aktuellste Firmware bringen. Erst danach, wenn auf dem iPhone die aktuellste Firmware installiert ist, kann eine gejailbreakte Firmware (mit oder ohne Unlock installiert werden)

Bei “Reperaturarbeiten” sollte am besten mit unveränderten Firmwares gearbeitet werden.
