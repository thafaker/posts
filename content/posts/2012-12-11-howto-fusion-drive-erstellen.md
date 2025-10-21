---
title: [HOWTO] Fusion Drive erstellen
slug: howto-fusion-drive-erstellen
date_published: 2012-12-11T20:58:23.000Z
date_updated: 2018-08-22T09:39:16.000Z
---

Fusion Drive nennt Apple seine neue Festplattentechnik, welche in diesem [Artikel](__GHOST_URL__/fusion-drive-apples-neue-festplattentechnik/) hinlänglich beschrieben wurde. Es stellt sich nun die Frage: Muss ich mir einen neuen Mac kaufen, um davon zu profitieren? Die Antwort ist ganz simpel: Nein! Beim Fusion Drive handelt es sich eigentlich um zwei Laufwerke, die softwaretechnisch zu einem Laufwerk zusammengefasst sind. Es ist also kein spezieller Chip, Chipsatz oder Controller notwendig. Dies bedeutet, das es mit einem etwas älteren Mac durchaus möglich ist, sich ein Fusion Drive zu erstellen, um in den Genuss von Geschwindigkeit und Kapazität zu kommen. Ich selbst habe meinen Late 2009er iMac mit einer SSD ausrüsten lassen und verwende in diesem beide Laufwerke als Fusion Drive. Um euch die Möglichkeit zu geben, auch ein Fusion Drive zu erstellen hat die [Macworld](http://www.macworld.com/article/2014011/how-to-make-your-own-fusion-drive.html) ein schönes Tutorial veröffentlich, auf dem sich dieses HowTo stützt.

[![](//picdump.thafaker.de/2012/12/fudrivehowto-100x100.jpg)](__GHOST_URL__/howto-fusion-drive-erstellen/fudrivehowto/)

Um ein Fusion Drive zu erstellen, sind wie bereits erwähnt zwei Laufwerke notwendig, sinnvollerweise eine SSD und eine normale Festplatte. Die SSD sollte ca. 120 GB haben und als Festplatte verwenden wir entweder die vorher eingebaute oder ein größeres Modell. Des Weiteren sollte der  Mac nicht zu alt sein. Er sollte in jedem Fall Unterstützung für Mac OSX Mountain Lion 10.8.2 bieten, dieses wird nämlich zwingend vorausgesetzt.

**WICHTIG! thafaker.de haftet nicht für eventuelle Schäden oder Datenverluste, die mit dem Nutzen dieses HowTos auftreten sollten! Erstellt in jedem Fall vor dem Erstellen des Fusion Drives ein Timemachine Backup, beziehungsweise sichert eure Daten [anderweitig](__GHOST_URL__/glacier-und-arq-best-longtime-backup-solution-furn-mac/). Beim Erstellen des Fusion Drives werden alle Daten gelöscht!**

Beide Festplatten werden über Apples zentrale Technologie Core Storage zu einem Laufwerk verbunden. Öffnet dazu das Terminal.

**Schritt 1:**

Gebt den folgenden Befehl ein:

> diskutil list

Im Terminalfenster werden nun alle angeschlossenen Laufwerke und Volumes angezeigt.

[![](//picdump.thafaker.de/2012/12/Bildschirmfoto-2012-12-11-um-20.50.48-580x407.png)](__GHOST_URL__/howto-fusion-drive-erstellen/bildschirmfoto-2012-12-11-um-20-50-48/)

Merkt euch hier, welche beiden Laufwerke ihr zusammenfügen wollt. Gebt ihr beim Fusionieren eine falsche Kennung ein, so überschreibt ihr unter Umständen das falsche Laufwerk. Als Laufwerksbezeichnung wählt ihr den Eintrag ganz links (Aufbau: /dev/disk#)

**Schritt 2:**

Verbindet beide Laufwerke zu einem mit dem folgenden Befehl. Wichtig: Den Namen der Volumen Gruppe und Laufwerk 1 und Laufwerk 2 müsst ihr euren Laufwerken anpassen.

> diskutil coreStorage create nameFestlegen Laufwerk1 Laufwerk2

Wollt Ihr beispielsweise eure zusammengelegten Laufwerke (in diesem Beispiel /dev/disk1″ und “/dev/disk2) schlichtweg FusionDrive nennen, gebt Ihr den Befehl also folgerichtig so ein:

> diskutil coreStorage create FusionDrive /dev/disk1 /dev/disk2

Den am Ende ziemlich langen Text, den das Terminal ausgibt solltet Ihr kopieren und in einer Textdatei abspeichern. Dieser gibt Aufschluss über die UUID (Identifikation des Laufwerks) der gerade erstellten Laufwerkszusammenkunft. Sie wird im Folgenden noch benötigt.

**Schritt 3**

Bis jetzt haben wir also eine logische Gruppe an Laufwerken erstellt. Diese muss nun ein für das System erkennbares, einzelnes Laufwerk werden. Auch dies erledigen wir über das Terminal. Hierbei lautet das Grundgerüst des Befehls:

> diskutil coreStorage createVolume lvgUUID type name size

Die "lvgUUID" ist hierbei die vorher von uns gesicherte Kennung des neu erstellten Laufwerks. Die Option "type" beschreibt das Dateisystem. Wir verwenden hierbei natürlich HFS+. Der Name kann frei gewählt werden. Möchtet Ihr einen Namen mit Leerzeichen verwenden, benötigt Ihr dort Anführungszeichen, Beispiel: "Mac HD Fusiondrive). Über die letzte Funktion "size" könnt Ihr festlegen, wieviel Kapazität der Laufwerke als Speicher verwendet werden soll. Wählt Ihr "100%", wird die komplette Kapazität in das Fusion Drive miteinbezogen. Der Befehl könnte also wie folgt aussehen (UUID ist fiktiv):

> diskutil coreStorage createVolume 849393H9-DHD3-H2DH-9834-JDH7HS678KS1 jhfs+ “Mac HD Fusiondrive” 100%

Das Fusion Drive ist nun erstellt, Ihr könnt nun im Anschluss euer Timemachine Backup wieder zurückspielen und euch an der Geschwindigkeit gepaart mit Kapazität erfreuen.

[[via](http://www.macworld.com/article/2014011/how-to-make-your-own-fusion-drive.html)]
