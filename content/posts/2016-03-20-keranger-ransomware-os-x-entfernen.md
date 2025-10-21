---
title: [ANLEITUNG] KeRanger Ransomware OS X entfernen
slug: keranger-ransomware-os-x-entfernen
date_published: 2016-03-20T10:59:55.000Z
date_updated: 2018-08-22T09:39:28.000Z
tags: keranger, os x, anleitung, howto, how to, transmission, bittorrent, Erpressungs-Trojanern, Erpressung, entfernung, ransomware
---

Wir hatten erst [kürzlich](__GHOST_URL__/eilt-erste-ransomware-fur-os-x-ist/) über den ersten *Verschlüsselungstrojaner* unter OS X berichtet, die sogenannte *Ransomware***KeRanger**. Es ist klar, dass dieser sich über die kompromittierte Software "Transmission", einen OS-X Client für das Bittorrent-Netzwerk, einschleust. 

Die Server des Softwareherstellers waren kompromittiert und so konnte die infizierte Version dort abgelegt - und von ahnungslosen Benutzern herunter geladen und installiert / infiziert werden.

![](__GHOST_URL__/content/images/2016/03/mac-os-x-ransomware-1.png)

*Soweit - so gut*! Ist man infiziert, hat man meist drei Tage zeit, bis die Software aktiv wird und die Festplatte verschlüsselt. Generell sollte man nachsehen, ob man sich den Schädling eingefangen hat, da niemals klar sein kann, ob tatsächlich nur diese eine Version 2.90 von Transmission betroffen war, oder der Trojaner (vielmehr seine Entwickler) auch andere Wege gefunden hat/haben.

### Anleitung **KeRanger** entfernen

Über das Programm Aktivitätsanzeige (im Ordner Dienstprogramme) lässt sich prüfen, ob der Mac bereits von KeRanger infiziert wurde: man sucht dort im Reiter "CPU" nach einem Prozess mit dem Namen `kernel_service` und – falls vorhanden – beendet diesen über den Button mit dem kleinen x, der sich in der linken oberen Ecke befindet.

![Aktivitätsanzeige OS X 10.11.3](__GHOST_URL__/content/images/2016/03/Bildschirmfoto-2016-03-20-um-11-45-30.png)

Zudem sollte man prüfen, ob die Dateien `.kernel_pid`, `.kernel_time` und `.kernel_complete` oder `.kernel_service` im Verzeichnis `~/Library` vorhanden sind. Ist dies der Fall, sollten sie gelöscht werden.

Um die Dateien zu sehen, muss man erst die Darstellung für versteckte Dateien im Finder aktivieren. Dies geht im Terminal mit dem Befehl:
`defaults write com.apple.finder AppleShowAllFiles TRUE`

gefolgt von:
`killall Finder`

Anschließend öffnet man mit gedrückter alt-Taste im Finder-Menü "Gehe zu" die Library. Um die versteckten Dateien wieder auszublenden, gibt man den Befehl:
`defaults write com.apple.finder AppleShowAllFiles FALSE`

im Terminal ein und bestätigt diesen mit der Eingabetaste. Anschließend folgt wieder
`killall Finder`

Dies startet den Finder mit den erteilten Änderungen neu.

*Viel Erfolg*.

([via](http://www.heise.de/mac-and-i/meldung/Erpressungs-Trojaner-KeRanger-Wie-Sie-Ihren-Mac-schuetzen-3130854.html))
