---
title: iPhone 3G / iPhone 3GS / iPhone 4 iOS 4.1 – Jailbreak & Unlock Anleitung – PwnageTool
slug: iphone-3g-iphone-3gs-iphone-4-ios-4-1-e28093-jailbreak-unlock-anleitung-e28093-pwnagetool
date_published: 2010-10-20T11:31:07.000Z
date_updated: 2018-08-22T09:38:16.000Z
---

---

### Vorwort

Diese Anleitung erklärt den **Jailbreak **für das **iPhone 3G**, **iPhone 3GS **und **iPhone 4** mit der **iOS 4.1 **unter **Mac****. **
### **Infos für Unlocker:**
Wie ihr euer iPhone **Unlocked **findet ihr weiter unten.

**Wichtig**: Ihr dürft **keinesfalls die original iOS 4.1 Firmware auf euer Gerät aufspielen**, da sonst das Baseband (Modem Firmware) aktualisiert wird und Ultrasn0w für den Unlock nicht mehr verwenden kann. Die Baseband fürs **iPhone 3G / 3GS** darf die Version **05.13.04** bzw. fürs **iPhone 4** die Version **01.59.00 nicht überschreiten**. Ansonsten funktioniert der Unlock nicht und ihr könnte euer iPhone nicht mehr frei schalten. Wenn dies bereits geschehen ist, könnte ihr [folgenden Artikel lesen](__GHOST_URL__/iphone-3gs-mit-baseband-05-16-02/) - viel Hoffnung kann ich allerdings nicht machen.

Unter **Einstellungen > Allgemein > Info > Modem-Firmware** könnt ihr nachsehen welche Baseband Version ihr habt.

---

### Wichtig für die Zukunft:

Achtet bitte darauf, **nicht** sofort ein **Update** der **kommenden iPhone Firmwares (iOS)** von Apple zu installieren. Wartet bis sich das Dev-Team dazu geäußert hat. Ansonsten kann es sein, dass ihr für immer den Jailbreak oder Unlock verliert, wenn ihr frühzeitig eine Aktualisierung durchführt! Sichert auch euren **SHSH-Blob**! Die Anleitung findet ihr [hier](__GHOST_URL__/tiny-umbrella-shsh-sichern-und-wiederherstellen/).

Ladet die Dateien am Besten mit dem Firefox oder Google Chrome herunter und speichert am besten alles auf dem Desktop. Unter Safari Mac führt dies meistens zu Problemen weil Safari die Firmwares direkt entpackt, man kann die aber nicht entpacken: der Download ist dann futsch.

---

### Jailbreak Software:

- **[PwnageTool (archiviert)](http://web.archive.org/web/20101021215847/http://blog.iphone-dev.org:80/post/1359246784/20102010-event) für **Mac****

### iPhone Firmware:

- iOS 4.1 (iPhone 4): [iPhone3,1_4.1_8B117_Restore.ipsw](http://appldnld.apple.com/iPhone4/061-7939.20100908.Lcyg3/iPhone3,1_4.1_8B117_Restore.ipsw)
- iOS 4.1 (iPhone 3GS): [iPhone2,1_4.1_8B117_Restore.ipsw](http://appldnld.apple.com/iPhone4/061-7938.20100908.F3rCk/iPhone2,1_4.1_8B117_Restore.ipsw)
- iOS 4.1 (iPhone 3G): [iPhone1,2_4.1_8B117_Restore.ipsw](http://appldnld.apple.com/iPhone4/061-7932.20100908.3fgt5/iPhone1,2_4.1_8B117_Restore.ipsw)

---

### Anleitung Jailbreak iOS 4.1 für iPhone 4 / iPhone 3GS / iPhone 3G:

1. **iTunes** auf die **Version 10.0** updaten
2. iPhone anschließen und iTunes öffnen
3. Erstellt sicherheitshalber ein Backup. **Rechtsklick auf euer iPhone**, dann auf **Synchronisieren** klicken.
[![iphone_synchronisieren](//picdump.thafaker.de/2011/08/iphone_synchronisieren.png)](http://picdump.thafaker.de/2011/08/iphone_synchronisieren.png)
4. Startet das **PwnageTool**.
5. Vergewissert euch, dass ihr im **Anfänger Modus** seid.
6. Klickt auf **iPhone 3G, 3GS, 4**und dann auf den blauen Pfeil.[![pwnagetool-pic1](//picdump.thafaker.de/2010/10/pwnagetool-pic1.jpg)](http://picdump.thafaker.de/2010/10/pwnagetool-pic1.jpg)
7. PwnageTool sucht nach der Firmware, die ihr bereits auf euren Desktop geladen habt. Klickt diese an und dann weiter.[![pwnagetool-pic2](//picdump.thafaker.de/2010/10/pwnagetool-pic2.jpg)](http://picdump.thafaker.de/2010/10/pwnagetool-pic2.jpg)
8. Bei der Meldung ob fortgesetzt werden soll, klickt ihr auf YES.
[![pwnagetool-pic3](//picdump.thafaker.de/2010/10/pwnagetool-pic3.jpg)](http://picdump.thafaker.de/2010/10/pwnagetool-pic3.jpg)
9. Bei der Meldung ob die Aktivierung durch iTunes vorgenommen werden soll, klickt ihr auf **NO**, damit die Baseband nicht aktualisiert wird!
[![pwnagetool-pic4](//picdump.thafaker.de/2010/10/pwnagetool-pic4.jpg)](http://picdump.thafaker.de/2010/10/pwnagetool-pic4.jpg)
10. Jetzt wird eure Custom-Firmware erstellt. Dies kann einige Minuten dauern.[![pwnagetool-pic5](//picdump.thafaker.de/2010/10/pwnagetool-pic5.jpg)](http://picdump.thafaker.de/2010/10/pwnagetool-pic5.jpg)
11. Jetzt müsst ihr das iPhone in den **DFU-Modus**bringen:

1. Schaltet euer iPhone aus.
2. Danach den **Home-Button** und **Power Button** für 10 Sekunden drücken
3. Jetzt den **Power Button loslassen** und den **Home-Button** für weitere 15 Sekunden gedrückt halten.
4. Wenn ihr eine Meldung im iTunes bekommt, dass das iPhone sich im Wartungszustand befindet, habt ihr diesen Schritt richtig gemacht. Ansonsten nochmals Probieren bis es klappt.

12. Auf **Wiederherstellen** mit “**ALT + Linksklick**” (Mac) und die neu erstellte **Custom Firmware **auswählen und Update durchführen. **Keinesfalls**die Original heruntergeladene Datei auswählen!![![itunes-wiederherstellen](//picdump.thafaker.de/2011/08/itunes-wiederherstellen.jpg)](http://picdump.thafaker.de/2011/08/itunes-wiederherstellen.jpg)
13. Nach der Installation, könnt ihr euer Backup in iTunes wiederherstellen.[![itunes-wiederherstellen1](//picdump.thafaker.de/2011/08/itunes-wiederherstellen1-580x245.png)](http://picdump.thafaker.de/2011/08/itunes-wiederherstellen1.png)
14. Auf eurem iPhone solltet ihr nun Cydia finden.

Viel Spaß mit eurem gejailbreakten iPhone!

---

### Unlock iPhone 3G / iPhone 3GS / iPhone 4 für iOS 4.1 (Baseband 05.13.04 / 01.59.00):

Das [Tutorial zum Unlock fürs iPhone 3G / iPhone 3GS / iPhone 4 für die iOS 4.1](__GHOST_URL__/iphone-3g-iphone-3gs-iphone-4-unlock-anleitung-%E2%80%93-baseband-05-13-04-01-59-00-%E2%80%93-ultrasn0w/) mittels ultrasn0w findet ihr hier.

**Hinweis**: thafaker.de haftet bei eventuellen Schäden am PC, Mac, iPhone oder anderen Dingen, die aufgrund dieser Anleitung hervorgerufen wurden, nicht. Die Verwendung dieser Anleitung geschieht auf eigener Gefahr!
