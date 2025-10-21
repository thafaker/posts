---
title: [HOW TO] Wlan Probleme mit iOS8 und Yosemite beheben
slug: how-to-wlan-probleme-mit-ios8-und-yosemite-beheben
date_published: 2014-11-26T19:03:24.000Z
date_updated: 2018-08-22T09:38:53.000Z
---

![Bildschirmfoto 2014-11-26 um 19.58.34](//picdump.thafaker.de/2014/11/Bildschirmfoto-2014-11-26-um-19.58.34-100x100.png)Viele von uns, jene mit *iOS 8* und *Yosemite* zumindest, klagen über Wlan-Probleme. Probleme der schlechten Verbindung oder Probleme des Nicht-Verbindens bzw. des schlechten Datendurchsatzes. Dies ist kürzlich durch den Hacker *Mario Ciabarra*[eruiert](https://medium.com/@mariociabarra/wifried-ios-8-wifi-performance-issues-3029a164ce94) - und freundlicherweise auch gleich mit einem Tipp versehen worden.

Das Problem liegt an Apples neuem "Apple Wireless Direct Link" (AWDL), der für *AirDrop*, *AirPlay* und auch *Games* verwendet wird. Die Lösung ist also schlicht: AirDrop zu deaktivieren bis Apple endlich mit einem Update zur Fehlerbehebung rüber kommt.

### A fix for iOS WiFi

Startet Cydia und sucht nach folgendem Wort *WiFried*. Wenn ihr das Paket gefunden habt, klickt ihr auf Install, lasst Cydia die Software installieren und das wars auch schon wieder, ziemlich easy, sogar ohne extra Quelle. Ihr habt nun im Airdrop-Menü einen Punkt wo ihr das an/ausschalten könnt, je nach Wunsch. *That's it*.

Großartig, wieso kann nicht alles so einfach sein? Dies ist mal wieder ein Beweis für die sinnhafte Wichtigkeit eines Jailbreaks, auch heute noch.

### Yosemite

Für Yosemite bietet sich die folgende Kommando-Zeile an, die ihr im Terminal ausführen könnt. Copy & Paste empfiehlt sich hier übrigens, ge.

AWDL für das WLan deaktivieren:

    Jans-iMac-2:~$ sudo ifconfig awdl0 down

schaltet AWDL (und damit AirDrop) aus, "sudo ifconfig awdl0 up

AWDL für das WLan wieder aktivieren:

    Jans-iMac-2:~$ sudo ifconfig awdl0 up

[http://www.youtube.com/watch?v=t4CsfY6ewS0](http://www.youtube.com/watch?v=t4CsfY6ewS0)
