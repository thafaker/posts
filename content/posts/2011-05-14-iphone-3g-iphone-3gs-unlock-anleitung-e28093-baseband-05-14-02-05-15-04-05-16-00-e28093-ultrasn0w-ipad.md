---
title: iPhone 3G / iPhone 3GS Unlock Anleitung – Baseband 05.14.02 / 05.15.04 / 05.16.00 – Ultrasn0w (iPad)
slug: iphone-3g-iphone-3gs-unlock-anleitung-e28093-baseband-05-14-02-05-15-04-05-16-00-e28093-ultrasn0w-ipad
date_published: 2011-05-14T11:31:13.000Z
date_updated: 2018-08-22T09:38:38.000Z
---

---

### Vorwort

Diese Anleitung erklärt, wie man einen **Unlock **fürs** iPhone 3G** und **iPhone 3GS **durchführen kann. Dafür muss euer iPhone gejailbreakt sein (Anleitungen findet ihr weiter unten).

Solltet ihr eine der folgenden aufgelisteten Basebands (Modemfirmware) auf eurem iPhone haben so könnt ihr diese Anleitung durchführen. Lest jedoch unbedingt die Warnung durch!! Welche Baseband-Version ihr auf eurem iPhone habt, findet ihr unter **Einstellungen > Allgemein > Info > Modem-Firmware**.

- 05.14.02
- 05.15.04
- 05.16.00

---

### WARNUNG

Das **iPhone [DevTeam (archiviert)](http://web.archive.org/web/20101130022459/http://blog.iphone-dev.org/post/1718400992/ultra-recycle) warnt ausdrücklich diese Anleitung nur durchzuführen**, wenn ihr die **Baseband 05.14.02** oder **05.15.04** bereits auf eurem iPhone habt. **Alle anderen sollten diese Anleitung meiden!**
Bei diesem Unlock muss zuerst mittels redsn0w die iPad-Baseband (06.15.00) auf euer iPhone gespielt werden, die dann entsperrt wird.

Was die **Konsequenzen** für dieses Baseband-Update bedeuten kann, seht ihr hier:

1. Es ist nicht möglich ein Downgrade von der Baseband 06.15.00 durchzuführen. Ihr werdet also eure Garantie verlieren, da Apple sieht welche Baseband-Version sich auf eurem iPhone befindet.
2. Sollten in Zukunft kritische Bug-Fixes kommen, so wird eure Baseband nicht aktualisiert, solange die neue iOS die Baseband 05.xx beinhaltet.
3. Wenn ihr eine Wiederherstellung der iOS durchführen wollt, so wird diese fehlschlagen. Dies ist dann nur mit einer Custom Firmware möglich.

**Nochmals: Führt dieses Update auf die 06.15.00 nicht durch, wenn ihr es nicht braucht! Nur wenn ihr einen Unlock für 05.14.02, 05.15.04 oder 05.16.00 benötigt, könnt ihr dies durchführen. Natürlich müsst ihr dann mit den oben angeführten Konsequenzen rechnen.**
---

### Kompatibilitätsliste von Ultrasn0w:

- **iPhone 3G / iPhone 3GS:**
- Baseband 04.26.08 (iPhone Firmware 3.0)
- Baseband 05.11.07 (iPhone Firmware 3.1.2)
- Baseband 05.12.01 (iPhone Firmware 3.1.3)
- Baseband 05.13.04 (iOS 4.0, iOS 4.0.1, iOS 4.0.2)
- Baseband 06.15.00 (iPad)

### Jailbreak Anleitungen:

- **iOS 4.1 (iPhone 3G / 3GS):**
- [Jailbreak-Anleitung iPhone 3G](__GHOST_URL__/iphone-3g-iphone-3gs-iphone-4-ios-4-1-%E2%80%93-jailbreak-unlock-anleitung-windows-%E2%80%93-custom-firmware-%E2%80%93-redsn0w-2/)
- [Jailbreak-Anleitung iPhone 3GS](__GHOST_URL__/iphone-3g-iphone-3gs-iphone-4-ios-4-1-%E2%80%93-jailbreak-unlock-anleitung-windows-%E2%80%93-custom-firmware-%E2%80%93-redsn0w-2/)

- **iOS 4.2.1 (iPhone 3G / 3GS: Baseband 05.15.04):**
- [Jailbreak-Anleitung iPhone 3G](http://www.ma3xl3.com/iphone/iphone-3g-iphone-3gs-iphone-4-ios-4-1-jailbreak-unlock-anleitung-windows-custom-firmware-redsn0w/)
- [Jailbreak-Anleitung iPhone 3GS](http://www.ma3xl3.com/iphone/iphone-3g-iphone-3gs-iphone-4-ios-4-1-jailbreak-unlock-anleitung-windows-custom-firmware-redsn0w/) (tethered)

### Unlock Tools:

- [Redsn0w 0.9.6rc8](https://sites.google.com/a/iphone-dev.com/files/home/redsn0w_win_0.9.6rc8.zip?attredirects=0&amp;d=1)für **Windows**
- [Redsn0w 0.9.6rc8](https://sites.google.com/a/iphone-dev.com/files/home/redsn0w_mac_0.9.6rc8.zip?attredirects=0&amp;d=1) für **Mac**

- iOS 4.1 (iPhone 3GS): [iPhone2,1_4.1_8B117_Restore.ipsw](http://appldnld.apple.com/iPhone4/061-7938.20100908.F3rCk/iPhone2,1_4.1_8B117_Restore.ipsw)
- iOS 4.1 (iPhone 3G):  [iPhone1,2_4.1_8B117_Restore.ipsw](http://appldnld.apple.com/iPhone4/061-7932.20100908.3fgt5/iPhone1,2_4.1_8B117_Restore.ipsw)

- iOS 4.2.1 (iPhone 3GS): [iPhone2,1_4.2.1_8C148a_Restore.ipsw](http://appldnld.apple.com/iPhone4/061-9895.20101122.Cdew2/iPhone2,1_4.2.1_8C148a_Restore.ipsw)
- iOS 4.2.1 (iPhone 3G): [iPhone1,2_4.2.1_8C148_Restore.ipsw](http://appldnld.apple.com/iPhone4/061-9853.20101122.Vfgt5/iPhone1,2_4.2.1_8C148_Restore.ipsw)

Achtet bitte darauf das ihr nicht sofort ein Update der kommenden iPhone Firmwares von Apple installiert. Wartet bis sich das Dev-Team dazu geäußert hat. Ansonsten kann es sein, dass ihr für immer den Jailbreak oder Unlock verliert, wenn ihr frühzeitig eine Aktualisierung durchführt!

### Anleitung für Unlock mit Ultrasn0w für iPhone 3GS, iPhone 3G

1. Euer iPhone muss bereits gejailbreakt sein (Anleitungen weiter oben)
2. iPhone anschließen
3. Redsn0w starten (Windows 7 / Vista Benutzer, redsn0w als Administrator im “XP Kompatibilitäts-Modus” ausführen)
4. Klickt nun auf **Browse**, wählt die auf eurem iPhone installierte iOS aus (iOS 4.1 oder iOS 4.2.1 - Downloadlink oben) und klickt auf **Next**.
[![redsn0w3gios4start_thumb.jpg](//picdump.thafaker.de/2010/09/redsn0w3gios4start_thumb.jpg)](http://picdump.thafaker.de/2010/09/redsn0w3gios4start_thumb.jpg)
5. Wählt nur “**Install iPad baseband**” aus und bestätigt die Meldung mit **Ja**[![redsn0w-0.9.6b5-install-ipad-baseband](//picdump.thafaker.de/2011/08/redsn0w-0.9.6b5-install-ipad-baseband.png)](http://picdump.thafaker.de/2011/08/redsn0w-0.9.6b5-install-ipad-baseband.png)[![redsn0w-0.9.6b5-BB-wanring](//picdump.thafaker.de/2011/08/redsn0w-0.9.6b5-BB-wanring.png)](http://picdump.thafaker.de/2011/08/redsn0w-0.9.6b5-BB-wanring.png)
6. **Schaltet euer iPhone aus** und klickt nochmals auf **Next**.
7. Nun müsst ihr das iPhone wie folgt in den **DFU-Mod**e bringen:

1. Den **Home-Button** und **Power Button** gleichzeitig für 10 Sekunden drücken
2. Jetzt den **Power Button loslassen** und den **Home-Button** für weitere 10 Sekunden gedrückt halten.

8. Seit ihr erfolgreich in den DFU-Modus gekommen, so spielt RedSn0w das iPad Baseband ein und klickt zum Schluss auf **Finish**.
9. Startet euer iPhone
10. Vergewissert euch, dass ihr eine Internetverbindung habt (WiFi)
11. Startet **Cydia**
12. Geht rechts unten auf **Suche, **gebt **ultrasn0w**ein, auswählen und installieren.[![ultrasn0w-0.1-1-unlock1](//picdump.thafaker.de/2010/08/ultrasn0w-0.1-1-unlock1.jpg)](http://picdump.thafaker.de/2010/08/ultrasn0w-0.1-1-unlock1.jpg)
13. Danach noch ein **Neustart **durchführen nun solltet ihr ein Netz empfangen.[![ultrasn0w-0.1-1-unlock2](//picdump.thafaker.de/2010/08/ultrasn0w-0.1-1-unlock2.jpg)](http://picdump.thafaker.de/2010/08/ultrasn0w-0.1-1-unlock2.jpg)

Viel Spaß mit eurem entsperrten iPhone das nun mit einem iPad Baseband läuft, niemals mehr ein Downgrade erfahren wird und welches in diesem Moment GPS verloren hat. ABER HEY, wir haben euch ausdrücklich gewarnt!

---

### Wichtig: Sichert eure SHSH vom iPhone:

- Das [Tutorial und alle Infos zum SHSH-Blob (Link nicht mehr verfügbar)](../2011/06/tiny-umbrella-shsh-sichern-und-wiederherstellen/) findet ihr hier.

**Hinweis**: thafaker.de haftet bei eventuellen Schäden am PC, Mac, iPhone oder anderen Dingen, die aufgrund dieser Anleitung hervorgerufen wurden nicht. Die Verwendung dieser Anleitung geschieht auf eigener Gefahr!
