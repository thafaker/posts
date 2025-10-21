---
title: [SECURITY] iPad per Angriff lahmlegen
slug: security-ipad-per-angriff-lahmlegen
date_published: 2016-04-14T09:23:22.000Z
date_updated: 2018-08-22T09:39:28.000Z
tags: timeserver, security, sicherheit, apple, ios, iphone, ipad, spoof
---

Der sogenannte **Timeserver-Spoof** kann nämlich ein iPad ins Koma schicken, wenn dieses mit einem WLan verbunden ist. Das Problem ist laut Berichten von Sicherheitsforschern erst mit iOS 9.3.1 behoben. 

![Apple iPad thafaker.de](http://thafaker.de/content/images/2016/04/Apple-Tablet.jpg)

[Wir hatten darüber berichtet](__GHOST_URL__/datumsumstellung-kann-ios-gerate-lahmlegen/), dass man mit der manuellen Eingabe der *Unix-Start-Time* auf iOS Geräten selbige außer Gefecht setzen kann! Stellt man das Datum auf 1970, haben die Geräte mit 64-Bit-CPUs (ab iPhone 5s) Startprobleme. iOS 9.3 beseitigt jenes Problem.

Sicherheitsforscher haben nun aber eine neue Methode beschrieben, mit der sich dieser Angriff automatisieren lässt, wie auf Heise geschrieben wird – und angeblich auch bei Geräten mit iOS 9.3.0 noch klappt.

In diesem Fall muss der Angreifer im selben WLan sein, wie das Gerät - und er muss das Wlan kontrollieren können. [...] Dafür lasse sich beispielsweise ein üblicher WLAN-Name wählen, den auch große Hotspot-Anbieter verwenden – das iOS-Gerät verbinde sich dann automatisch und ohne Nachfrage mit dem vermeintlich bekannten Netzwerk. [...]

IDevices nehmen bei Verbindung immer Kontakt zu Apples Timeserver auf, um die Zeit und das Datum abzuchecken, das ist gewollt. Gibt man sich nun als Timeserver aus und stellt das Datum so automatisch auf das Jahr 1970, würden sich die Geräte automatisch *bricken*. Sicherheitsforscher die das erfolgreich demonstriert haben, nutzten für den Versuch Hardware im Wert von 120 Euro, also keine Hochsicherheitstechnik sondern vielmehr u.a. einen *Raspberry Pi*.

[...] Den Angriff auf iPhones durchzuführen ist allerdings erheblich komplizierter, da diese die Datumseinstellung standardmäßig über das Mobilfunknetz beziehen statt Apples NTP-Server zu kontaktieren.

([via](http://www.heise.de/mac-and-i/meldung/Sicherheitsforscher-Timeserver-Spoof-schickt-iPad-ins-Koma-3173229.html))

**Artikelfoto**: (C) [http://tinyurl.com/hkmxtne](http://tinyurl.com/hkmxtne)
