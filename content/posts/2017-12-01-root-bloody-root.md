---
title: Root Bloody Root
slug: root-bloody-root
date_published: 2017-12-01T13:09:26.000Z
date_updated: 2018-08-22T09:37:42.000Z
tags: apple, fix.it, sicherheit, lücke, high sierra, macOS 10.13, 2017-001
---

Ganz im Sinne von Sepulturas uralt-Hit ([Video](https://www.youtube.com/watch?v=F_6IjeprfEs)) möchte ich auf die schwerwiegende Sicherheitslücke in **macOS High Sierra** hinweisen, die immer unverständlicher wird. Kurz zum Hintergrund: Der Fehler tritt auf, wenn ein Nutzer sich bei einem deaktivierten Account mit einem beliebigen Passwort (oder leer gelassenem Passwortfeld) anmeldet, wie der Sicherheitsforscher Patrick Wardle erklärte. Das Mac-Betriebssystem versuche in diesem Fall, ein Upgrade durchzuführen und das verschlüsselt gespeicherte Passwort in ein Shadow-Password zu verwandeln. Durch einen Fehler werde dabei aber das gerade neu beim Anmelden eingegebene Passwort gesetzt – und so der Zugriff für jeden freigegeben. 

Der Bug kann zudem nicht nur einem lokalen Angreifer Root-Rechte einräumen, sondern lässt sich mitunter auch aus der Ferne ausnutzen, wenn der Mac bestimmte Dienste anbietet wie etwa die Bildschirmfreigabe, betonen Sicherheitsforscher.

> If certain sharing services enabled on target - this attack appears to work remote (the login attempt enables/creates the root account with blank pw) Oh Apple [pic.twitter.com/lbhzWZLk4v (archiviert)](http://web.archive.org/web/20210610104001/https://t.co/lbhzWZLk4v)
> — patrick wardle (@patrickwardle) [28. November 2017 (archiviert)](http://web.archive.org/web/20210611050801/https://twitter.com/patrickwardle/status/935639234437935105?ref_src=twsrc%5Etfw)

Mittlerweile hat Apple gepatcht und spielt dieses Update automatisch ein, weil die Sicherheitslücke so gravierend ist. Allerdings kann diese Aktualisierung für macOS 10.13 die Dateifreigabe lahmlegen. Inzwischen hat der Mac-Hersteller bei dem Sicherheits-Update nochmals nachgebessert – das File-Sharing-Problem aber offenbar nicht ausgeräumt.

![Bildschirmfoto-2017-12-01-um-15.33.08](__GHOST_URL__/content/images/2017/12/Bildschirmfoto-2017-12-01-um-15.33.08.png)

#### Workaround bei Dateifreigabe-Problem in High Sierra

Apple ist der Fehler bekannt, das Unternehmen hat bereits einen manuellen Workaround veröffentlicht: Nutzer sollen im Terminal
`sudo /usr/libexec/configureLocalKDC`

eingeben und den Befehl ausführen, so Apple – dafür ist die Eingabe des Admin-Passwortes vonnöten. Dies repariere die Dateifreigabe.

Zunächst bekam Apple viel Lob, da es diese kritische Sicherheitslücke praktisch [über Nacht (archiviert)](http://web.archive.org/web/20221220224118/https://twitter.com/radian/status/935904628348141568) schloss. Nun jedoch stellte sich heraus, dass Apple schon länger davon wusste.

> Wie Lemi Orhan Ergin schreibt, der für iyzico.com arbeitet, sei Infrastrukturexperten seiner Firma das Problem schon vor einer Woche aufgefallen. Am 23. November sei dann Apple informiert worden. Danach passierte zunächst nichts. Erst fünf Tage später kam es dann zu einer Stellungnahme Apples in Reaktion auf Ergins Tweet sowie am 29. November zum Patch. "Einfach gesagt: Ich war nicht derjenige, der die Sicherheitslücke entdeckt hat, sondern derjenige, der sie sichtbarer gemacht hat, indem er sie auf Twitter erwähnte." Warum Apple nicht schon früher reagierte, ist unklar.

Den [ganzen Artikel](https://www.heise.de/mac-and-i/meldung/root-Luecke-in-macOS-Apple-hatte-wohl-mehr-Zeit-zum-Patchen-als-gedacht-3905926.html) gibt es bei Heise.

Aber wie dem auch sei, Loch ist Loch, auf jeden Fall sollte jeder High Sierra Nutzer das **Sicherheitsupdate 2017-001** einspielen. **Schnellstens**! Wie immer in ihrer freundlichen Softwareaktualisierung Mac App Store.
