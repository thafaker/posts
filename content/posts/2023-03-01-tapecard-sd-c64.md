---
title: C=64 mit Tapecard SD
slug: tapecard-sd-c64
date_published: 2023-03-01T13:18:07.000Z
date_updated: 2023-12-07T09:51:35.000Z
tags: c64, vintage computing, vintage games
---

Bei mir hat sich, so trug es sich zu, ein kleiner Brotkasten den Weg in meine Vintage Ecke gebahnt. Ein **C=64** im ursprünglichen Look mit einem Diskettenlaufwerk **VC 1541** am Monitor **1084S **- Großartig.
![Tapecard SD](__GHOST_URL__/content/images/2023/03/IMG_0776.jpg)Tapecard SD
Aber wie das so ist, macht es mir immer auch große Freude die neuen technischen Finessen auszuprobieren die für die alten Computer in kleinen Homebrewauflagen überall entwickelt werden - und zunächst benötige ich etwas einfaches, um Daten hin und her schaufeln zu können. Es gibt ein Projekt für den Tape-Port, das sogenannte **TapeCard SD** ([Link](https://github.com/KimJorgensen/tapecart)). Es läuft mit einem kleinen Adruino, kostet ungefähr 35 € und lädt pfeilschnell. Bestückt mit einer FAT 32 formatierten Micro SD Card hat man den idealen Zustand, Dateien zu kopieren. Integriert ist ein kleiner Filebrowser mit welchem man durch die Software auf der SD Karte wechseln kann.
![Tapecard SD Modul](__GHOST_URL__/content/images/2023/02/IMG_0774.jpeg)Tapecard SD Modul
Das ganze funktioniert so gut, dass ich es aufschreiben muss. Und die Geschwindigkeit, im Gegensatz zu dem Standarddiskettenlaufwerk, ist atemberaubend. Und so einfach. Und man benötigt nicht mal extra Strom, das Teil ist *Buspowered*, anstecken: **läuft**.

1. Micro-SD-Karte mit FAT 32 formatieren
2. Software kopieren (Wurde bei mir auf CD mitgeliefert)
3. browser.prg muss direkt auf der Karte liegen, in keinem Ordner. Sonst bleibt der C64 mit der "*Press Play On Tape*" Meldung stehen.
4. Den TapeCard SD an den C=64 Datasette-Anschluss anstecken
5. Alles einschalten
6. SHIFT + RUN drücken
7. Läuft los, Bildschirm wechselt die Farbe, findet Filebrowser, startet
8. et voila…

Ich habe ein kleines Video gedreht. Dazu habe ich eine SD-Karte formatiert, die browser.prg und das Spiel Gianna Sisters kopiert und starte es direkt auf dem C=64.
thahipster.de tapecard sd on c=64
## Ressourcen

- [TapeCard SD GitHub Repo](https://github.com/KimJorgensen/tapecart)
- [[L](https://github.com/KimJorgensen/tapecart/releases)atest release](https://github.com/KimJorgensen/tapecart/releases)
- …
