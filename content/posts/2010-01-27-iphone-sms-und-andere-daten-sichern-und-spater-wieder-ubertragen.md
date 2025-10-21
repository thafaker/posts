---
title: iPhone SMS und andere Daten sichern und später wieder übertragen
slug: iphone-sms-und-andere-daten-sichern-und-spater-wieder-ubertragen
date_published: 2010-01-27T21:28:01.000Z
date_updated: 2018-08-22T09:38:25.000Z
---

Ein freundlicher Leser des Weblogs, Peacecare, der schon häufig sehr praktikable Hinweise bot, hat einen neuen Streich zu präsentieren: die Sicherung sensibler und wichtiger Daten wie SMS oder auch Kalendereinträge und das spätere zurückspielen auf ein *frisches* iPhone. Diese kurze Anleitung richtet sich an Mac-User, sollte aber auch unter Windows möglich sein.

Hallo Freunde,

habe noch ein Schmankerl für alle, die ihr 3G nach [meiner Anleitung](__GHOST_URL__/14/jailbreak-iphone-3g-oder-3gs-mit-baseband-05-11-07-und-blackra1n/comment-page-1#comment-36415) neu aufgebaut haben.

**Hintergrund**: Um nicht Gefahr zu laufen, dass nach dem erfolgreichen “Aufbohren” wieder alles auf Null geht, sollte man kein Backup des alten Phones aufspielen. Nun haben viele User sicher 'ne Menge SMS oder Notizen oder auch Kalendereinträge, die noch auf dem alten Barren schlummern und gut ins neue passen würden. Die könnt ihr ohne großen Aufwand auf Euer 3G spielen.

**Lets go**:

-  Auf das Alte und auch auf das Neue von Cydia “Open SSH” runterladen.
- Für den Mac empfehle ich CyberDuck (für Win eventuell SmartFTP o.ä)
- Via CyberDuck mit dem Alten verbinden. Achtung: Bonjour klicken!! (Unter Windows muss man eventuell via SSH direkt auf die IP des iPhones connecten)
- Dann wird das Alte angezeigt.
- Klick drauf. --> Fenster öffnet sich --> **Name**: root **Kennwort**: alpine
- Jetzt seht Ihr einen Teil der 3G “Innereien”.
- Oben in der NaviLeiste draufklicken, auf private/var gehen
- --> und dann in mobile/Library/SMS navigieren.
- Den ganzen Ordner SMS oder Notes oder Calendar kopieren.
- Erlauben
- CyberDuck schließen
- Nun das Neue verbinden --> wieder in /private/var/mobile/Library/ navigieren.
- Per Drag und Drop den gesicherten Ordner einfügen (Achtung: Muss in Library)
- Ersetzen lassen.
- Fertig.

Nun habt Ihr z.B Eure SMS wieder

*Gruß Peacecare*
