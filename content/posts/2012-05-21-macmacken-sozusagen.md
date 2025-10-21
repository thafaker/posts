---
title: Macmacken, sozusagen - UUID nach Festplattenwechsel wieder an TimeMachine Backup angleichen
slug: macmacken-sozusagen
date_published: 2012-05-21T14:38:37.000Z
date_updated: 2018-08-22T09:38:08.000Z
---

[![timemachine symbol](//picdump.thafaker.de/2012/05/timemachine-125x125.png)](http://picdump.thafaker.de/2012/05/timemachine.png)In Anlehnung eines Weblogs was es nicht mehr gibt, verwende ich den Titel um mich über eine Unart von TimeMachine aufzuregen. TimeMachine ist Apples eigenes Backup-System, welches besonders einfach und Benutzerfreundlich inkrementelle Backups am laufenden Band erstellt und bei Bedarf einzelne Dateien aus verschiedenen Epochen wiederherzustellen vermag. Auch kann man sein OSX vollständig neu aufsetzen und mit TimeMachine den Zustand vor der Neuinstallation wiederherstellen. 

Und da beginnt auch schon mein Problem. Eigentlich hat TimeMachine keine Probleme damit, den selben Mac und die gleiche Festplatte dem bereits vor der Neuinstallation vorhandenen Backup zuzuordnen, die geschieht über Name, UUID der Partition sowie der MAC-Adresse der Netzwerkkarte(n).

Ich habe nun ein laufenden TimeMachine Backup auf meiner externen FW800 LaCie, dieses habe ich auch verwendet um meinen iMac komplett neu aufzusetzen. Die 500GB der externen Platte sind bis zu 450GB prall gefüllt, sodass noch etwa 50GB für weitere Daten frei bleiben.

Wer schon mal ein vollständiges TimeMachine-Backup angelegt hat der weiß, wie lange schon 500GB Daten zur Sicherung brauchen. Egal, nun zu meinem eigentlichen Problem: nach der Neuinstallation und der Wiederherstellung war nun meine törichte Idee, mein vorhandenes Backup einfach weiter laufen zu lassen, es ist ja da wie bisher und es hat sich nichts an meinen Inhalten geändert, außer eben, dass ich ein mal neu installiert habe. Aber PUSTEKUCHEN. Wenn man nämlich seine Systempartition neu erstellt, also löscht oder auch neu partitioniert, dann gibt's auch ne neue UUID, ne eindeutige Kennung der Partition. Diese benutzt auch TimeMachine um das Backup dem jeweiligen Mac zuzuordnen. Tja... bei mir gabs ne neue UUID und deshalb ist für TM mein bisheriges Backup nicht mehr mit meinem iMac kompatibel. FUCK. In einer FAQ heißt es zu meinem Problem folgendermaßen:

**Was passiert, wenn ich das Startvolume oder eine andere Festplatte lösche?** Beim Löschen einer Festplatte wird eine neue UUID vergeben. Für Time Machine ist die gelöschte Platte anschließend **ein völlig neues Gerät, für das ein eigenes neues Verzeichnis angelegt wird**. Das alte Verzeichnis samt Daten bleibt erhalten, kann aber eben nicht mehr weiter genutzt werden.

[![TimeMachine Backup nach Formatierung neue UUID keine Zuordnung mehr](//picdump.thafaker.de/2012/05/Bildschirmfoto-2012-05-21-um-16.32.43-580x447.png)](http://picdump.thafaker.de/2012/05/Bildschirmfoto-2012-05-21-um-16.32.43.png)

Hier noch mal die Fehlermeldung, welche meine Vermutung nun sehr zu 100% bestätigt.

> Backing up to: /Volumes/Timemachine/Backups.backupdb
> Event store UUIDs don't match for volume: System

Um Fehlermeldungen von TimeMachine ohne größere Probleme (das Programm nutzt das System.log) angezeigt zu bekommen, empfiehlt sich das kleine und kostenlose [TIME MACHINE BUDDY (archiviert)](http://web.archive.org/web/20120621234952/http://www.bluedog.com.au:80/default/Time_Machine_Buddy.html), ein Dashboard-Widget was den Zweck hat, das TimeMachine Log anzuzeigen.

[Hier (archiviert)](http://web.archive.org/web/20110810083541/http://www.tiramigoof.de:80/wordpress/?p=5362) habe ich eine ausreichende Ressource gefunden, die sich mit den Vorzügen und einer Art FAQ zu TimeMachine auszeichnet.

Es gibt also keine Chance mehr für mich und mein bisheriges Update. Ich muss es komplett neu erstellen lassen...

---

[**UPDATE**] Wer suchet, der findet. Beim [Simon](http://simon.heimlicher.com/articles/2011/02/18/time-machine-volume-uuid) habe ich eine Möglichkeit gefunden, die UUID nachträglich zu ändern oder quasi an die neue UUID angleichen zu lassen, sodass OSX wieder mitspielt. YEAH - es funktioniert.

Der heilige Befehl um trotz veränderter UUID oder sonst einem Grund einem alten Backup einen neuen iMac zuzuordnen ist also folgender:
`sudo tmutil associatedisk -a...`

So sieht es bei mir aus:

    sudo tmutil associatedisk -a /Volumes/aktuelle_Festplatte/ /Volumes/deine_TimeMachine/Backups.backupdb/der_Name_deines_Macs/Latest/die_bisherige_SystemPlatte/

Großartig, ich kann also mein altes TimeMachine-Backup völlig problemlos weiter verwenden, Apple hat da also diesen `tmutil` Command direkt deswegen eingebaut. Ich bin sehr froh, dass ich dieses Hinweis noch gefunden habe und hoffe, er nützt jetzt auch anderen Leuten, denn, ich wollte die 500 GB nicht noch mal neu kopieren, zumal mein Volume eben voll ist und ich das Alte hätte komplett löschen müssen, wobei mir wichtige Daten verloren gegangen wären, da ich jetzt die ein oder andere Sache noch nicht wiederhergestellt habe - sie ist ja im Backup.

PS: Dieser Befehl funktioniert erst ab OS X Lion 10.7, für 10.6 gibt es aber selbst gebastelte Scripts und andere Tricks, die man anwenden muss, aber auch dann soll es problemlos funktionieren - auf eigene Gefahr ;-)

PS: Hier noch mal zwei Screenshots, so sah es aus, als TimeMachine ein vollständig neues Backup anlegen wollte:
[![TIMEMACHINE not_working](//picdump.thafaker.de/2012/05/not_working-580x447.png)](http://picdump.thafaker.de/2012/05/not_working.png)

Und so sieht es nun aus, seitdem ich mit dem tmutil Command die UUID angeglichen und TimeMachine gesagt habe, mach das Backup aufs alte Volume, führe es weiter von der neuen Platte aus, quasi.

[![IS_WORKING](//picdump.thafaker.de/2012/05/IS_WORKING-580x447.png)](http://picdump.thafaker.de/2012/05/IS_WORKING.png)

*Und dann... dann macht OS X selbst in Version 10.7 plötzlich wieder Spaß und lässt ein richtiges Betriebssystem unter der mehr und mehr durch iOS verschandelten Oberfläche erkennen...*
