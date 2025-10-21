---
title: [JAILBREAK] AppleTV 2 mit iOS 5.1 (9B179b)
slug: jailbreak-appletv-2-mit-ios-5-1-9b179b
date_published: 2012-04-11T13:55:49.000Z
date_updated: 2018-08-22T09:38:11.000Z
---

Dies ist der erste Artikel über den Jailbreak eines AppleTV auf unseren Webseiten. Allerdings erfährt das AppleTV in letzter Zeit und dank okayem Preis einen gehörigen Nutzer-Schub und somit denken wir, ist es nur eine logische Konsequenz, diesen nun auch öfter bei uns zu erwähnen.

---
[![](//thafakerde.appspot.com/img/iphone-jailbreak-150x150.jpg)](__GHOST_URL__/download-tools-jailbreaks/)Eine Liste mit allen wichtigen Downloads zu iOS und Jailbreak, also Tools wie *Pwnage Tool* oder *Sn0wbreeze*, findet ihr hier, in meiner übersichtlichen [Downloadsektion](__GHOST_URL__/download-tools-jailbreaks/).

---

Beim Jailbreak der aktuellen Firmware iOS 5.1 ((Build 9B179b)) handelt es sich um einen kabelgebundenen aka **Tethered** Jailbreak. Das bedeutet, dass wenn euer gejailbreaktes AppleTV vom Strom getrennt wird (Stromausfall, etc.), es auf die Starthilfe eines Mac oder Windows-Rechners angewiesen ist um wieder erfolgreich gestartet werden zu können. Seas0nPass ist eine kostenlose Jailbreak-Software speziell für das AppleTV, mit der sich eine gejailbreakte Firmware erstellen lässt, welche dann mittels iTunes auf das AppleTV installiert wird. Wie immer gilt: **Jailbreak auf eigenes Risiko**.

AppleTV 2 Jailbreak Firmware 5.0 (9:31)

## Wir benötigen:

- AppleTV 2
- aktuellste Version von Seas0npass für Mac bzw. Windows
- Ein lokales Netzwerk (Ob Ethernet oder Wifi spielt keine Rolle)
- Einen iTunes Account (obligatorisch)
- Micro-USB-auf-USB-Kabel ((Sowas [hier](http://www.amazon.de/Micro-USB-Kabel-USB-A-Stecker-Micro-B/dp/B000X26AYU/) quasi. Nein, ich verdiene daran nichts!))
- Apple Alu-Fernbedienung
- [aTV Flash Black Software](http://firecore.com/atvflash-black) (einmalig 22 Euro) Als alternative Oberfläche die mehr kann, als Apple selbst :-) Kein Muss!

## Anleitung Jailbreak:

1. Schliesse das AppleTV an die Stromversorgung und per USB an den Computer an
2. **Öffne Seas0nPass** und klicke auf “**Create IPSW**”
[![seas0npass_scr](//picdump.thafaker.de/2012/04/seas0npass_scr-580x392.jpg)](http://picdump.thafaker.de/2012/04/seas0npass_scr.jpg)
Seas0nPass läd nun, sofern nötig, die benötigte Firmware herunter und jailbreakt diese selbstständig. Dies kann ein paar Minuten dauern.
3. Sobald Seas0nPass die Meldung anzeigt “***Waiting for device to enter DFU mode…***“, muss man auf der Apple-Fernbedienung für **7 Sekunden** gleichzeitig den Wiedergabe- und Menü-Knopf drücken.
[![seas0npass_scr2](//picdump.thafaker.de/2012/04/seas0npass_scr2-580x392.jpg)](http://picdump.thafaker.de/2012/04/seas0npass_scr2.jpg)
Seas0nPass zeigt an ob bzw. wann das Gerät erfolgreich in den DFU-Modus gebracht wurde. (Der DFU-Modus ist ein Techniker-Modus welcher die Installation einer gejailbreakten Firmware ermöglicht.)
4. iTunes öffnet sich automatisch und Seas0nPass installiert selbstständig die gejailbreakte Firmware auf das AppleTV 2.
Sollte SeasonPass die Meldung ausgeben “Script failed”, muss die gejailbreakte Firmware, welche sich in der Regel im Download-Ordner befindet, manuell in iTunes ausgewählt werden.
Hierzu Shift-Taste (beim Mac) bzw. ALT-Taste (Windows) gedrückt halten, auf Wiederherstellen klicken und hier die Firmware auswählen.
5. Die gejailbreakte Firmware wird nun auf dem AppleTV installiert. Dies kann einige Minuten dauern.
6. Danach zeigt iTunes die Meldung “…Gerät…erfolgreich… wiederhergestellt” an. Die LED auf der Vorderseite des AppleTV sollte jetzt permanent blinken.
7. Jetzt muss das AppleTV 2 noch kabelgebunden gestartet werden (Tethered Boot)

1. Seas0nPass wieder öffnen
2. “Boot Tethered” klicken
3. Das AppleTV wieder in den DFU-Modus versetzen
4. AppleTV 2 wird gestartet
5. Wenn alles funktioniert hat leuchtet die LED des AppleTV durchgehend

8. Jetzt das AppleTV vom USB trennen, das Stromkabel unbedingt angesteckt lassen!
9. Das AppleTV ist nun gejailbreakt und kann per HDMI mit dem Fernseher verbunden werden. Der Fernseher sollte das AppleTV bereits erkennen und anzeigen.
10. Mit dem WiFi-Netzwerk und dem iTunes-Account für die iTunes Privatfreigabe verbinden.
11. Jailbreak ist soweit fertig.

Um jetzt auch etwas vom gejailbreakten AppleTV 2 zu haben, empfiehlt sich die Installation von [aTV Flash Black](http://firecore.com/atvflash-black). Diese kostenpflichtige Software erweitert das AppleTV um zahlreiche Features wie Browser, Last.fm, Medienserver und ermöglicht auch das Abspielen von normalerweise nicht **unterstützten Dateiformaten wie beispielsweise mkv**.

## Installation von aTV Flash Black

1. Das AppleTV und der Computer sollte **mit dem lokalen (Wifi-)Netzwerk verbunden** sein.
2. Sowohl auf dem AppleTV als auch in iTunes auf dem Computer sollte die[ iTunes Privatfreigabe (archiviert)](http://web.archive.org/web/20120209043720/http://www.giga.de:80/downloads/itunes/tipps/itunes-privatfreigabe-am-ipad-einrichten/) aktiviert sein.
3. **aTV Flash Black** auf dem Computer öffnen und installieren, wie in unserem Video zu sehen.
4. aTV Flash Black wird jetzt über die Privatfreigabe auf das gejailbreakte AppleTV kopiert.
5. Auf dem AppleTV sollte nach einem kurzen Lade-Bildschirm ein **neues Icon namens “Verwaltung”** zu sehen sein. (Hier auf dem Screenshot auf Englisch “Maintenance”)
[![atvblack](//picdump.thafaker.de/2012/04/atvblack-580x326.jpg)](http://picdump.thafaker.de/2012/04/atvblack.jpg)
6. Hier lassen sich nun die “Extras” wie den CouchSurfer (Browser) installieren welche dann als neue “Apps” auf dem Homescreen angezeigt werden.
[![atvblack2](//picdump.thafaker.de/2012/04/atvblack2-580x326.jpg)](http://picdump.thafaker.de/2012/04/atvblack2.jpg)
7. Fertig. Euer AppleTV 2 ist nun gejailbreakt und aTV Flash Black ist installiert.
Der Jailbreak sowie alle softwareseitigen Änderungen lassen sich jederzeit komplett rückgängig machen. Hierzu einfach das AppleTV an den Computer anschliessen und in iTunes (am besten im DFU-Modus) eine ungejailbreakte Firmware auf das AppleTV installieren.
