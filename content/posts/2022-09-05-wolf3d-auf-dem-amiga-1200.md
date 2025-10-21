---
title: Wolfenstein 3D auf dem AMIGA 1200
slug: wolf3d-auf-dem-amiga-1200
date_published: 2022-09-05T17:25:21.000Z
date_updated: 2024-03-01T14:50:05.000Z
tags: retro gaming, retro computing, vintage computing, vintage games, wolfenstein 3d, wolf3d, wolf4amiga
---

*It's retro play time* again und ihr wisst ja wie sehr ich meinen Amiga 1200 mag. Was liegt da also näher als auf ihm eine Runde **Wolfenstein 3D** ([Link](https://de.wikipedia.org/wiki/Wolfenstein_3D)) zu versuchen? Nun, eigentlich nur der Fakt, dass Wolfenstein nicht für den AMIGA veröffentlicht wurde sondern seine größte Berühmtheit aus der PC-DOS-Ära erfährt.

Jedoch ist jemand (der Ungarische Programmierer BSzili)  ebenso ein Wolfenstein-Freund wie ich und hat, nachdem er sah dass Wolfenstein auch auf einem 286er PC läuft und alle existierenden AMIGA-Ports jedoch mindestens einen 68040er Prozessor (definitiv mehr Bums als n 286er, also ein schlechter AMIGA-Port) brauchen, eine Version entwickelt um das Spiel gegen die Nazis auf einem Standard-Amiga 1200 (68020 CPU) lauffähig zu machen. Man benötigt dafür lediglich seinen neuen Amiga-Port (Wolf4Amiga) und die originalen Wolf W6 Dateien der Originalversion, sechs Stück an der Zahl, weil Wolf4Amiga nicht mit der Shareware-Version zusammen arbeitet. 

Das musste ich ausprobieren. Gesagt - getan :)

### Vorbereitung (Minimum):

- 68020 Prozessor mit 14 MHz (Amiga 1200)
- AGA Chipset (Amiga 1200)
- 1 MB Chip RAM
- 2 MB Fast RAM
- 3 MB Festplattenplatz
- Wolf4Amiga aus dem Aminet ([Download](http://aminet.net/package/game/shoot/wolf4amiga))
- Wolfenstein W6 Files 

### Vorgehen

1. Wolf4Amiga aus dem Aminet laden und auf den Amiga übertragen
2. Die Wolfenstein W6 Files (Sowas wie die DOOM.WAD) der Originalversion auf den Amiga übertragen
3. Wolf4Amiga entpacken mit dem Befehl: lha x wolf4amiga.lha
4. In diesen neuen Ordner schieben wir die W6 Dateien
5. Meine sind gezipped, also diese mit dem Befehl unzip w6files.zip entpacken
6. Jetzt liegen im Ordner Wolf4Amiga die Wolfenstein Programmdateien und die sechs W6-Dateien.
7. Jetzt starten wir Wolf4Amiga durch Klick auf den fröhlichen *William „B.J.“ Blazkowicz.*
8. Nun beginnt die automatische Konvertierung der Soundfiles von Soundblaster auf den Paula Soundchip des AMIGA. Das findet nur ein mal statt.
9. Und dauert. Ewig. Auf echter Hardware unfassbar lange. Ich habe das in meinem Video beschleunigt.
10. Ist alles korrekt durchgelaufen startet Wolfenstein 3D nach der Konvertierung und ihr könnte mit Maus und Tastatur spielen.
11. Viel Spaß :)

Hier seht ihr mein kleines Click-Trough-Video zum Spiel. Es funktioniert :) 
Wolf4Amiga Wolfenstein 3D auf Amiga 1200 68020
Als kleinen Benchmark zeige ich euch, wie lange die Umwandlung der Sound-Files auf meinem AMIGA 1200 mit ACA1233n Turbokarte und 68030er CPU mit 40 MHz dauert. *This last a long time.*

`Converting music 0/26  99% [|] 65 secs
Converting music 1/26  99% [/] 53 secs
Converting music 2/26  99% [-] 49 secs
Converting music 3/26  99% [-] 76 secs
Converting music 4/26  99% [] 69 secs
Converting music 5/26  99% [|] 49 secs
Converting music 6/26  99% [|] 68 secs
Converting music 7/26  99% [|] 59 secs
Converting music 8/26  99% [/] 69 secs
Converting music 9/26  99% [] 73 secs
Converting music 10/26  98% [] 10 secs
Converting music 11/26  99% [/] 64 secs
Converting music 12/26  99% [|] 69 secs
Converting music 13/26  99% [-] 62 secs
Converting music 14/26  99% [] 101 secs
Converting music 15/26  99% [|] 34 secs
Converting music 16/26  99% [] 23 secs
Converting music 17/26  99% [-] 84 secs
Converting music 18/26  99% [/] 76 secs
Converting music 19/26  99% [-] 106 secs
Converting music 20/26  99% [/] 67 secs
Converting music 21/26  99% [/] 68 secs
Converting music 22/26  99% [|] 125 secs
Converting music 23/26  99% [/] 22 secs
Converting music 24/26  99% [|] 29 secs
Converting music 25/26  99% [] 78 secs
Converting music 26/26  99% [|] 104 secs`

### Ressources

- [initialer Forum Post](http://eab.abime.net/showthread.php?t=110019)
- weiterer [Foren Post](https://gamesnostalgia.com/download/wolfenstein-3d/4734?t=46570730)
