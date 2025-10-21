---
title: [HOW TO] How to make a bootable OS X 10.11 Boot Stick - El Capitan
slug: how-to-how-to-make-a-bootable-os-x-10-11-boot-stick
date_published: 2015-10-04T08:36:44.000Z
date_updated: 2019-04-05T10:07:10.000Z
tags: how to, howto, anleitung, el capitan, os x 10.11, boot stick, bootable
---

Da seit ein paar Tagen das neue **OS X 10.11***El Capitan* Betriebssystem von Apple zum kostenlosen Download bereit steht, möchten wir an dieser Stelle kurz beschreiben, wie ihr einen bootfähigen USB Stick bekommen. Dies ist wichtig wenn ihr 

- eine Clean-Install durchführen wollt
- kein Internet zur Verfügung habt
- die HDD austauscht

etc. pp. Die Liste könnte endlos sein und es empfiehlt sich sowieso immer, einen bootfähigen Stick zu haben. Auch als Rescue falls das System mal ausgefallen ist.

#### Vorbereitung

Ihr benötigt nicht viel, aber doch einiges.

1. OS X 10.11 Installer (**[DOWNLOAD (archiviert)](http://web.archive.org/web/20151212074317/https://itunes.apple.com/app/os-x-yosemite/id1018109117)**) (6.08 GB)
2. USB Stick mit mindestens 8 GB Größe

2.1 sollte frisch formatiert sein
3. Administrator-Rechte als Benutzer

#### Anleitung

1. Schließt den Stick an euren Mac an
2. öffnet das Terminal
3. kopiert folgenden Code und tragt ihn in euer Terminal ein:

---

`sudo /Applications/Install\ OS\ X\ El\ Capitan.app/Contents/Resources/createinstallmedia --volume /Volumes/**Untitled** --applicationpath /Applications/Install\ OS\ X\ El\ Capitan.app --nointeraction`

---

ACHTUNG Wobei das Wort **Untitled** mit der Bezeichnung eures Sticks ausgetauscht werden muss, ohne die **. Mein Stick heißt "ElCapInstaller" und so trage ich dies dort ein.

[![thafaker el capitanthafaker el capitan install screenshot](/content/images/2015/10/Bildschirmfoto-2015-10-04-um-11-24-43.png)

1. 
Sollte es mit dem Kopieren und Einfügen des oben aufgeführten Befehls Probleme geben, lässt sich die Syntax durch Eingabe der ersten Zeichen wie /Ap und der Betätigung der Tab-Taste automatisch vervollständigen. Die Erstellung benötigt ca. 10 Minuten, je nach Geschwindigkeit eures Sticks.

2. 
Anschließend startet man den Mac neu und hält die -Taste gedrückt, sodass ihr das Bootmenü seht.

3. 
Hier wählt ihr den Stick aus und der normaler Installer startet. Haut euch den Käpt'n auf die Platte, fertig.

*Bis bald.*
