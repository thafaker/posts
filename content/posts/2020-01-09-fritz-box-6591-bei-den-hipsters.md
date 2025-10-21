---
title: FRITZ!Box 6591 Cable bei den Hipsters
slug: fritz-box-6591-bei-den-hipsters
date_published: 2020-01-09T18:12:19.000Z
date_updated: 2020-01-09T18:12:19.000Z
tags: internet, wlan, fritzbox, 6591, cable
---

**Wir** sind ja große Freunde von Technik, aber unsere Netzwerk-Infrastruktur, die haben wir über viele Jahre etwas vernachlässigt. Genau genommen sind wir immer noch auf einem 2009er **ASUS RTN56U**, der uns zwar gute Dienste geleistet hat, mittlerweile aber viele aktuelle Features missen lässt. Allen voran die Zusammenarbeit von 2,4GHz und 5GHz gemeinsam mit einem *Devolo Powerlan /Wlan Repeater*. Das funktioniert nur sporadisch und am Ende genau konträr zu dem, wie es gedacht ist: nämlich das Wlan zu verbessern. Aber auch die allgemeine Geschwindigkeit lässt sehr zu wünschen übrig, unterstützt das Gerät natürlich nicht den aktuellen Stand der Wlan-Funktechnik. 
![Asus RT N56 U Wlan Router (C) Asus.com](__GHOST_URL__/content/images/2020/01/P_setting_fff_1_90_end_500.jpg)Asus RT N56 U Wlan Router (C) Asus.com
Auf der anderen Seite kann man auf dem Gerät ziemlich einfach eine alternative Firmware ([Padavan](https://bitbucket.org/padavan/rt-n56u/src/master/)) aufspielen und hat sogleich einen coolen Linux-Router mit Busybox und einem Paketmanager, der das Einspielen neuer Software zu einer einfachen Sache werden lässt. So ist dann auf dem Asus auch ein Open-VPN Server kein Problem. Aber all das tröstet nicht über die dauerhaften und vor allem nervigen Verbindungsprobleme hinweg, sodass am Ende die Entscheidung hin zu einer Fritz!Box gefallen ist. Und nun war die Frage, was für eine Version wir für unseren Kabelanschluss nutzen wollen. Nach einigem Hin und Her entschieden wir uns für die 6591, die aktuellste und stärkste Fritz!Box für das Kabelnetz.
![Aufrecht stehende Fritz!Box 6591 Cable](__GHOST_URL__/content/images/2020/01/IMG_1359.jpeg)Aufrecht stehende Fritz!Box 6591 Cable
### Kabeldeutschland mit eigenem Router

Seit 2016 gibt es eine Aufhebung des Gerätezwangs, das heißt, auch Kabelanbieter müssen dem Nutzer ein eigenes Modem zugestehen. Das ist im DSL-Bereich schon immer so gewesen, im Kabelnetz haben das die Betreiber aber mit vielen verschiedenen Begründungen immer wieder verhindert. Bis der Gesetzgeber irgendwann mal sein Veto einlegte und die Firmen dazu zwang. 
![Die Fritzbox im Vergleich zum Kabelmodem sagemcom fast5460](__GHOST_URL__/content/images/2020/01/IMG_1360.jpeg)Die Fritzbox im Vergleich zum Kabelmodem sagemcom fast5460
Die Betreiber haben dazu unterschiedliche Wege eingeschlagen, bei Kabeldeutschland/Vodafone läuft das über einen sogenannten **Aktivierungscode**, den man als Neukunde zugeschickt bekommt. Das ist ein unscheinbares Schreiben und die Nummer folgt der Art: **ABCDE-ABC1E-A1BC2**. Wenn man seine Hardware das erste mal zusammen baut und anschließt, muss das Modem "registriert" werden, was über diesen Aktivierungscode geschieht. Ich bin bereits länger schon Kunde bei Kabeldeutschland und habe mich erst jetzt dazu entschieden, ein eigenes Modem zu verwenden, wollte aber auch keine 7 Euro im Monat Leihgebühr für ein Gerät von Vodafone zahlen. 
![](__GHOST_URL__/content/images/2020/01/IMG_1358-1.jpeg)Fritz!Box Rückseite
Da die Dokumente nur 13 Monate im Kundenportal gespeichert werden, war mein Schreiben mit dem Aktivierungscode nicht mehr abrufbar. Zum Glück hatte ich es mir damals als PDF gespeichert. Falls ihr diesen Code nicht mehr finden könnt, dann müsst ihr euch einen neuen zusenden lassen. Dies geschieht meist per Post, sodass man einige Tage warten muss. Prüft das vorher, bevor ihr euer Modem kauft, alles umbaut und dann nicht aktivieren könnt. Die Zusendung eines neuen Codes geschieht im Kundenportal.
![Die Fritz!Box mit Zubehör: Lankabel, Coaxkabel, Analog-Telefonanschluss, Netzteil (nicht im Bild)](__GHOST_URL__/content/images/2020/01/IMG_1356.jpeg)Die Fritz!Box mit Zubehör: Lankabel, Coaxkabel, Analog-Telefonanschluss, Netzteil (nicht im Bild)
#### Aktivierung des Anschlusses

Die Aktivierung des Anschlusses bzw. die *Provisionierung* des freien Endgeräts mit dem Kabelnetz erfordert mehrere Schritte:

1. Verbindung des neuen Routers mit dem PC mittels LAN oder WLAN
2. Öffnen einer beliebigen Seite im Browser, es öffnet sich das Aktivierungsportal von Vodafone Kabel Deutschland
3. Eingabe der Kundennummer und des Aktivierungscodes (wie oben bereits ausgeführt) in der Maske; Anschließend wird die MAC-Adresse des eigenen Endgeräts angezeigt.
4. Das Feld "Nutzungsbedingungen gelesen und akzeptiert" markieren und auf "Kabelmodem aktivieren" klicken. Anschließend werden die SIP-Zugangsdaten angezeigt, die für die Telefonie benötigt werden.
**Wichtig: Diese Daten lassen sich zwar auch zu einem späteren Zeitpunkt noch im MeinKabel-Kundenportal abrufen bzw. neu erzeugen (SIP-Passwort), dennoch empfiehlt es sich, die Zugangsdaten zur Sicherheit abzuspeichern.** Diese müssen später in der Fritzbox eingetragen werden, damit die Telefonie funktioniert.
5. Neustart des Modems bzw. Routers, um die Aktivierung abzuschließen
Falls das Endgerät nicht neu gestartet wird, muss man den Aktivierungsprozess von vorne beginnen.

Das wars auch schon wieder. Der Anschluss und die Aktivierung der Fritz!Box dauerten keine 20 Minuten. Fortan stehen mir 213 MBit Down und 13,2 MBit Upload zur Verfügung. Alles funktioniert wie gewünscht.

![](__GHOST_URL__/content/images/2020/01/IMG_1348-1.jpeg)

![](__GHOST_URL__/content/images/2020/01/IMG_1356-1.jpeg)

![](__GHOST_URL__/content/images/2020/01/IMG_1359-1.jpeg)

![](__GHOST_URL__/content/images/2020/01/IMG_1360-1.jpeg)

![](__GHOST_URL__/content/images/2020/01/IMG_1358.jpeg)
