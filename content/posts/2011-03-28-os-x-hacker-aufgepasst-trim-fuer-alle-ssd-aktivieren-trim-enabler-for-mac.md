---
title: "OS X Hacker aufgepasst: TRIM für Apple-fremde SSD aktivieren (Trim Enabler for Mac) [Update]"
slug: os-x-hacker-aufgepasst-trim-fuer-alle-ssd-aktivieren-trim-enabler-for-mac
date_published: 2011-03-28T19:34:43.000Z
date_updated: 2018-08-22T09:38:38.000Z
---

[![Bildschirmfoto 2011-03-29 um 11.52.56](//picdump.thafaker.de/2011/03/Bildschirmfoto-2011-03-29-um-11.52.56-150x150.png)](http://picdump.thafaker.de/2011/03/Bildschirmfoto-2011-03-29-um-11.52.56.png)[**Update**] *TRIM 1.1 ist da*

Wie der Entwickler gestern auf seiner Website versprochen hatte, wollte er den Code des *Trim Enabler for Mac* anpassen und einen "deaktivieren" oder "undo" Knopf einbauen. Dies ist bereits geschehen und steht mit Version 1.1 zur Verfügung. Im unteren Teil dieses Artikels könnt ihr die aktuellste Version über den Download-Button laden oder ihr besucht direkt die [Entwickler-Website (archiviert)](http://web.archive.org/web/20110401201644/http://www.groths.org:80/?p=308) (vielmehr den Blog-Artikel zur Software) von Oskar Groth.

[**Original**] *Trim Enabler for Mac 1.0*
[![ocz-ssd](//picdump.thafaker.de/2011/03/ocz-ssd-150x150.jpg)](http://picdump.thafaker.de/2011/03/ocz-ssd.jpg)Im Zuge meiner Entscheidung für ein neues Macbook habe ich mich ja auch mit den diversen Unzulänglichkeiten von verschiedenen Settings und Setups beschäftigt und heraus gefunden, dass OS X 10.6 den für SSDs wichtigen TRIM Befehl im Gegensatz zu Windows 7 ((*Sprich*: "Seven" nicht "Sieben"!)) nicht unterstützt. Nun aber stellte sich heraus, dass ein spezielles Build von OS X 10.6.6, ausgeliefert ausschließlich mit neuen Macbooks von 2011, diesen TRIM Befehl für Apple-eigene SSDs unterstützen würde.

Einige findige Hacker haben nun diese Kernel-Erweiterung (kext) extrahiert und auf andere OS X 10.6 Systeme portiert und siehe da: plötzlich meldet der System-Profiler aktivierten TRIM-Support auch für Apple-fremde SSDs, beispielsweise von Crucial oder OCZ. Soweit so gut kommt Freude auf, denn wie man weiß, sorgt der TRIM-Befehl für ein intelligentes Speichermanagement und optimiert so die SSD und sorgt dadurch wohl auch für ein längeres Leben selbiger.

Das schöne ist: dieser Hack ((man kann gar nicht mehr von Hack sprechen weils so einfach ist)) ist gar nicht schwierig zu bewerkstelligen, weil [Oskar Groth (archiviert)](http://web.archive.org/web/20110401201644/http://www.groths.org:80/?p=308) ((Übrigens heißt der Sänger von Apoptygma Berzerk Stephan Groth)) eine kleine grafische Oberfläche programmiert hat, mit welcher man die Veränderung im System automatisch durchführen lassen kann. ***Trim Enabler for Mac***.

Warum richtet sich der Tipp an Hacker? Also, es liegt sicher nicht am Schwierigkeitsgrad sondern eher an anderen Faktoren:

- Die Macher des Hacks hatten keine Zeit es ausgiebig zu Testen, Spätfolgen kennt also keiner
- Es kann dadurch auch zu Problemen kommen, die [SSD läuft plötzlich langsamer (archiviert)](http://web.archive.org/web/20230605125813/http://www.groths.org/?p=308) oder
- es droht Datenverlust oder
- das System bootet gar nicht mehr (Tipp des Autors: im Single-User-Mode mit Shift beim Boot starten)
- man sollte nicht vergessen, dass einige SSDs ein Firmware-Update brauchen, bevor der TRIM-Befehl bei ihnen überhaupt funktioniert, ältere SSDs sind davon betroffen
- man sollte also auf jeden Fall ein Backup haben, für den Fall der Fälle...

[![download-button](//picdump.thafaker.de/2011/03/download-button.gif) (archiviert)](http://web.archive.org/web/20110728005126/http://groths.org/zeus/TRIMEnabler.zip)
**Weitere Links**:

- [Groth.org (archiviert)](http://web.archive.org/web/20110401201644/http://www.groths.org:80/?p=308)
- [Hardmac (archiviert)](http://web.archive.org/web/20110405093519/http://www.hardmac.com:80/news/2011/03/27/the-universal-solution-to-activate-trim)

Der Entwickler arbeitet bereits [an einer neuen Version (archiviert)](http://web.archive.org/web/20110401201430/http://www.groths.org:80/?p=311), die auch einen Knopf zum Deaktivieren des Hacks enthält.
