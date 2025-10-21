---
title: Amiga 1200 Diskettenlaufwerk Chinon FZ-357 seltsames Verhalten
slug: amiga-1200-diskettenlaufwerk-chinon-fz-357-seltsames-verhalten
date_published: 2024-02-11T18:34:54.000Z
date_updated: 2024-02-11T18:34:54.000Z
tags: Chinon FZ-357, amiga 1200, vintage computing
---

Ich betreibe einen Amiga 1200 mit ACA 1233N Turbokarte und neuen 3.2.2 Kickroms von *Hyperion* nebst Amiga OS 3.2.2.1. Mein Amiga ist gebraucht und wurde mit einem **Chinon FZ-357** Diskettenlaufwerk geliefert. Wenn ich den Amiga mit eingelegter, bootfähiger Diskette (Spiel etc.,) starte, bootet er korrekt vom Laufwerk. Auch wenn ich eine Diskette mit Dateien im Laufwerk, während ich das Gerät einschalte, habe, wird diese Diskette korrekt unter der Workbench angezeigt. Lasse ich aber das Laufwerk leer dann erhalte ich unter der Workbench immer den Fehler "DF0: Unlesbar". Lege ich dann eine Diskette ein, wird diese nicht erkannt/geladen. Das heißt, das Diskettenlaufwerk funktioniert prinzipiell, aber es funktioniert nicht richtig unter der Workbench. Ich habe/höre auch keinen Click. Ansonsten funktioniert der Amiga einwandfrei. Kann es eine Einstellung am Diskettenlaufwerk sein? Ist es gar nicht kompatibel sondern ein PC-Umbau? 

Was ich schon probiert habe:

- testweise die originalen Kickroms 3.0
- neues System aufgesetzt
- anderes Netzteil verwendet: keine Abhilfe, das Problem besteht einfach immer.
- Der Amiga ist recapped.

[**LÖSUNG**] Tatsächlich war der sogenannte Taster am Diskettenlaufwerk, er erkennt, dass eine Diskette eingelegt ist, über die Jahre verdreckt und hat dauerhaft eine eingelegte Diskette an das System gemeldet. Eine ordentliche Säuberung des Tasters mit Isopropanol schaffte Abhilfe, nun funktioniert das Laufwerk wie zu erwarten, auch der Click funktioniert wieder. Vielen Dank an das A1K Forum, welches mit den [Tipp mit dem Taster](https://www.a1k.org/forum/index.php?threads/90496/) gab.
![Taster an einem Chinon FZ-357 Diskettenlaufwerk](__GHOST_URL__/content/images/2024/02/IMG_7609.jpeg)Taster an einem Chinon FZ-357 Diskettenlaufwerk![Taster an einem Amiga Diskettenlaufwerk (C) xpoole](__GHOST_URL__/content/images/2024/02/maxresdefault.jpg)Taster an einem Amiga Diskettenlaufwerk (C) [xpoole](https://www.a1k.org/forum/index.php?members/7478/)
## Diskettenlaufwerke am Amiga

Bei den Diskettenlaufwerken für den Amiga handelt es sich um 3,5„ DD-Laufwerke mit einer Datenrate von 500KBit pro Sekunde. Die Umdrehungsgeschwindigkeit beträgt 300RPM. Diese Daten sind identisch mit 720KByte-Laufwerken für den PC. Tatsächlich formatiert der Amiga die Diskette jedoch mit 880KByte pro Diskette. Dieser Vorteil wird erreicht, weil der Amiga nicht nur einzelne Sektoren, sondern immer ganze Tracks auf die Diskette schreibt. Ein PC-Diskettenlaufwerk ist jedoch nicht ohne weiteres zum Amiga kompatibel. Manche Laufwerke kann man umbauen.

Der Amiga verwendet eine Shugart-ähnliche Floppy-Schnittstelle. Anders als die meisten PCs nutzt der Amiga das Diskchange-Signal um zu erkennen, ob eine Diskette eingelegt ist oder nicht. Dieses Signal lag bei mir nicht mehr richtig an, da der Taster es nicht mehr senden konnte. Das Signal wird vom Laufwerk gespeichert: Wird eine Diskette herausgenommen und wieder eingelegt, meldet das Laufwerk immer noch „Diskette entnommen“. Erst wenn der Schreib/Lese-Kopf einen Schritt bewegt wurde, wird der Zustand der Diskchange-Leitung aktualisiert. Auf diese Weise kann der Computer einen Wechselvorgang nicht verpassen, egal wie schnell er ausgeführt wurde. [[Amiga Wiki](https://www.amigawiki.org/doku.php?id=de:expansion:storage:disk_drive)]
