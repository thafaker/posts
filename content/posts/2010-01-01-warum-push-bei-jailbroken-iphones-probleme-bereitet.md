---
title: Warum Push bei jailbroken iPhones Probleme bereitet [Update]
slug: warum-push-bei-jailbroken-iphones-probleme-bereitet
date_published: 2010-01-01T20:12:27.000Z
date_updated: 2018-08-22T09:38:19.000Z
---

Wenn das iPhone (originales 3G oder 3GS) ohne autorisierte (bei uns T-Mobile) SIM-Karte aktiviert worden ist (hacktivated) und mit der iPhone Firmware höher als 3.0 läuft, kann es zu Problemen mit der Push Funktion kommen. Youtube kann keine Verbindung herstellen und IM+ oder Twitter Notifications werden nicht übermittelt oder schlimmer noch, man bekommt falsche Nachrichten zugestellt.
[![51771218](//picdump.thafaker.de/2010/01/51771218.png)](http://picdump.thafaker.de/2010/01/51771218.png)

Dies liegt daran, dass jedes iPhone bei der ersten Aktivierung über iTunes ein 1024 bittiges Zertifikat erhält, bestehend aus nicht rückführbaren Informationen des iPhones und der sogenannten IMEI Nummer (welche einmalig in jedem Handy der Welt steckt). Zur Aktivierung benötigt man eine legale SIM-Karte.

Hat man nun sein iPhone nicht legal aktiviert und diesen sogenannten **Pushfix** installiert, teilen sich tausende Benutzer ein einziges Zertifikat. Und das führt dann wie oben beschrieben zu den bekannten Problemen wie eben, dass die Nachrichten nicht zugestellt werden können und und und...

Ein kostenlose Lösung ist nicht in Sicht.

Allerdings gibt es ein kostenpflichtiges Angebot. Man kann sich durch Eingabe seiner IMEI-Nummer auf einer [Website (archiviert)](http://web.archive.org/web/20091224055431/http://pushfix.info:80/) ein solches Zertifikat erstellen lassen, über [Cydia (archiviert)](http://web.archive.org/web/20100114102541/http://cydia.pushfix.info:80/) dann einen Pushfix intallieren und der funktioniert garantiert. Allerdings kostet diese Lösung Geld.

- Man findet die IMEI-Nummer (und andere Informationen) in der Anzeige "Info". Tippen Sie im Hauptbildschirm auf **Einstellungen -> Allgemein -> INFO** und dort ganz unten.

Die Frage ist nun natürlich, ob es reicht, sein iPhone völlig neu wiederherzustellen UND es dann mit einer T-Mobile SIM zu aktivieren. Ich denke, das Zertifikat ist dann einmalig erstellt worden (durch die SIM) und funktioniert wohl weil man sich ja kein oft benutztes Zertifikat teilen muss, auch wenn man es später jailbreaked. Unterstützt wird meine These durch einen ausführlichen [Kommentar](__GHOST_URL__/14/jailbreak-iphone-3g-oder-3gs-mit-baseband-05-11-07-und-blackra1n/comment-page-1#comment-36415) zu diesem Thema von *Peacecare*. Danke sehr.

[**Update**]

Es gibt nun eine kostenlose Hilfe, einen [kostenlosen Pushfix](__GHOST_URL__/02/neuer-pushfix-kostenlos-fur-das-iphone). Er wird über Cydia installiert.
