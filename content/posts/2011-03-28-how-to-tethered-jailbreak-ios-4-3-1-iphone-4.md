---
title: How To tethered Jailbreak iOS 4.3.1 iPhone 4
slug: how-to-tethered-jailbreak-ios-4-3-1-iphone-4
date_published: 2011-03-28T16:00:21.000Z
date_updated: 2018-08-22T09:38:38.000Z
---

Wie hier bereits von uns ausführlich berichtet, gibt es seit kurzem einen tethered Jailbreak für das neue iOS 4.3.1 in Verbindung mit dem iPhone 4. Jetzt will ich Schritt für Schritt beschreiben, wie das geht.

Man benötigt außerdem zwangsläufig einen Mac sowie folgende Software:

- [PwnageTool 4.2](http://thepiratebay.org/user/iphonedev/) ([Torrent](http://thepiratebay.org/user/iphonedev/))
- [iTunes 10.2.1](http://www.apple.com/de/itunes/download/)
- [die aktuellste iOS 4.3.1-Firmware](../iphone-firmware/) (in diesem Tut für das iPhone 4)
- [Das PwnageTool-Bundle für iOS 4.3.1 (archiviert)](http://web.archive.org/web/20250214133214/http://rapidshare.com/)
- Das Tool [Tetheredboot](https://sites.google.com/site/0xjohnny/downloads/tetheredboot.zip?attredirects=0) (Google Code)
- Den Universal Ramdisk Fixer (ist Teil des PwnageTool-Bundles)

**Folgende Informationen sind bekannt**:

- Es gibt keinen Unlock für das neue Baseband in iOS 4.3.1
- iPad2 Besitzer sollten vorerst von iOS 4.3.1 Abstand nehmen, bis weitere Infos bekannt sind.
- Cydia funktioniert perfekt und ist für iOS 4.3.1 angepasst worden
- wenn man von einer alten iOS Version upgraded, wird das Baseband mit PwnageTool nicht aktualisiert
- Hacktivation funktioniert

Hier noch ein [zweiter (archiviert)](http://web.archive.org/web/20110501101813/http://www.iphone-privacy.com/) Link für zwei Dateien, die wir hier im Artikel beschrieben haben und die man benötigt.

## Vorbereiten und modifizieren des PwnageTool 4.2

1. **Schritt**: [Downloade](http://rapidshare.com/files/454442372/RedmondPie_PwnageTool_4.3.1_Bundle__2_.zip) das PwnageTool bundle (welches den Universal Ramdisk Fixer enthält) für iOS 4.3.1. Entpacke den .zip Ordner, in Ihm findet man eine .bundle Datei, kopiere die Datei auf den Desktop.
2. **Schritt**: Lade das PwnageTool 4.2 [herunter (archiviert)](http://web.archive.org/web/20110419231941/http://torrents.thepiratebay.org/6176918/PwnageTool_4.2.dmg.6176918.TPB.torrent) (Torrent-Datei) und kopiere es in den Programme Ordner. Dann Rechts-Klick auf das Programm und dann auf "Zeige Paket-Inhalt" wie in diesem Screenshot.
[![paketinhalt](//picdump.thafaker.de/2011/03/paketinhalt-150x150.png)](http://picdump.thafaker.de/2011/03/paketinhalt.png)
3. **Schritt**: Gehe in den Ordner *Contents/Resources/FirmwareBundles/* und kopiere die Datei *iPhone3,1_4.3.1_8G4.bundle* dort rein
[![ressurces](//picdump.thafaker.de/2011/03/ressurces-150x150.png)](http://picdump.thafaker.de/2011/03/ressurces.png)

## Erstelle eine Custom Ramdisk fürs iOS 4.3.1 Custom Firmware

1. **Schritt**: Der Universal Ramdisk Fixer ist Bestandteil des PwnageTool bundle Pakets das wir oben bei Schritt 1 herunter geladen haben. Dieses Programm jetzt einfach installieren. Dieser Schritt ist wichtig weil der Ramdisk-Teil des aktuellen PwnageTool kaputt ist, deshalb muss er mit dem Fixer *gepatchet* werden.
[![ramdisk](//picdump.thafaker.de/2011/03/ramdisk-150x150.png)](http://picdump.thafaker.de/2011/03/ramdisk.png)

## Custom Firmware 4.3.1 basteln

1. **Schritt**: Die aktuellste Firmware [downloaden (archiviert)](http://web.archive.org/web/20110530073342/http://thafaker.de:80/iphone-firmware/) und auf den Desktop kopieren.
2. **Schritt**: Jetzt das PwnageTool im Experten-Modus starten.
[![expertenmodus](//picdump.thafaker.de/2011/03/expertenmodus-150x150.png)](http://picdump.thafaker.de/2011/03/expertenmodus.png)
3. **Schritt**: Die Firmware 4.3.1 auswählen
[![firmware](//picdump.thafaker.de/2011/03/firmware-150x150.png)](http://picdump.thafaker.de/2011/03/firmware.png)
4. **Schritt**: Nun klickt man einfach auf *Erstellen* und das PwnageTool baut die neue Custom Restore Datei die man später mit iTunes auf das iPhone 4 installieren wird.
[![cf_b](//picdump.thafaker.de/2011/03/cf_b-150x150.png)](http://picdump.thafaker.de/2011/03/cf_b.png)
Bei mir kam währen des *Building IPSW* die Aufforderung, ich sollte die neueste Ramdisk 1.72 downloaden und es öffnete sich eine [Website (archiviert)](http://web.archive.org/web/20110501101813/http://www.iphone-privacy.com/). Als ich das getan hatte, lief PwnageTool dann auch problemlos durch.
[![baut](//picdump.thafaker.de/2011/03/baut-150x150.png)](http://picdump.thafaker.de/2011/03/baut.png)
5. **Schritt**: Nun folgt man den Schritten vom PwnageTool um in den berühmten DFU-Modus zu gelangen, in diesem Modus kann man eine Firmware in das Gerät schieben, es in iTunes wieder her stellen:

1. Home -und Powerknopf gleichzeitig für 10 Sekunden drücken und gedrückt halt
2. Nun den Powerknopf los lassen und den Homebutton weitere 10 Sekunden drücken
3. Nun sollte das Gerät im DFU-Modus sein

## Custom Firmware mit iTunes aufs iPhone installieren

1. **Schritt**: iTunes meldet sogleich, dass es ein iPhone im "Wartungsmodus" entdeckt hat.
[![wartung](//picdump.thafaker.de/2011/03/wartung-150x150.png)](http://picdump.thafaker.de/2011/03/wartung.png)
2. **Schritt**: Ihr klickt nun auf *Wiederherstellen* und zwar mit der gedrückter Alt-Taste am Mac.
[![Bildschirmfoto 2011-03-28 um 17.10.52](//picdump.thafaker.de/2011/03/Bildschirmfoto-2011-03-28-um-17.10.52-150x150.png)](http://picdump.thafaker.de/2011/03/Bildschirmfoto-2011-03-28-um-17.10.52.png)
3. **Schritt**: Nun wählt ihr die durch das PwnageTool erstellte Firmware Datei aus, damit iTunes jene benutzt
[![Bildschirmfoto 2011-03-28 um 17.11.14](//picdump.thafaker.de/2011/03/Bildschirmfoto-2011-03-28-um-17.11.14-150x150.png)](http://picdump.thafaker.de/2011/03/Bildschirmfoto-2011-03-28-um-17.11.14.png)
4. **Schritt**: Und dann gehts los, wah? Jetzt klickt ihr auf "Wiederherstellen" und iTunes rattert los, wird die Firmware entpacken, wird das iPhone mehrmals neu starten, wird die Firmware ins iPhone 4 laden und zum Schluss, hoffentlich... haben wir ein jailbroken iPhone 4 oder befinden uns auf den Weg dort hin.
[![Bildschirmfoto 2011-03-28 um 17.11.20](//picdump.thafaker.de/2011/03/Bildschirmfoto-2011-03-28-um-17.11.20-150x150.png)](http://picdump.thafaker.de/2011/03/Bildschirmfoto-2011-03-28-um-17.11.20.png)
Dies dauert übrigens eine ganze Weil, bei mir so circa 15 Minuten.
5. Bei mir erschien währen der Wiederherstellung leider ein **Fehler 1601**, Wiederherstellung nicht möglich.
[![1601](//picdump.thafaker.de/2011/03/1601-150x150.png)](http://picdump.thafaker.de/2011/03/1601.png)
Später fand ich heraus, dass dies an einer `/etc/hosts` Datei liegt, in welcher folgende zwei Einträge fehlen:
`74.208.10.249 gs.apple.com
74.208.10.249 gs.apple.com`
Man öffnet das Terminal und gibt ein: `sudo nano /etc/hosts` und trägt diese fehlenden zeilen ein. Danach trat der Fehler bei mir nicht mehr auf.
[![done](//picdump.thafaker.de/2011/03/done-150x150.png)](http://picdump.thafaker.de/2011/03/done.png)
6. Übrigens startet das iPhone nicht neu, weil ja der untethered Jailbreak nicht klappt. Bei mir blieb das iPhone nach erfolgreicher Wiederherstellung einfach mit dem Apple-Zeichen stehen.

## Booting in Tethered Mode

1. **Schritt**: Jetzt kommt der eigentlich schwierige Teil, nun muss man das iPhone nämlich tethered booten, damit der Jailbreak auch tatsächlich eingeschleust und etabliert wird. Dies bedeutet, wir müssen die Befehle -welche sich sonst automatisch injizieren- per Hand in das iPhone bringen - das ist der Nachteil eines tethered Jailbreaks.
2. **Schritt**: Dazu benutzen wir das Programm-Paket *thethered boot*, welches man hier [downloaden](https://sites.google.com/site/0xjohnny/downloads/tetheredboot.zip) kann.
3. **Schritt**: Bevor wir aber zur tetheredboot.zip kommen, brauchen wir erst mal zwei Dateien aus unserer vorhin erstellten Custom Firmware. Die Dateien: *kernelcache.release.n90 *sowie *iBSS.n90ap.RELEASE.dfu*
4. **Schritt**: Wir machen uns eine Kopie von unserer 4.3.1 Custom Firmware die das PwnageTool erstellt hat und bennen diese von der Dateiendung IPSW in die Dateiendung ZIP um. Jetzt entpacken wir diese ZIP-Datei.
5. **Schritt**: In dem entpackten Ordner liegt direkt die Datei kernelcache.release.n90 und im Ordner *Firmware/dfu* liegt die andere Datei, iBEC.n90ap.RELEASE.dfu
[![iBEC](//picdump.thafaker.de/2011/03/iBEC-150x150.png)](http://picdump.thafaker.de/2011/03/iBEC.png)
6. **Schritt**: Jetzt erstellen wir uns einen neuen Ordner *tetheredboot* auf dem Desktop und kopieren die beiden Dateien dort hinein.
7. **Schritt**: Die restlichen Dateien aus der herunter geladenen ZIP-Datei *tetheredboot.zip* kopieren wir auch dort hinein. Das sieht dann so aus:
[![tethered](//picdump.thafaker.de/2011/03/tethered-150x150.png)](http://picdump.thafaker.de/2011/03/tethered.png)
8. **Schritt**: Schaltet euer iPhone aus und startet das Terminal, gebt dort folgenden Befehl ein:
sudo -s
Jetzt müsst ihr euer Passwort eingeben, dadurch werdet ihr Super User (Adminstrator).
9. **Schritt**: gebt im Terminal die beiden Zeichen cd ein und zieht dann den Ordner tetheredboot von eurem Desktop in das Terminalfenster: es sollte jetzt diese Zeile da stehen:
`bash-3.2# cd /Users/DeinName/Desktop/tetheredboot`
Jetzt drückt ihr Enter und nun befindet ihr Euch im Ordner tetheredboot auf eurem Desktop.
10. **Schritt**: Tippt bitte folgende Befehlsfolge in eurer Terminal-Fenster oder kopiert es:
`./tetheredboot -i iBSS.n90ap.RELEASE.dfu -k kernelcache.release.n90`
Danach drückt ihr einfach ENTER und es sollte loslegen
11. **Schritt**: Jetzt zieht ihr nacheinander die Dateien in das Terminal und schreibt nach der ersten Datei -i und nach der zweiten Datei -k dahinter. Das ganze sollte so aussehen:[![befehlskette](//picdump.thafaker.de/2011/03/befehlskette-150x150.png)](http://picdump.thafaker.de/2011/03/befehlskette.png)
Dann drückt ihr Enter. Bei mir stand im Terminal, ich muss das iPhone in den DFU-Mode bringen, also wie oben beschrieben, tat ich das: nun ratterte allerlei Befehlszeilen-Voodoo durch die Console,
[![vodoo](//picdump.thafaker.de/2011/03/vodoo-150x150.png)](http://picdump.thafaker.de/2011/03/vodoo.png)
dann war das fertig, ich zog das iPhone vom Kabel ab und plötzlich konnte ich "Slide to Unlock" machen und mein iPhone war mit Cydia neu aufgesetzt. Es blieb übrigens mit weißem Bildschirm relativ lange stehen, ich dachte schon es hätte nicht geklappt, aber dann war der Homescreen da.
12. Das ganze war schon ziemlich holprig und ich glaube, an einigen Punkte hat es gehangen. Aber ich bin noch mal nach meiner Anleitung vor gegangen und es funktioniert.
[![jailbroken](//picdump.thafaker.de/2011/03/jailbroken-386x580.png)](http://picdump.thafaker.de/2011/03/jailbroken.png)
13. Ich habe danach sofort CYDIA (Cydia meldet auch gleich 2 essentielle Updates) gestartet um mir nach diesem [Tutorial hier gecrackte IPAs](__GHOST_URL__/wie-installiere-ich-ipa-dateien-auf-meinem-ipodiphone/) aufspielen zu können.
14. Dann habe ich mit iTunes mein altes Backup eingespeilt *et voila*, mein iPhone 4 ist nun mit iOS 4.3.1 jailbroken :-) (Denkt dran, nach jedem Neustart muss man das iPhone wieder tetheren)
[![backup](//picdump.thafaker.de/2011/03/backup-150x150.png)](http://picdump.thafaker.de/2011/03/backup.png)

**Bekannte Probleme**:

- Cydia bringt ein *Hash mismatch* und kann sich nicht aktualisieren, beim zweiten Versuch lief es bei mir, vielleicht lief der Download schief, einfach noch mal versuchen.
- Das iPhone 4 (ohne Simlock/Netlock) findet plötzlich kein Netz mehr, als wenn es einen Simlock hätte - noch keine Lösung.

([via](http://www.redmondpie.com/jailbreak-ios-4.3.1-iphone-4-with-pwnagetool-4.3.1-bundle-how-to-guide/))
