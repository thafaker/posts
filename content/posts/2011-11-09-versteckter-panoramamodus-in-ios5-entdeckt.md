---
title: Versteckter Panoramamodus in iOS5 entdeckt [UPDATE]
slug: versteckter-panoramamodus-in-ios5-entdeckt
date_published: 2011-11-09T10:51:41.000Z
date_updated: 2018-08-22T09:38:27.000Z
---

Die altbekannte systemeigene Kamera-App kann in iOS 5 Fotos mit und ohne Blitz sowie als HDR-Aufnahme schießen. Es gibt allerdings eine Funktion, die uns Apple vorenthalten hat: die Panoramafunktion. Diese Funktion existiert, sie ist jedoch deaktiviert und taucht somit auch nicht in der Auswahl auf, wie findige Hacker herausfanden. Es muss jedoch lediglich eine .plist Datei modifiziert werden, um die Funktion freizuschalten, wie Conrad Kramer [schreibt (archiviert)](http://web.archive.org/web/20250905043545/https://twitter.com/).

Es handelt sich dabei um die Datei "com.apple.mobileslideshow.plist". Bei dieser muss der Parameter "Yes" hinter "EnableFirebreak" gesetzt werden. Die Datei befindet sich unter iOS im Verzeichnis "/var/mobile/Library/Preferences/com.apple.mobileslideshow.plist".

Wenn die Option gesetzt ist, erscheint dann ,laut Conrad Kramer, im Kamera-App Menü der Button Panorama. Dieser funktioniert wie bei Kompaktkameras üblich durch langsames Bewegen der Kamera in die auf dem Bildschirm vorgegebene Richtung, bis die Aufnahme komplettiert wurde. Danach errechnet das IPhone das passende Bild aus mehreren Einzelfotos, die während des Schwenkens automatisch aufgenommen werden.

[![](//picdump.thafaker.de/2011/11/panoramaios5.png)](__GHOST_URL__/versteckter-panoramamodus-in-ios5-entdeckt/panoramaios5/)Kramer kündigte bereits einen Tweak für Cydia an, mit dem die Panoramafunktion bei jedem Jailbreak-iPhone mit iOS 5 freigeschaltet werden soll. Grant Paul alias chpwn teilte mit, Firebreak bereits [auf Cydia veröffentlicht](http://cydiahelp.com/enable-panorama-camera-mode-in-ios-5-with-firebreak-jailbreak/) zu haben.

Wie die Manipulation auf einem iPhone **ohne** Jailbreak durchgeführt wird, zeigt die Website [Funkyspacemonkey](http://www.funkyspacemonkey.com/enable-panorama-mode-nonjailbroken-iphone-including-4s-running-ios-5?utm_source=twitterfeed&amp;utm_medium=twitter&amp;utm_campaign=Feed%3A+FunkySpaceMonkey+) Schritt für Schritt.

Bisher wurde lediglich dieser Screenshot veröffentlicht und noch keine Panoramaaufnahme. Wir Fakers haben es noch nicht getestet und können dementsprechend noch nicht sagen ob es funktioniert. Alles wie immer auf eigenes Risiko.

[**Update #1 14:16**] Mittlerweile haben wir die Panorama-Funktion im Selbstversuch getestet und können sagen: die Installation via Cydia gestaltet sich spielend einfach, es ist nicht mal ein *Reboot* sondern nur ein *Respring* notwendig, aber die Bilder sehen "auf die Schnelle" schon sehr bescheuert aus. Dies wird auch der Grund seitens Apples sein, diese Funktion nicht frei zu schalten - sie funktioniert schlicht nicht gut genug.

**Vorgehensweise**

1. ihr braucht ein [Jailbroken (archiviert)](http://web.archive.org/web/20110918200244/http://thafaker.de:80/jailbreak-unlock-status/) (zur zweiten Tabelle scrollen) iPhone
2. Cydia starten
3. nach "Firebreak" suchen
4. installieren
5. Respring durchführen
6. Foto-App starten
7. Option klicken
8. Panorama aussuchen
9. Anweisungen folgen --> FERTIG!

[gallery link="file"]

*Um auf dem Laufenden zu bleiben, könnt ihr uns auf [Twitter](http://twitter.com/#%21/thafakerde) folgen oder die [Facebook-Seite](http://de-de.facebook.com/pages/thafaker-auf-Beton/154600141278763) besuchen.*
