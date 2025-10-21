---
title: OSX FUSE ist das neue MacFuse
slug: osx-fuse-ist-das-neue-macfuse
date_published: 2012-06-15T19:04:27.000Z
date_updated: 2018-08-22T09:39:16.000Z
---

![OS X FUSE](//picdump.thafaker.de/2012/06/Bildschirmfoto-2011-09-12-um-12.22.27-100x100.jpg)Ich musste mich heuer mal wieder mit Fuse unter OSX beschäftigen, weil ich eine ältere 1TB HDD mit allerlei Unrat und vergessenen Daten abchecken wollte. Lesend ist das unter OSX übrigens überhaupt kein Problem, aber wenn man auch Daten auf das NTFS-Laufwerk schreiben oder löschen möchte, dann stößt man an OS X ihre Grenzen. Schreibsupport besteht nämlich für NTFS nicht. Und NTFS ist aber der absolute Standard in der Windows-Welt. Mist. In der Vergangenheit berichtete ich schon öfter mal hier und dort über die kostenlose Allzweckwaffe [MacFuse](http://code.google.com/p/macfuse/), doch die inoffizielle *Version 2.1.9* führt bei einigen Benutzern zu Abstürzen, Zitat: ”Die inoffizielle MacFUSE Version 2.1.9 ist nicht voll kompatibel mit Mac OS X Lion! MacFUSE-Laufwerke können wie im Fall von NTFS-3G mit dem Finder nicht beschrieben werden (mit dem Terminal geht es) und bei vielen gleichzeitigen Zugriffen auf das Laufwerk kann das Dateisystem “abstürzen”.
![OS X FUSE](//picdump.thafaker.de/2012/06/Bildschirmfoto-2011-09-12-um-12.22.27.jpg)
Die Lösung: **OSXFUSE**. [OSXFUSE (archiviert)](http://web.archive.org/web/20110923231122/http://osxfuse.github.com:80/) ist das “neue” MacFUSE. Es macht da weiter, wo MacFUSE aufgehört hat, ist also auch voll kompatibel zu MacFUSE, löst die genannten Probleme und wird aktiv weiter entwickelt.” Ist also scheinbar ein aktiver Fork des Ganzen.

NTFS 3G funktioniert bei mir leider auch mit OS X Fuse nicht. Die [NTFS-3G](http://macntfs-3g.blogspot.de/) Macher bieten allerdings eine zu Lion kompatible, kommerzielle Version ihres Treibers an. Was macht ihr, damit ihr vollen Schreib/Lesezugriff auf große NTFS-Laufwerke erhaltet? Gibt es unter umständen einen Trick?

Mit Fuse kann man übrigens noch viel mehr als nur NTFS Support einbauen, denkbar sind eigentlich alle Dateisysteme wie auch EXT3 ((aus der Linux-Welt)) oder Crypto-Filesystems sowie sogar eine SSH-Verbindung als Laufwerk.

**DOWNLOAD**

- [OSX Fuse 2.4.2 (Link nicht mehr verfügbar)](https://github.com/downloads/osxfuse/osxfuse/OSXFUSE-2.4.2.dmg)
