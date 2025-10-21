---
title: Wie sichere ich SHSH Files oder stelle ein iPhone wieder her?
slug: wie-sichere-ich-shsh-files-oder-stelle-ein-iphone-wieder-her
date_published: 2010-12-13T13:31:02.000Z
date_updated: 2018-08-22T09:38:16.000Z
---

**TinyUmbrella**

**SHSH Files sichern, wiederherstellen, downgraden**

Diese Anleitung behandelt das Tool ''TinyUmbrella''.

Mit ''TinyUmbrella'' kann man die **SHSH Files sichern/auslesen**, um damit die gleiche **Firmware wiederherstellen**, die auf dem Gerät vorhanden ist, oder auch um auf eine **ältere FW, deren SHSH Files gesichert sind, downzugraden**.

Damit das iDevice auch in Zukunft jailbreakbar bleibt, ist man gezwungen die SHSH Files zu sichern.

Diese Anleitung funktioniert mit folgenden GeräteN:

- iPhone 3G
- iPhone 3GS
- iPhone 4
- iPad
- iPod 2G
- iPod 3G

**Für die Sicherung, Wiederherstellung und den Downgrade mit TinyUmbrella ist kein Jailbreak erforderlich.**
**Gesichert werden immer ALLE SHSH´s die möglich sind bzw. diese die bereits über Cydia (Make my Life  easier) gesichert wurden, dabei ist es unerheblich, welche FW sich auf  dem Gerät befindet !!!
****1. Schritt: Überprüfen/sichern der SHSH Files (lokal)**

TinyUmbrella von der Herstellerhomepage laden:
[**The Firmware Umbrella**](http://thefirmwareumbrella.blogspot.com/)( Auf der rechten Seite Betriebssystem auswählen )

Nachdem dem Download öffnet man TinyUmbrella und schließt das Gerät an.

Beim klick links auf das iDevice unter **"Connected Devices"** und rechts auf **"General"** werden sämtliche Infos des angeschlossenen Gerätes angezeigt:

[![1](//picdump.thafaker.de/2010/12/1-580x447.png)](http://picdump.thafaker.de/2010/12/1.png)

Beim klick auf **"Advanced"** kann der Speicherort der SHSH´s gewählt werden, die anderen Einstellungen sollten so belassen werden.

Bei Änderungen unten rechts mit **"Apply Changes"** bestätigen:

[![2](//picdump.thafaker.de/2010/12/2-580x445.png)](http://picdump.thafaker.de/2010/12/2.png)

Auf **"Log"** klicken und oben rechts auf **"Save SHSH"**, nach einigen Sekunden wird in der Mitte angezeigt wieviele SHSH´s gesichert werden konnten:

[![3](//picdump.thafaker.de/2010/12/3-580x450.png)](http://picdump.thafaker.de/2010/12/3.png)

Beim Klick auf **"General"** werden in der Mitte die gesicherten SHSH´s angezeigt:

[![4](//picdump.thafaker.de/2010/12/4-580x447.png)](http://picdump.thafaker.de/2010/12/4.png)

**2. Schritt: Wiederherstellung oder Downgrade durchführen**

Damit TinyUmbrella funktioniert, müssen die SHSH Files auf der Festplatte gesichert sein, siehe 1. Schritt

Auf **"Log"** klicken und oben rechts auf **"Start TSS Server"**(nur starten, läuft im Hintergrund weiter) bis wir fertig sind. **Nicht auf Stop klicken.**

[![5](//picdump.thafaker.de/2010/12/5-580x448.png)](http://picdump.thafaker.de/2010/12/5.png)

**Anschließend iTunes öffnen und das Gerät in den DFU Modus versetzen:**

`How To: Enter DFU Mode on an iPhone/iPod Touch`

**Mit gedrückter Shift Taste auf ''Wiederherstellen'', klicken** (beim Mac Alt Taste) es öffnet sich ein Fenster. Nun die Firmware auswählen, die wir aufspielen wollen und bestätigen.

**[Firmware Download](http://www.felixbruns.de/iPod/firmware/)**

iTunes fängt nun mit dem aufspielen der FW an. Wenn das Gerät mit der gleichen Firmware wiederherstellt wird, auf der es war, läuft diese Problemlos durch.

Beim Downgrade auf eine ältere FW erscheint am Ende der Fehler 1015. Das  ist normal. Die Firmware ist bereits aufgespielt und das Gerät befindet  sich im Recovery Modus.

Anschließend in TinyUmbrella rechts oben auf **"Exit Recovery"** klicken:

[![6](//picdump.thafaker.de/2010/12/6-580x447.png)](http://picdump.thafaker.de/2010/12/6.png)

**Das Gerät bootet neu und startet regulär.**

Für Schäden übernehme ich keine Haftung

Das sollte es bereits gewesen sein.

([via](http://www.handy-faq.de/forum/iphone_forum/159335-tiny_umbrella_shsh_sichern_wiederherstellung_downgrade.html))
