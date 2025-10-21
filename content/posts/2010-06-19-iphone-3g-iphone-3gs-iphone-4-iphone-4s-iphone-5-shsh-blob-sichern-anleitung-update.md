---
title: iPhone 3G / iPhone 3GS / iPhone 4 / iPhone 4S / iPhone 5 / iPhone 5c / iPhone 5S / iPhone 6 – SHSH Blob sichern – Anleitung [UPDATE]
slug: iphone-3g-iphone-3gs-iphone-4-iphone-4s-iphone-5-shsh-blob-sichern-anleitung-update
date_published: 2010-06-19T16:21:42.000Z
date_updated: 2018-08-22T09:38:21.000Z
tags: how to, ipad, jailbreak, iphone, howto, tiny umbrella, shsh, blobs, blops, ecid, sicherung, ipod
---

### Einleitung

Was ist ein **SHSH Blob /****SHSH Hash** oder eine **ECID SHSH**? Der SHSH Hash ist eine **eindeutige Signatur** der von den Apple Servern angefragt wird, wenn ihr eine Wiederherstellung der Firmware durchführen wollt. Hierbei ist es so, dass jede Firmware und jedes iPhone einen anderen Hash besitzen. Somit gibt es bei jeder Firmware Version nur einen eindeutigen Schlüssel für euer Gerät. Ziel von Apple ist es, dass ihr keine ältere Firmware auf eurem iPhone wiederherstellen könnt, da die alten Signatur nicht mehr freigegeben werden.

Somit kann es sein, dass ihr euren Jailbreak verliert, wenn ihr eine Wiederherstellung durchführen müsst oder ihr versehentlich ein Update gemacht habt und keinen SHSH Hash der alten Firmware besitzt.

Für diese Anleitung braucht ihr NICHT die aktuellste iOS auf eurem iPhone und funktioniert auch ohne Jailbreak.

Ladet jedesmal wenn Apple eine neue Firmware veröffentlicht die TinyUmbrella Datei neu von dieser Seite herunter und führt eine Sicherung durch.

**UPDATE**: Seit neustem sollten auch iPhone 3G Besitzer den SHSH-Blob sichern, da nun auch eine “soft” SHSH-Überprüfung eingeführt wurde.

---

### Software fürs SHSH-Backup:

- [TinyUmbrella 6.01.00 (archiviert)](http://web.archive.org/web/20130116140905/http://cache.firmwareumbrella.com/downloads/tinyumbrella-6.01.00.exe) (Windows)
- [TinyUmbrella 6.01.00 (archiviert)](http://web.archive.org/web/20130116140816/http://cache.firmwareumbrella.com/downloads/TinyUmbrella-6.01.00.app.zip) (Mac)

---

### Anleitung zum Sichern des SHSH Blob mit TinyUmbrella:

1. Ihr braucht mindestens **iTunes 9.0**
2. Schließt euer iPhone an.
3. **Ladet **die **TinyUmbrella **Datei herunter (je nach dem was für ein System ihr habt) und **startet** das Programm.
4. Klickt in der **linken Liste euer Gerät aus (1)**, geht auf den Reiter **Advanced (2)** und deaktiviert **Request SHSH From Cydia (3)** um den aktuellsten Blob zu sichern.
5. Klickt dann auf **Save SHSH (4) **und wartet kurz. Euer SHSH-Blob ist nun lokal bei euch gespeichert.
[![tinyumbrella-description](//picdump.thafaker.de/2012/09/tinyumbrella-description-580x393.jpg)](http://picdump.thafaker.de/2012/09/tinyumbrella-description.jpg)
6. Wechselt in den Reiter **General** und kontrolliert kurz ob euer aktuellste SHSH-Blob gesichert wurde. Solltet ihr auf **Cydia** auch noch ältere Blobs gesichert haben, so habt ihr die Möglichkeit diese auch noch auf euren Rechner zu holen, indem ihr **Request SHSH From Cydia** aktiviert und nochmals auf **Save SHSH** klickt.

---

### Wiederherstellen einer älteren iOS mit TinyUmbrella (iPhone 3GS / iPhone 4):

[UPDATE] Um einen Downgrade für ein **iPhone 4S** durchzuführen, müsst ihr [dieser Anleitung](__GHOST_URL__/howto-downgrade-ios-5-1-1-auf-ios-5-0-1-iphone-4s-ipad2-anleitung/) folgen.

Sollte in Zukunft eine aktuellere iOS Version zur Verfügung stehen als die, die ihr wiederherstellen oder downgraden wollt, so sollte das kein Problem sein, vorausgesetzt ihr habt den SHSH Blob!

1. Schließt euer iPhone an euren Computer an
2. Startet **TinyUmbrella**
3. Wählt in der linken Liste euer Gerät aus
4. Klickt auf **Start TTS Server**, kontrolliert ob **TinyUmbrella’s TTS server is running** darunter steht
5. Schließt euer iPhone an den Computer an, versetzt es in den **DFU-Modus **und startet **iTunes**.
6. Im iTunes auf Wiederherstellen mit “Shift + Linksklick” (Windows) oder “Alt + Linksklick” (Mac) und die gewünschte **iOS Firmware **auswählen.
![itunes-wiederherstellen](//picdump.thafaker.de/2012/09/itunes-wiederherstellen.jpg)

Das wars auch schon wieder, bis bald :)

Sollte euch die Anleitung gefallen haben, könnt ihr mich unterstützen indem ihr einfach mal ordentlich durchflattert. Danke.
