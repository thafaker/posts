---
title: Wo liegen eigentlich die von iTunes herunter geladenen Firmwares?
slug: wo-liegen-eigentlich-die-von-itunes-herunter-geladenen-firmwares
date_published: 2016-09-17T09:20:42.000Z
date_updated: 2018-08-22T09:37:38.000Z
tags: ispw, firmware, ios, download, ssd, tutorial, how to, howto, anleitung, wie geht
---

Meine SSD ist ständig voll. Also bin ich häufig auf der Suche nach Speicherfressern. Und vorhin, als ich so durch den Kies stapfte, kam in mir die Frage auf, was eigentlich mit den iOS-Update-Files passiert, wenn ich mein iDevice über iTunes aktualisiere? Wo landet die Firmware, die diesbezüglich herunter geladen wird? Und wird die auch wieder gelöscht? 

![](__GHOST_URL__/content/images/2016/09/Custom-Firmware-Restore.jpg)

Ich machte mich also auf die Suche und fand den Pfad, unter Mac OS X werden die Dateien folgendermaßen gespeichert:

### Mac OS X
**iPhone**~/Library/iTunes/iPhone Software Updates**iPad**~/Library/iTunes/iPad Software Updates**iPod touch**~/Library/iTunes/iPod Software Updates
**Beachte**: Das tilde "~" ist dein Home-Verzeichnis.

Man öffnet also einfach seine Terminal.app, wechselt mit cd `~/Library/iTunes/` ins betreffende Verzeichnis, tippt `open .` ein und schon öffnet sich der Finder und man sieht die Dateien darin. Bei mir lagen gute 4GB an alten iOS Firmware Dateien darin. Schnell gelöscht, etwas Platz.

### Windows XP
**iPhone**C:\Documents and Settings\[username]\Application Data\Apple Computer\iTunes\iPhone Software Updates**iPad**C:\Documents and Settings\[username]\Application Data\Apple Computer\iTunes\iPad Software Updates**iPod touch**C:\Documents and Settings\[username]\Application Data\Apple Computer\iTunes\iPod Software Updates
### Windows Vista, 7, and 8
**iPhone**C:\Users\[username]\AppData\Roaming\Apple Computer\iTunes\iPhone Software Updates**iPad**C:\Users\[username]\AppData\Roaming\Apple Computer\iTunes\iPad Software Updates**iPod touch**C:\Users\[username]\AppData\Roaming\Apple Computer\iTunes\iPod Software Updates
Da kann man ja ruhig mal reinschauen, ge.

*Bis bald.*
