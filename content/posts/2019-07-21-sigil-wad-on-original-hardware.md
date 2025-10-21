---
title: How to run JOHN ROMERO'S SIGIL MEGAWAD for DOOM on originale hardware
slug: sigil-wad-on-original-hardware
date_published: 2019-07-21T19:24:36.000Z
date_updated: 2019-11-26T16:52:27.000Z
tags: sigil, doom, sigil.wad, doom.wad, vintage computing, retro computing
---

Ihr wisst ja, ich habe die Veröffentlichtung von **SIGIL**, der inoffiziellen DOOM-Erweiterung zum 25-jährigen Jubiläum des Spiels, [immer mal wieder](__GHOST_URL__/sigil-wad-on-original-hardware/OS/2%20Warp%204.52%20im%20Einsatz) begleitet und darüber geschrieben. Bis es dann endlich offiziell zum Download durch John Romero, den Erfinder von DOOM, zur Verfügung gestellt wurde. Und lud es ebengleich herunter…

Ich habe SIGIL dann mit GZDoom (eine Art Emulator) unter macOS gespielt und mich ([Anleitung hierzu](__GHOST_URL__/sigil-doom-kostenlos-download/)) daran erfreut, all die Zeit aber darüber nachgedacht, es auf original Hardware, sprich meinem [Vintage DOS 6.22 PC](__GHOST_URL__/vintage-pc-mit-dos-6-22-und-windows-3-11-und-os-2-warp/), zu spielen. Und nun habe ich die Zeit gefunden und mein Vorhaben endlich in die Tat umgesetzt, aber lest selbst :-) 

### SIGIL on vintage Hardware DOS 6.22 DOOM.WAD
![](__GHOST_URL__/content/images/2019/07/sigil_dos-1.JPG)SIGIL.WAD on DOOM 1 running on a MS-DOS 6.22 Vintage PC
Die originale DOOM Engine kann SIGIL nicht wirklich gut abspielen, zu viele Objekte im Spiel sorgen dafür, dass die Engine mit einem Fehler abbricht. 
`R_FindPlane: No more visplanes`
Hier gibt es eigentlich keine Möglichkeiten, da SIGIL einfach höhere Ansprüche stellt und eben mit einer moderen Engine wie GZDOOM gespielt werden möchte. Aber es gibt mehr… nämlich die 1999er OpenSource Implementierung mit dem schönen Namen BOOM. Damit sollte es klappen :-)

1. Ladet euch BOOM [hier (archiviert)](http://web.archive.org/web/20190831040329/https://www.doomworld.com/idgames/themes/TeamTNT/boom/boom202) herunter und entpackt es 
2. Ladet euch SIGIL [hier](https://www.romerogames.ie/si6il) herunter und entpackt es
3. kopiert eure originale DOOM.WAD aus Doom in das Verzeichnis von BOOM
4. kopiert die Datei `SIGIL_COMPAT.wad` in den Ordner von BOOM, denkt allerdings daran dass DOS nur 8.3 Zeichen im Dateinamen kann, benennt die Datei also vorher um, z.B. in `sigilcom.wad`
5. Startet im BOOM Verzeichnis die Datei asetup.exe um eure Soundkarte einzustellen.
6. Startet das Spiel mit folgendem Befehl: `BOOM.EXE -FILE SIGILCOM.WAD`

SIGIL on real Hardware Vintage PC
*Viel Spaß am Gerät*.

[**UPDATE**] Leider habe ich einen Fehler, der das Spiel abbricht und den ich aktuell nicht beheben kann.
![](__GHOST_URL__/content/images/2019/07/error.jpg)SIGIL.WAD BOOM Error
