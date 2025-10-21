---
title: iPhone 3Gs mit Baseband 05.16.02 - Die Möglichkeiten
slug: iphone-3gs-mit-baseband-05-16-02
date_published: 2011-08-07T08:59:43.000Z
date_updated: 2018-08-22T09:38:34.000Z
---

[![iPhone 3Gs](//picdump.thafaker.de/2011/08/3gs_artikelbild-150x150.png)](http://picdump.thafaker.de/2011/08/3gs_artikelbild.png)Ich habe mich mal mit den Möglichkeiten beschäftigt die einem obligen, wenn man vor einem iPhone 3Gs mit Telekom Netlock sitzt, welches aus irgendeinem Grund das aktuellste Baseband 05.16.02 aufgespielt hat. Zum Beispiel durch das ungewollte Aktualisieren auf die aktuellste Firmware iOS 4.3.5 via iTunes.

---

WERBUNG

---

Laut iPhone-Dev-Team wird es definitiv keinen Unlock für diese Baseband Version und die folgenden (05.16.00, 05.15.04, 05.14.02) mehr geben. Da das iPhone 4 auf dem Markt ist, haben die Hacker andere Prioritäten und die alten Löcher sind durch Apple alle gestopft worden, heißt, frühere Geschichten funktionieren nicht mehr. *No way*! Eine Hoffnung gibt es allerdings, nur leider ist die Mitteilung darüber auch schon etwas älter: Musclenerd vom DevTeam hat in [diesem Tweet (archiviert)](http://web.archive.org/web/20250905043545/https://twitter.com/) angekündigt, dass man zwar keine individuellen Baseband Unlock[![Bildschirmfoto 2011-08-07 um 13.38.42](//picdump.thafaker.de/2011/08/Bildschirmfoto-2011-08-07-um-13.38.42-150x150.png)](__GHOST_URL__/iphone-3gs-mit-baseband-05-16-02/bildschirmfoto-2011-08-07-um-13-38-42/) bauen wird, aber eine Prozedur erstellen wird, mit der man erst auf das iPad-Baseband aktualisiert um dann wieder auf eine (für das iPhone 3Gs vorgesehene und auch Unlock / Jailbreakbare) funktionierende Baseband-Version vom 3Gs zu downgraden. Gut ist dies, weil die vom iPad ja bekannte Probleme hat, wie weiter unten im Artikel beschrieben wird. ACHTUNG: Dieser Downgrade ist noch nicht erhältlich und es ist unbekannt, wann er veröffentlicht wird... und ob überhaupt.

Es sieht also düster aus, man hat nun einen Haufen Schrott vor sich mit dem man nicht mehr telefonieren kann, sofern man nicht zur Telekom wechseln will, denn damit funktioniert es natürlich immer.

**Was gibt es für Möglichkeiten** (click)?

- [HowTo Unlock mit Hilfe des iPad Basebands](__GHOST_URL__/iphone-3gs-mit-baseband-05-16-02/#Unlock_Anleitung)
- [Benutzung der Gevey Ultrasim Karte eines iPhone 4](__GHOST_URL__/iphone-3gs-mit-baseband-05-16-02/#Gevey_Sim)

Irgendwann fand jemand heraus, dass man die Baseband-Version 06.15.00 des iPads unlocken kann und schlug vor, iPhones auf dieses Baseband zu aktualisieren, also ein iPad Baseband auf dem 3Gs zu installieren. Das DevTeam bastelte diese Option auch gleich in Redsn0w ein und los ging die Fahrt. Bei diesem Unlock muss also zuerst mittels redsn0w die iPad-Baseband (06.15.00) auf das iPhone gespielt werden, die dann entsperrt wird.

Mittlerweile warnt das iPhone [DevTeam (archiviert)](http://web.archive.org/web/20101130022459/http://blog.iphone-dev.org/post/1718400992/ultra-recycle) aber ausdrücklich davor, das 3G oder 3Gs auf ebenjene iPad Firmware zu aktualisieren, weil man erst später, zu spät, heraus fand, das ein paar gravierende Probleme entstehen.

iPhone 3GS Unlock Anleitung – Baseband 05.14.02 / 05.15.04 / 05.16.00 / 05.16.02 – Ultrasn0w

Dies sind die Konsequenzen des iPad-Basebands auf einem iPhone:

1. Es ist nicht möglich ein Downgrade von der Baseband 06.15.00 durchzuführen. Ihr werdet also eure Garantie verlieren, da Apple sieht welche Baseband-Version sich auf eurem iPhone befindet.
2. Sollten in Zukunft kritische Bug-Fixes kommen, so wird eure Baseband nicht aktualisiert, solange die neue iOS die Baseband 05.xx beinhaltet.
3. Wenn ihr eine Wiederherstellung der iOS durchführen wollt, so wird diese fehlschlagen. Dies ist dann generell nur mit einer Custom Firmware möglich.
4. GPS-Funktion fällt aus.
5. Noch mal zu Punkt 1. Ihr werdet das wahrscheinlich nie wieder entfernen können, man kann nur ein Baseband-Downgrade durchführen, wenn Apple selbst höhere Nummerierungen verwendet, aber Apple wird wohl weiterhin bei der 05. Zählweise bleiben...

Da viele danach fragen, wird es hier jetzt dennoch ein How To geben wie man sein 3Gs auf das iPad Baseband aktualisiert und dann wieder mittels Ultrasn0w unlocked - aber wir würden das nicht tun und ihr tut es natürlich auf eigene Gefahr hin, ihr verliert die Garantie bei Apple!

# Unlock Tools:

- [Redsn0w 0.9.6rc16 (archiviert)](http://web.archive.org/web/20120614030331/https://rapidshare.com/files/461331023/redsn0w_win_0.9.6rc16.zip) für Windows
- [Redsn0w 0.9.6rc16 (archiviert)](http://web.archive.org/web/20120614024401/https://rapidshare.com/files/461331035/redsn0w_mac_0.9.6rc16.zip) für Mac

- iOS 4.1 (iPhone 3GS): [iPhone2,1_4.1_8B117_Restore.ipsw](http://appldnld.apple.com/iPhone4/061-7938.20100908.F3rCk/iPhone2,1_4.1_8B117_Restore.ipsw)
- iOS 4.2.1 (iPhone 3GS): [iPhone2,1_4.2.1_8C148a_Restore.ipsw](http://appldnld.apple.com/iPhone4/061-9895.20101122.Cdew2/iPhone2,1_4.2.1_8C148a_Restore.ipsw)
- iOS 4.3.3 (iPhone 3GS): [iPhone2,1_4.3.3_8J2_Restore.ipsw](http://appldnld.apple.com/iPhone4/041-1009.20110503.M73Yr/iPhone2,1_4.3.3_8J2_Restore.ipsw)

## Anleitung HowTo für Unlock mit Ultrasn0w für iPhone 3GS

1. Die Screenshots stammen zwar aus Windows, sind aber identisch mit denen der OS X Version.
2. Euer iPhone muss bereits gejailbreakt sein (hier für 3Gs [4.3.3](__GHOST_URL__/jailbreak-fuer-ios-4-3-3/) oder [4.3.1](__GHOST_URL__/jailbreak-untethered-jailbreak-fuer-ios-4-3-1-verfuegbar-pwnagetool/))
3. iPhone anschließen
4. Redsn0w starten (Windows 7 / Vista Benutzer, redsn0w als Administrator im “XP Kompatibilitäts-Modus” ausführen)
5. Klickt nun auf **Browse**, wählt die auf eurem iPhone installierte iOS aus (iOS 4.1 / iOS 4.2.1 / iOS 4.3.3 - Downloadlink oben) und klickt auf **Next**.
![1](//picdump.thafaker.de/2011/08/1.jpeg)
6. Wählt nur “**Install iPad baseband**” aus und bestätigt die Meldung mit **Ja**![2](//picdump.thafaker.de/2011/08/2.png)![3](//picdump.thafaker.de/2011/08/3.png)
7. **Schaltet euer iPhone aus** und klickt nochmals auf **Next**.
8. Nun müsst ihr das iPhone wie folgt in den **DFU-Mod**e bringen:

1. Den **Home-Button** und **Power Button** gleichzeitig für 10 Sekunden drücken
2. Jetzt den **Power Button loslassen** und den **Home-Button** für weitere 10 Sekunden gedrückt halten.

9. Seit ihr erfolgreich in den DFU-Modus gekommen, so spielt RedSn0w das iPad Baseband ein und klickt zum Schluss auf **Finish**.
10. Startet euer iPhone
11. Vergewissert euch, dass ihr eine Internetverbindung habt (WiFi)
12. Startet **Cydia**
13. Geht rechts unten auf **Suche, **gebt **ultrasn0w** ein, auswählen und installieren.
![4](//picdump.thafaker.de/2011/08/4.jpeg)
14. Danach noch ein **Neustart **durchführen nun solltet ihr ein Netz empfangen.
![5](//picdump.thafaker.de/2011/08/5.jpeg)

Das war es auch schon, jetzt habt ihr ein jailbroken sowie entsperrtes iPhone 3Gs.

## Gevey Sim Karte des iPhone 4 mit 3Gs nutzen?
[![ultra2](//picdump.thafaker.de/2011/08/ultra2-150x150.jpg)](http://picdump.thafaker.de/2011/08/ultra2.jpg)Es gibt im Netz seit dem iPhone 2G aka iPhone Classic auch sogenannte Turbo -oder Ultra Sims, die allerdings in einem sehr schlechten Ruf standen. Diese Simkarten werden zusammen mit der normalen Simkarte in das iPhone eingesteckt und ermöglichen durch einen zusätzlichen Chip die Umgehung der Netlock-Sperre des iPhones.

Klingt ziemlich gut, denn man braucht hier keinen Software-Unlock aka Ultrasn0w vom DevTeam oder ähnliches und muss auch nichts weiter auf dem iPhone installieren, die ganze Arbeit verrichtet hier der Chip und das Telefon funktioniert mit jeder Simkarte.

Für das iPhone 3Gs ist solch eine Ultrasim allerdings nie veröffentlicht worden, wohl aber für das iPhone 4 mit seinen Basebands.

Laut eines [Tweets](http://www.maheshkukreja.com/gevey-112-exploit-works-on-iphone-3gs-baseband-051602-as-well) eines der Entwickler der Gevey Sim funktioniert dieser Hardware-Unlock theoretisch auch mit einem 3Gs. Warum nur theoretisch? Weil das iPhone 4 eine Micro-Simkarte benötigt und das iPhone 3Gs eine normale Mini-Simkarte. Die Gevey passt also nicht.

[![gevey_works](//picdump.thafaker.de/2011/08/gevey_works.jpg)](http://picdump.thafaker.de/2011/08/gevey_works.jpg)

Er schreibt, dass eine größere Simkarte theoretisch auch im 3Gs funktioniert und das Baseband 05.16.02 des iPhone 3Gs entsperren würde. Nun habe ich weiter recherchiert und leider nirgendwo einen Hinweis finden können, dass es jemand wirklich probiert hätte.

In einem Forum -dessen Link ich nicht mehr finde- jedoch steht der Hinweis, dass man mit etwas Klebeband die Gevey Sim zusammen mit der normalen Sim im 3Gs platzieren kann und dies durchaus funktionieren würde.

@[Sherif_Hashim (archiviert)](http://web.archive.org/web/20250905102106/https://twitter.com/), DevTeam Mitglied und iPhone Baseband Hacker schlägt auch die Gevey Sim vor, allerdings in Verbindung mit dem iPhone 4, bei ihm läuft das problemlos, die Sim an sich scheint also okay zu sein.

Leider kostet die Gevey knapp 30 Dollar via eBay und das ist wohl auch der Grund, warum das nicht einfach mal jemand probiert: Leute ohne teuren Telekom-Vertrag haben eben auch nicht die Kohle um eben mal knapp 30 Tacken raus zu werden, bei der Gefahr, dass es nicht funktioniert. In diesem [Forum (archiviert)](http://web.archive.org/web/20110717125847/http://www.boerse.bz:80/hard-software/apple/iphone-ipod-touch/747889-gevey-sim-aufklaerung-faq-13.html) wird auch nur missmutig über das 3Gs mit einer Gevey gesprochen. Es scheint eine hakelige Angelegenheit zu sein die nicht zwingend immer funktioniert.

Und mehr kann ich auch nicht sagen. Hat denn jemand meiner Leser diesen Tandem versucht? Hat jemand ein funktionierendes gelocktes iPhone 3Gs mit BB 05.16.02 und der Gevey Sim zum Laufen bekommen?

Es folgt eine Übersicht der aktuellen Jailbreak/Unlock-Möglichkeiten für alle iDevices und die spezifischen iOS-Versionen sowie deren Basebands.

---

**Aktueller Jailbreak-Status**:
**iOS**3G3GS4iPad 1ATViPad 24.2.1[![J](//www.benm.at/wp-content/plugins/jailbreak/geht.png) (Link nicht mehr verfügbar)](http://i.benm.at/eZH7VX)[![J](//www.benm.at/wp-content/plugins/jailbreak/geht.png) (Link nicht mehr verfügbar)](http://i.benm.at/eZH7VX)[![J](//www.benm.at/wp-content/plugins/jailbreak/geht.png) (Link nicht mehr verfügbar)](http://i.benm.at/eZH7VX)[![J](//www.benm.at/wp-content/plugins/jailbreak/geht.png) (Link nicht mehr verfügbar)](http://i.benm.at/eZH7VX)[![J](//www.benm.at/wp-content/plugins/jailbreak/geht.png) (Link nicht mehr verfügbar)](http://i.benm.at/eZH7VX)-4.3-[![J](//www.benm.at/wp-content/plugins/jailbreak/geht.png) (Link nicht mehr verfügbar)](http://i.benm.at/eNTz8V)[![J](//www.benm.at/wp-content/plugins/jailbreak/geht.png) (Link nicht mehr verfügbar)](http://i.benm.at/eNTz8V)[![J](//www.benm.at/wp-content/plugins/jailbreak/geht.png) (Link nicht mehr verfügbar)](http://i.benm.at/eNTz8V)[![J](//www.benm.at/wp-content/plugins/jailbreak/geht.png) (Link nicht mehr verfügbar)](http://i.benm.at/m3DNn1)![N](//www.benm.at/wp-content/plugins/jailbreak/nein.png)4.3.1-[![J](//www.benm.at/wp-content/plugins/jailbreak/geht.png) (Link nicht mehr verfügbar)](http://i.benm.at/eNTz8V)[![J](//www.benm.at/wp-content/plugins/jailbreak/geht.png) (Link nicht mehr verfügbar)](http://i.benm.at/eNTz8V)[![J](//www.benm.at/wp-content/plugins/jailbreak/geht.png) (Link nicht mehr verfügbar)](http://i.benm.at/eNTz8V)[![J](//www.benm.at/wp-content/plugins/jailbreak/geht.png) (Link nicht mehr verfügbar)](http://i.benm.at/m3DNn1)![N](//www.benm.at/wp-content/plugins/jailbreak/nein.png)4.3.2-[![J](//www.benm.at/wp-content/plugins/jailbreak/geht.png) (Link nicht mehr verfügbar)](http://i.benm.at/eNTz8V)[![J](//www.benm.at/wp-content/plugins/jailbreak/geht.png) (Link nicht mehr verfügbar)](http://i.benm.at/eNTz8V)[![J](//www.benm.at/wp-content/plugins/jailbreak/geht.png) (Link nicht mehr verfügbar)](http://i.benm.at/eNTz8V)[![J](//www.benm.at/wp-content/plugins/jailbreak/geht.png) (Link nicht mehr verfügbar)](http://i.benm.at/m3DNn1)![N](//www.benm.at/wp-content/plugins/jailbreak/nein.png)4.3.3-[![J](//www.benm.at/wp-content/plugins/jailbreak/geht.png) (Link nicht mehr verfügbar)](http://i.benm.at/iZOgQK)[![J](//www.benm.at/wp-content/plugins/jailbreak/geht.png) (Link nicht mehr verfügbar)](http://i.benm.at/iZOgQK)[![J](//www.benm.at/wp-content/plugins/jailbreak/geht.png) (Link nicht mehr verfügbar)](http://i.benm.at/iZOgQK)[![J](//www.benm.at/wp-content/plugins/jailbreak/geht.png) (Link nicht mehr verfügbar)](http://i.benm.at/m3DNn1)[![J](//www.benm.at/wp-content/plugins/jailbreak/geht.png) (Link nicht mehr verfügbar)](http://i.benm.at/pFkFM2)4.3.4-[![T](//www.benm.at/wp-content/plugins/jailbreak/tethered.png) (Link nicht mehr verfügbar)](http://i.benm.at/pPSq0P)[![T](//www.benm.at/wp-content/plugins/jailbreak/tethered.png) (Link nicht mehr verfügbar)](http://i.benm.at/pPSq0P)[![T](//www.benm.at/wp-content/plugins/jailbreak/tethered.png) (Link nicht mehr verfügbar)](http://i.benm.at/pPSq0P)--**Aktueller Unlock-Status**:
**Baseband**iPhone 3GiPhone 3GSiPhone 401.59.00--![J](//www.benm.at/wp-content/plugins/jailbreak/geht.png)02.10.04--![N](//www.benm.at/wp-content/plugins/jailbreak/nein.png)03.10.01--![N](//www.benm.at/wp-content/plugins/jailbreak/nein.png)05.13.04![J](//www.benm.at/wp-content/plugins/jailbreak/geht.png)![J](//www.benm.at/wp-content/plugins/jailbreak/geht.png)-05.12.01![J](//www.benm.at/wp-content/plugins/jailbreak/geht.png)![J](//www.benm.at/wp-content/plugins/jailbreak/geht.png)-04.26.08![J](//www.benm.at/wp-content/plugins/jailbreak/geht.png)![J](//www.benm.at/wp-content/plugins/jailbreak/geht.png)-05.11.07![J](//www.benm.at/wp-content/plugins/jailbreak/geht.png)![J](//www.benm.at/wp-content/plugins/jailbreak/geht.png)-05.16.00-![N](//www.benm.at/wp-content/plugins/jailbreak/nein.png)-05.16.02-![N](//www.benm.at/wp-content/plugins/jailbreak/nein.png)-04.10.01--![N](//www.benm.at/wp-content/plugins/jailbreak/nein.png)06.15.00![J](//www.benm.at/wp-content/plugins/jailbreak/geht.png)![J](//www.benm.at/wp-content/plugins/jailbreak/geht.png)-05.15.02![J](//www.benm.at/wp-content/plugins/jailbreak/geht.png)![J](//www.benm.at/wp-content/plugins/jailbreak/geht.png)-05.15.04![T](//www.benm.at/wp-content/plugins/jailbreak/tethered.png)![T](//www.benm.at/wp-content/plugins/jailbreak/tethered.png)-
[**Update**] Ich bin mir nicht sicher da ich dies nicht testen konnte, aber vielleicht bringt einem ja die Möglichkeit der [iOS 5 Beta 6 Jailbreak](__GHOST_URL__/sn0wbreeze-jailbreak-fur-ios-5-beta/) Variante etwas?

---

*Um auf dem Laufenden zu bleiben, könnt ihr uns auf **[Twitter (archiviert)](http://web.archive.org/web/20250905043545/https://twitter.com/)** folgen oder die **[Facebook-Seite](http://de-de.facebook.com/pages/thafaker-auf-Beton/154600141278763)** besuchen.*

---
