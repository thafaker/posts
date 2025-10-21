---
title: "macOS High Sierra: bootbaren USB-Stick erstellen"
slug: macos-high-sierra-bootbaren-usb-stick-erstellen
date_published: 2017-10-02T09:29:02.000Z
date_updated: 2018-08-22T09:37:42.000Z
tags: how to, howto, anleitung, wie geht, high sierra, bootfähig, usb stik, mac os high sierra, clean install
---

Nachdem Apple vor kurzen macOS 10.13 High Sierra vorgestellt hat und man es aus dem Mac App Store kostenlos herunterladen kann, fragen sich (so wie ich) sicher einige, wie man daraus einen bootfähigen USB-Stick erstellen kann, um bei Bedarf eine saubere Neuinstallation durchführen zu können. Dies macht manchmal Sinn, denn eine Wiederherstellung ist nicht das gleiche wie ein echter *Clean Install*! In diesem Artikel beschreiben wir kurz Schritt für Schritt, wie ihr vorgehen müsst. 

Zunächst benötigen wir natürlich High Sierra, was im Mac App Store geladen werden muss. Das ist der ganz normale Installer der dann im Programme-Ordner liegt, aus welchem der USB-Stick erstellt wird. Was braucht man noch? Einen USB-Stick mit 8 Gb oder mehr Speicherkapazität. Dieser wird vollständig gelöscht, also sichert die Daten auf dem Stick. Dann benötigt man zu guter letzt auch noch einen kompatiblen Mac. Generell geht jeder Mac, der auch schon 10.12 Sierra installieren konnte. Hier eine Liste:

### Bootfähigen USB-Stick erstellen: das wird benötigt

- Macbook ab Ende 2009
- Macbook Pro ab Mitte 2010
- Macbook Air ab Ende 2010
- Mac mini ab Mitte 2010
- iMac ab Ende 2009
- Mac Pro ab 2010 oder neuer
- macOS High Sierra 10.13 aus dem Mac App Store herunterladen
- kompatibler USB-Stick mit 8 GByte Kapazität (wird gelöscht)

### Bootfähigen USB-Stick erstellen: Schritt für Schritt

Los gehts, Schritt für Schritt voran, meine Damen und Herren.

1. High Sierra [herunter laden](https://itunes.apple.com/de/app/macos-high-sierra/id1246284741?mt=12) (4.80 GB)
2. Nach dem Download das Setup-Programm, das automatisch nach dem Herunterladen startet, abbrechen!
3. USB Stick anschließen
4. Festplattendienstprogramm starten und Stick formatieren.
![Bildschirmfoto-2017-10-02-um-11.09.52](__GHOST_URL__/content/images/2017/10/Bildschirmfoto-2017-10-02-um-11.09.52.png)
5. Wenn der Stick formatiert ist, startet ihr die Terminal.app, denn die restlichen Befehle geben wir in der Console ein.
6. **Terminal** starten: "Programme --> Dienstprogramme --> Terminal.app"
7. Copy and pasted den folgenden Befehl:
`sudo /Applications/Install\ macOS\ High\ Sierra.app/Contents/Resources/createinstallmedia --volume /Volumes/UNTITLED && say Boot Installer Complete`
8. Für /Volumes/**UNTITLED** tragt ihr den Namen eures USB Sticks ein. Bei mir heißt er: **highsierrainstaller**. Der Code lautet bei mir also folgendermaßen:
`sudo /Applications/Install\ macOS\ High\ Sierra.app/Contents/Resources/createinstallmedia --volume /Volumes/highsierrainstaller && say Boot Installer Complete`
9. Wenn ihr das ins Terminal eingetippt habt, drückt ihr bitte ENTER.
![Bildschirmfoto-2017-10-02-um-11.17.39](__GHOST_URL__/content/images/2017/10/Bildschirmfoto-2017-10-02-um-11.17.39.png)
10. Der Prozess startet und der Stick wird abermals formatiert. Genau genommen kann man sich den Schritt oben im Festplattendienstprogramm auch sparen.
11. Der Installer bereitet den Stick vor, kopiert die Daten, macht den Stick bootfähig und das ganze braucht seine Zeit. Ich habe hier einen alten 16 GB USB 2.0 Stick genommen... vielleicht habt ihr ja schon USB 3
12. Zum Schluss steht ein `done` in eurem Terminal.
13. Der Stick ist fertig. Jetzt müsst ihr den Installer starten. Dazu macht ihr einen Neustart und haltet nach dem Gong die Taste "OPTION” (ALT) gedrückt. Es erscheint folgendes Menü:
![small](__GHOST_URL__/content/images/2017/10/smalle.png)
14. Hier wählt ihr den Stick aus und drückt ENTER.
15. Der Installer startet.
16. Wenn ihr eure Platte formatieren möchtet, startet das *Festplattendienstprogramm* und löscht sie.
17. Dann gehts los…
18. FERTIG.

Ich habe diesen Weg genutzt, um mein **Macbook Pro 13" touchbar** neu aufzusetzen.
