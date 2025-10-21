---
title: [BASEBAND] Downgrade auf iPhone 3G/3GS mit iPad-BB 06.15 nun möglich
slug: baseband-downgrade-auf-iphone-3g3gs-mit-ipad-bb-06-15-nun-moglich
date_published: 2012-07-01T10:46:56.000Z
date_updated: 2018-08-22T09:39:09.000Z
---

![baseband-downgrade-iphone-3g](//picdump.thafaker.de/2011/05/baseband-downgrade-iphone-3g-150x150.png)Wer ein iPhone 3G und iPhone 3GS mit gehacktem iPad-Baseband 06.15.00 hat, kann nun endlich downgraden: mit einer neuen redsn0w-Version kann dieses Baseband wieder entfernt und ein älteres Baseband aufgespielt werden.

Mit redsn0w 0.9.14b1 lässt sich das vorhandene 06.15-Baseband auf Baseband 05.13.04 bringen und reaktiviert damit die verlorengegangenen GPS-Funktionen und ist in der Lage, Standard-iOS-Versionen aufzuspielen. Bisher musste man auf Grund des Basebands eine Custom-Firmware aufspielen.

Die einzelnen Schritte:

1. Nach dem Start von redsn0w den Button Extras->Select IPSW nutzen, um einzustellen, welche Firmware installiert ist (wer ein iPhone 3GS mit neuem Bootrom können diesen Schritt auch überspringen, wer sich nicht sicher ist, sollte diesen Schritt durchführen).
2. das iPhone kontrolliert herunterfahren (Homebutton gedrückt halten und Ausschalten-Slider nutzen)
3. Zum ersten Screen zurückgehenund auf “Jailbreak” klicken. Einen Haken in “Downgrade from iPad baseband” machen, Cydia deaktivieren, danach auf Next klicken und den Anweiseungen für den DFU-Ramdisk-Modus folgen.

Nach dem Starten der Ramdisk erscheint auf dem Display das Pwnapple-Logo und im Optimalfall geht das iPhone in den Baseband-Flash-Modus. Dies dauert laut Dev-Team relativ lange (bis zu 8 Minuten), währenddessen gibt es keinerlei Rückmeldungen, wenn der Vorgang beendet ist, startet sich das iPhone selbst neu. Weiterhin weist musclenerd auf folgendes hin: Falls nach dem Durchführen des Downgrades immer noch das 06.15-Baseband angezeigt wird, soll man das Tool erneut nutzen. Wer außerdem nach dem Downgrade “Kein Signal” angezeigt bekommt, der soll es mit einer Neuinstallation von MobileSubstrate und/oder ultrasn0w probieren.

[via [Dev-Team (archiviert)](http://web.archive.org/web/20120701134935/http://blog.iphone-dev.org:80/post/25350690843/0615-fun)] ([via](http://www.iphonenotes.de/2012/06/18/baseband-downgrade-auf-iphone-3g3gs-mit-ipad-bb-06-15-nun-moglich/?utm_source=feedburner&amp;utm_medium=feed&amp;utm_campaign=Feed%3A+Iphone-notesde+%28iPhone-notes.de%29))
