---
title: Tiny Umbrella SHSH sichern und wiederherstellen
slug: tiny-umbrella-shsh-sichern-und-wiederherstellen
date_published: 2011-06-29T20:05:47.000Z
date_updated: 2018-08-22T09:38:35.000Z
---

Aus aktuellem, nicht näher benanntem, Anlass gibt es auf thafaker.de nun auch endlich ein Tutorial um SHSH Files via TinyUmbrella zu sichern und das iDevice ebenfalls mithilfe dieser Software auf eine ältere iOS Version wiederherzustellen. *Viel Erfolg*.

## **SHSH Files sichern, wiederherstellen, downgraden**

Diese Anleitung behandelt das Tool ''TinyUmbrella''.
Mit ''TinyUmbrella'' kann man die **SHSH Files sichern/auslesen**, um damit die gleiche **Firmware wiederherstellen**, die auf dem Gerät vorhanden ist, oder auch um auf eine **ältere FW, deren SHSH Files gesichert sind, downzugraden**.

Damit auch in Zukunft unser Gerät jailbreakbar bleibt, ist man gezwungen die SHSH Files zu sichern.

Diese Anleitung funktioniert mit folgenden Geräten:

- iPhone [3G](3G)
- iPhone 3Gs
- iPhone 4
- iPad 1 & 2
- iPod 2G
- iPod 3G

**Für die Sicherung, Wiederherstellung und den Downgrade mit TinyUmbrella ist kein Jailbreak erforderlich.**
**Gesichert werden immer ALLE SHSH´s die möglich sind bzw. diese die bereits über Cydia (Make my Life easier) gesichert wurden, dabei ist es unerheblich, welche FW sich auf dem Gerät befindet !!!
****1. Schritt: Überprüfen/sichern der SHSH Files (lokal)**
**TinyUmbrella Download:**
- [TinyUmbrella [OSX]](http://cache.firmwareumbrella.com/downloads/TinyUmbrella-5.00.07.pkg)
- [TinyUmbrella [WIN]](http://cache.firmwareumbrella.com/downloads/tinyumbrella-5.00.07.exe)

Nachdem dem Download öffnet man TinyUmbrella und schließt das Gerät an. Beim klick links auf das iDevice unter **"Connected Devices"** und rechts auf **"General"** werden sämtliche Infos des angeschlossenen Gerätes angezeigt:

[![](//www.abload.de/img/tu017ejr.png)](http://www.abload.de/image.php?img=tu017ejr.png)

Beim klick auf **"Advanced"** kann der Speicherort der SHSH´s gewählt werden, die anderen Einstellungen sollten so belassen werden.

[![](//www.abload.de/img/tu02s9n6.png)](http://www.abload.de/image.php?img=tu02s9n6.png)

Auf **"Log"** klicken und oben rechts auf **"Save SHSH"**, nach einigen Sekunden wird in der Mitte angezeigt wieviele SHSH´s gesichert werden konnten:

[![](//www.abload.de/img/tu0379mm.png)](http://www.abload.de/image.php?img=tu0379mm.png)

Beim klick auf **"General"** werden in der Mitte die gesicherten SHSH´s angezeigt:

[![](//www.abload.de/img/tu03shsh19wn.png)](http://www.abload.de/image.php?img=tu03shsh19wn.png)

**2. Schritt: Wiederherstellung oder Downgrade durchführen**

Damit TinyUmbrella funktioniert, müssen die SHSH Files auf der Festplatte gesichert sein, siehe 1. Schritt

Auf **"Log"** klicken und oben rechts auf **"Start TSS Server"**(nur starten, läuft im Hintergrund weiter) bis wir fertig sind. **Nicht auf Stop klicken.**

[![](//www.abload.de/img/tu04bxwf.png)](http://www.abload.de/image.php?img=tu04bxwf.png)

Anschließend iTunes öffnen und das Gerät in den DFU Modus versetzen:

**Mit gedrückter Shift Taste auf ''Wiederherstellen'', klicken** (beim Mac Alt Taste) es öffnet sich ein Fenster. Die FW auswählen, die wir aufspielen wollen und bestätigen.

**[Firmware Download](__GHOST_URL__/download-ios-firmwares-fur-iphone/)**

iTunes fängt nun mit dem aufspielen der FW an.

Wenn das Gerät mit der gleichen Firmware wiederherstellt wird, auf der es war, läuft diese Problemlos durch.

Beim aufspielen der 4.2.1 und 4.3.x beim **3GS und iPhone 4** erscheint der iTunes Fehler **1013 oder 1015**, dann direkt den JB mit **greenpois0n 1.0rc6.1** nach dieser Anleitung durchführen.

[**iOS 4.2.1 untethered JB mit greenpois0n**](__GHOST_URL__/howto-jailbreak-iphone-4-ios-4-2-1-mit-greenpois0n-rc5/)

Beim Downgrade auf eine ältere FW erscheint am Ende der Fehler 1015. Das ist normal. Die Firmware ist bereits aufgespielt und das Gerät befindet sich im Recovery Modus.

Anschließend in TinyUmbrella rechts oben auf **"Exit Recovery"** klicken:

[![](//www.abload.de/img/tu05exit6ajr.png)](http://www.abload.de/image.php?img=tu05exit6ajr.png)
**Das Gerät bootet neu und startet regulär.**
