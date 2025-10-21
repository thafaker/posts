---
title: Neuer Backdoor ist Cross-Platform und kann neben OS X auch Win und Lin [UPDATE]
slug: neuer-backdoor-ist-cross-platform-und-kann-neben-os-x-auch-win-und-lin
date_published: 2012-07-14T09:05:36.000Z
date_updated: 2018-08-22T09:37:37.000Z
---

![cccebit_bundestrojaner](//picdump.thafaker.de/2008/11/cccebit_bundestrojaner-150x150.png)Endlich gibt es mal wieder einen Aufschrei auch im OS X Sicherheitslager. Langsam entwickeln sich die Viren auch für OS X und erfahren ein größeres Interesse weil auch die Nutzung der Plattform langsam aber stetig steigt. Laut einem [Blog-Eintrag](http://www.f-secure.com/weblog/archives/00002397.html) von Karmina Aquino, Senior Analyst bei F-Secure, hat das F-Secure Team auf einer kolumbianischen Webseite eine Malware aufgespürt, die den Besucher auffordert, ein Zertifikat von »ComuTv« zu bestätigen. 

Screenshots im Blog-Eintrag demonstrieren den Ablauf des Angriffs zwar nur unter Windows, eine im Blog ebenfalls dokumentierte Analyse der JAR-Datei zeigt aber anschaulich, wie der Angriff im Detail funktioniert und dabei alle drei Plattformen »bedient«. Demnach prüft die JAR-Datei zunächst, welches Betriebssystem auf dem Rechner läuft und lädt dann den passenden Schädling für Windows, Mac OS X oder Linux herunter, denn das zuständige Code-Fragment enthält auch ein unter Unix funktionierendes If-Statement, samt Verweis auf die für Unix/Linux passende Binärdatei.

Die drei Dateien für die unterschiedlichen Plattformen zeigen dabei ein identisches Verhalten und verbinden sich zu den IP-Adressen von 186.69.87.249 bis 186.87.69.249, von der sie sich weiteren Code zur Ausführung besorgen. Dabei werden die Ports 8080, 8081 und 8082 benutzt.

Es empfiehlt sich also wieder einmal, nicht bedenkenlos auf alles zu klicken, was darum bittet. [[Weiterlesen](http://www.pro-linux.de/news/1/18601/neue-cross-plattfom-backdoor-betrifft-auch-linux.html)]

[**UPDATE**] Das Binary für OS X ist übrigens noch ein uraltes fürn PowerPC, unter OS X braucht man zum Ausführen also Rosetta - und das gibt's für Lion schon gar nicht mehr, soweit ich weiß. Die Gefahr ist also recht gering würde ich sagen.
![intel](//picdump.thafaker.de/2012/07/intel.png)
