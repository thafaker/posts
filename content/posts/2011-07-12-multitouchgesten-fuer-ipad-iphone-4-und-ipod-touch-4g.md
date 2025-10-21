---
title: Multitouchgesten für Ipad, IPhone 4 und IPod touch 4g [Update]
slug: multitouchgesten-fuer-ipad-iphone-4-und-ipod-touch-4g
date_published: 2011-07-12T08:30:32.000Z
date_updated: 2018-08-22T09:38:34.000Z
---

Nun bringt ja iOS 5 höchstwahrscheinlich offiziell diese schmucke Gestensteuerung mit, mit welcher man zum Beispiel  mit mehreren Fingern durch die Apps schalten kann, auf den Homescreen zurückspringt, oder den Taskmanager öffnet. Diese ist jedoch keinesfalls neu. Denn das war bereits für 4.3 geplant und wurde jedoch nur in der zweiten Beta von iOS 4.3 aktiviert. Ab der dritten Beta gabs es die Funktion schon nicht mehr. Ganz entfernt wurde die Funktion jedoch nicht, sie ist lediglich deaktivert, wie einige Hacker herausfanden. Hierbei hat man drei Möglichkeiten zur Aktivierung, ohne Jailbreak am Mac,  mit Jailbreak und mit Jailbreak und zusätzlicher App.

[![](//picdump.thafaker.de/2011/07/IMG_0005.png)](__GHOST_URL__/multitouchgesten-fuer-ipad-iphone-4-und-ipod-touch-4g/img_0005/)

**iPad Multitouchgesten aktivieren (ohne Jailbreak am Mac)**

Wir brauchen:

- - Mac
- - iPad/ iPad 2
- - iOS 4.3/ iOS 4.3.1
- - [Xcode (archiviert)](http://web.archive.org/web/20110905035905/http://itunes.apple.com:80/de/app/xcode/id422352214?mt=12)

Anleitung:

1. XCode 4 aus dem Mac App Store herunterladen (3,99€)
2. IPad an den Mac anschließen und XCode öffnen
3. Auf *Use Device for Development* klicken
4. Wird man nun nach den Entwicklerdaten gefragt, einfach auf Abbrechen klicken
5. Das Gerät ist nun im Entwicklermodus und man kann unter **Einstellungen****-> Allgemein** die Gestensteuerung aktivieren

**iPad Multitouchgesten aktivieren (mit Jailbreak)**

Wir brauchen:

- - Jailbroken iPad/ Jailbroken iPad 2 (iOS 4.3.3 Jailbreak findet ihr [hier](__GHOST_URL__/der-jailbreak-fuer-das-ipad-2-ist-da-jailbreakme-3-0-how-to/))
- - iOS 4.3/ iOS 4.3.1
- - iFile (Normale Version: $4,00; 7 Tage Testversion: kostenlos; Gecrackte Version: kostenlos)

Anleitung:

1. In Cydia die App iFile laden
2. iFile öffnen und in den Ordner****/var/mobile/Library/Preferences/ ****navigieren
3. Die Datei **com.apple.springboard.plist** mit “Textbetrachter” öffnen
4. Nach einem beliebigen Tag den folgenden Code eingeben:

**<key>SBUseSystemGestures</key>**

**<true/>**

5. Auf "Fertig" klicken
6. Das IPad neustarten oder Respringen

**
IPhone 4, IPod touch****4g****Multitouchgesten aktivieren****(mit Jailbreak und der App MT Gestures)**
Wir brauchen:

- - Jailbroken iPhone 4/ Jailbroken iPod Touch 4. Generation
- - iOS 4.3/ iOS 4.3.1
- - MT Gestures (kostenlos erhältlich in Cydia)

Anleitung:

1. MT Gestures aus Cydia laden
2. WinterBoard öffnen und Pod4,1_4.3.1_Gestures aktivieren
3. iPhone 4 oder iPod Touch 4. Generation neustarten oder respringen
4. In den Einstellungen nun **Multitasking_Gestures** aktivieren. Sollte die Option nicht direkt zu finden sein, einfach unter **Einstellungen > Allgemein** gehen und dort runterscrollen. Dort findet sich dann **Multitasking_Gestures**, diese dann einfach aktivieren.

**[Update]**

Leider funktioniert zumindest die iFile Variante nicht mit 4.3.3, wie ich nach einem Test feststellen musste. Die MT Gestures funktionieren aber dafür ganz gut mit dem IPad 2.
