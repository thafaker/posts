---
title: [ROOTING] Galaxy S4 mit Snapdragon rooten
slug: root-galaxy-s4-mit-snapdragon-rooten
date_published: 2013-04-27T13:29:21.000Z
date_updated: 2018-08-22T09:38:48.000Z
---

![samsung-galaxy-s4](//picdump.thafaker.de/2013/04/samsung-galaxy-s4-100x100.jpg)Da das unter Android laufende nagelneue Galaxy S4, was es erst seit 2 Tagen gibt, bereits gerootet (gejailbreakt) werden kann, ist dies Grund genug, die Vorgehensweise dazu kurz zu beschreiben.

Der Exploit stammt von der gleichen Person, die auch die Motorola Bootloader Unlocks realisiert hat. Die Vorgehensweise ist zwar komplizierter als eine One-Click-Lösung, aber noch einfach genug, damit sie jeder durchführen kann.

Der Root Zugriff ist bisher nur für Galaxy S4 Varianten mit Snapdragon Chipsatz erhältlich, das sollte hierzulande aber keinen stören, da es die Variante ist, die hier verkauft wird.

Das Rooting funktioniert nur mit der Buildnummer XXUAMD2; aktuell ist allerdings bereits Buildnummer XXUAMDM. Mit der funktioniert der Exploit nicht mehr. Wenn ihr auf dem neuen Build hockt und rooten wollt, müsst ihr mit **Odin** zurück.

1. Alle Inhalte der [**ZIP-Datei** (archiviert)](http://web.archive.org/web/20130828045258/http://vulnfactory.org/public/motochopper.zip) ([Mirror (archiviert)](http://web.archive.org/web/20250905094406/https://mega.co.nz/)) extrahieren.
2. Sicher gehen, dass die neuesten [Samsung USB Treiber (archiviert)](http://web.archive.org/web/20120910004533/http://www.samsung.com:80/us/support/downloads/SGH-i907) installiert sind, wenn Windows genutzt wird.
3. USB Debugging muss auf dem Gerät aktiviert sein. Geht dazu auf Einstellungen --> Anwendungen --> Entwicklung --> dort USB Debugging das Häkchen setzen
4. Gerät über USB mit dem PC verbinden.
5. Unter Windows in das Extraktionsverzeichnis gehen und die “run.bat” Datei ausführen. Linux oder OSX Nutzer rufen im entpackten Ordner im Terminal `./run.sh` aus.
6. ADB Verbindung vom PC auf dem Gerät erlauben.

Das wars auch schon wieder, bis bald.
