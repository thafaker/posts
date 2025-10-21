---
title: Powerline - DLan als Alternative?
slug: powerline-dlan-als-alternative
date_published: 2016-02-08T12:55:47.000Z
date_updated: 2018-08-22T09:39:28.000Z
tags: PowerLAN, powerline, dlan, devolo, steckdose, lan, wlan, geschwindigkeit, anleitung, how to, erfahrungsbericht, tipps, homeplug, aneitung, howto
---

Ich habe ja erst [kürzlich](__GHOST_URL__/netgear-nighthawk-x6-r8000/) von meinem Versuch berichtet, eine vollständige WLan-Abdeckung in meinem neuen Domizil zu erreichen. Mit einem wesentlich stärkeren Router konnte ich zwar mehr Geräte gleichzeitig verbinden, aber die maximale Reichweite und den Durchsatz konnte ich nicht erhöhen. 

Und so habe ich mich mit dem von mir immer verschmähten Powerline-Ansatz beschäftigt. Also Netzwerk über die Steckdose. Ich hatte dazu verschiedene Aspekte im Hinterkopf:

1. Unsicher und abhörbar vom Nachbarn
2. Langsam, Geschwindigkeit schlecht, Brutto-Netto-Scherz
3. relativ teuer

Da meine Informationen aber bereits ein paar Jahre zurück liegen und die Technik niemals schläft, forschte ich nach.

#### Grundlegend:

Technisch realisiert wird die Übertragung mit Hilfe von Adaptern, die einerseits mit dem Stromnetz und andererseits (über einen eingebauten Ethernet-Anschluss) mit einem zu vernetzenden Endgerät (z. B. einem PC, einem Drucker, einer Spielekonsole oder einer Webcam) verbunden werden.

Das heißt konkret: Steckdose an einer Wand in der Nähe des Routers suchen und dort den Powerline-"Sender" einstecken. Per Netzwerkkabel mit dem Router verbinden. Nun eine Steckdose in dem Raum suchen, wo man sich erweitern möchte. Eine Taste zur Synchronisation an beiden Geräten drücken, 30 Sekunden warten - Verbindung steht. Spielend einfach und heutzutage auch schon an dieser Stelle verschlüsselt.

> Internet --> Router --> Powerline --> Powerline --> Endgeräte

![](__GHOST_URL__/content/images/2016/02/powerline-1.jpg)

#### Und bei mir?

Ich habe mich für eine Kombination entschieden, die dem aktuellen Standard **Homeplug 1200** entspricht und theoretische 1200MBit brutto schafft. Der "Empfänger" spannt in meinem Setup einen eigenen Wlan-Access-Point auf. Somit stecke ich mein Powerline dort in die Steckdose, wo ich Wlan möchte - fertig.

Ich habe mein Wlan im Wohnzimmer am Kabelmodem, was nicht bis in alle Zimmer der Wohnung vordringt. Nun habe ich noch ein zusätzliches WLan in der Küche, sodass die Wohnung von zwei Seiten beleuchtet wird. Den Weg vom Wohnzimmer in die Küche gehe ich über Powerlan durch die Steckdose. Das Wlan erweitere ich, sodass ich im 2,4GHz und 5GHz-Bereich das identische Wlan wie im Wohnzimmer habe und meine Geräte je nach Standort das für sie Stärkste automatisch nutzen. Das funktioniert absolut problemlos. Die Wlan-Abdeckung ist nun nahezu perfekt.

##### Was kommt an Geschwindigkeit raus?

Wichtig ist ja nicht nur der WLan-Empfang, sondern auch, was nun effektiv durch die Stromleitung geht, sonst ist dies der Flaschenhals. Ich habe ohne weitere Optimierungen den Powerline neben der TV-Bank (mit u.a. Settop-Box, Apple-TV, Spielconsole, Audio) an der Steckdose beim Router eingesteckt - und das andere in der Küche bei der Steckdose unter dem Lichtschalter. In dieser Konfiguration erhalte ich:

- ca. 6 Megabyte / Sekunde (240 bis 300 MBit brutto)

Das empfinde ich als keinen schlechten Wert. Natürlich schaffe ich damit noch nicht mal die 12 MB/Sec eines 100MBit-Netzwerkes - geschweige denn diese theoretischen 1200MBit (brutto), aber immerhin kann ich damit meine Internetleitung besser auslasten, was mir momentan reicht. Wenn ich Zeit habe, versuche ich das dauerhaft zu optimieren, denn natürlich ist das nicht der Weisheit letzter Schluss, denn so taugt das recht wenig für echtes Networking mit Datentransfer etc. denn eher zum Surfen.

#### Stolperfallen

Leider kann man seine Gegebenheiten vorher meist nicht wirklich nachvollziehen. Wie und was für Leitungen liegen, welche Qualität verwendet wurde etc. weiß man meist nur, wenn man das Haus selbst gebaut hat. Lebt man zur Miete, sieht es hier düster aus. Allerdings kann man sich seine neue Technik über das Internet bestellen und hier von seinem Rückgaberecht gebrauch machen, wenn es nicht funktioniert. So hat man die Möglichkeit, das grundsätzlich auszuprobieren. Es folgen ein paar Tipps:

- Mehrfachverteilersteckdosen nicht benutzen
- Verteilersteckdosen mit Überspannungsschutz funktionieren zu 95% gar nicht
- Zwei Wandsteckdosen nebeneinander: hier sollte man nur eine belegen und die andere frei lassen, da es sich sonst *überlagert*.
- Über den *Stromzähler* kommt man oft nicht hinaus
- verschiedene Phasen dämpfen die Geschwindigkeit
- Externe Geräte können u.U. dämpfen:
- Dimmer,
- Vorschaltgeräte bzw. Netzteile,
- Bohrmaschinen
- Staubsauger

Einen guten Überblick zur Thematik DLan und Problembeseitigung zeigt der [folgende Artikel](http://dreibeinblog.de/devolo-dlan-tipps-und-tricks/) auf.

---

Artikelfoto: (C) [computerwoche.de](http://images.computerwoche.de/images/computerwoche/bdb/2598668/522x294.jpg), [dlanmeister.de](http://dlanmeister.de/wp-content/uploads/2015/09/devolo-dlan-powerline-500-av-wireless-starter-kit-review-zur-einfachen-heimvernetzung-nat-games-review-03.jpg)
