---
title: Runtastic Road Bike - alle Aktivitäten exportieren
slug: runtastic-road-bike-alle-aktivitaten-exportieren
date_published: 2017-08-30T16:06:16.000Z
date_updated: 2018-08-22T09:37:42.000Z
tags: howto, how to, anleitung, export, terminal, runtastic, activities
---

Ich mag **Runtastic** nicht mehr. *Wohl*, damals waren sie die ersten mit einer guten GPS-App zum Radfahren für das iPhone und ich nutzte sie lange. Aber Runtastic hat beispielsweise kein Interesse daran, die Apple Watch zu unterstützen. Hier vor allem den eingebauten GPS-Sensor der Series 2, mit dem es möglich ist, ohne Telefon zu fahren, weil die Uhr alles alleine Kann. Erst recht, weil die Series 2 auch MP3 Dateien direkt in der Uhr speichern kann und somit via Bluetooth Kopfhörer auch als MP3-Player fungiert. Überhaupt kein Grund mehr für ein Telefon. 

In dieser Anleitung möchte ich nach einigem Suchen einen sehr einfachen Weg aufzeigen, wie man alle seine Runtastic Roadbike Aktivitäten auf ein mal herunter laden… und beispielsweise in Strava wieder hoch laden kann. Das Format der Wahl zum Export ist hierbei *.tcx.

![17661911_441842339495012_6801314977912193024_n](__GHOST_URL__/content/images/2017/08/17661911_441842339495012_6801314977912193024_n.jpg)
thafaker.de Rose Bike Rennrad

Wir kommen allerdings nicht um die Kommandozeile herum, denn Runtastic hat auf seiner Website eine Captcha-Schutzfunktion eingebaut, die es den Browser-Scripten unmöglich macht, [mehr als 5 Aktivitäten (archiviert)](http://web.archive.org/web/20201111185223/https://gist.github.com/christianewald/0009d3ce1a372a11ae82) auf einmal herunter zu laden. Man müsste sich also nach 5 aktivitäten neu einloggen und erneut starten. Hat man so wie ich 5 Jahre zu exportieren, brächte man einen Praktikant_Innen[[1]](#fn1) dazu.

### HowTo Download Runtastic Roadbike Activities

Zunächst benötigt ihr [folgendes Script](https://github.com/Metalnem/runtastic) für die Kommandozeile, welches ihr hier herunter laden könnt.

1. Download Terminal-Script: [Windows](https://github.com/Metalnem/runtastic/releases/download/v2.1.1/runtastic-win64-2.1.1.zip), [Linux](https://github.com/Metalnem/runtastic/releases/download/v2.1.1/runtastic-linux64-2.1.1.zip), [Mac OS X](https://github.com/Metalnem/runtastic/releases/download/v2.1.1/runtastic-darwin64-2.1.1.zip)
2. Entpackt die Datei durch Doppelklick
3. Öffnet das Terminal unter OS X
4. Tippt folgendes dort ein `cd ~/Downloads/`
5. Jetzt befindet ihr euch im Download-Ordner, dort wo ihr das Script entpackt habt. Das Script heißt **runtastic**
6. Tippt folgendes ein:
`./runtastic -email user@example.org -password secret123 -format tcx`

Wobei ihr für *user@example* natürlich euren Login bei Runtastic eingeben müsst, und bei *secret123* - ganz klar, euer Password so wie ihr es auch auf der Website von Runtastic tut.
7. Den Rest könnt ihr so lassen und drückt Enter. Das Script startet. Es dauert eine Weile.
8. Das Script tut nun folgendes: Es loggt sich mit den Euren Daten in euren Account bei Runtastic ein, lädt sämtliche Aktivitäten als ZIP Datei herunter und wenn ihr die herunter geladene Datei entpackt, *et voila*, habt ihr einen Ordner voll mit .tcx Dateien. Das sind Eure Aktivitäten.
9. Diese Dateien könnt ihr nun bei Strava wieder hoch laden, wenn ihr das möchtet. Wenn nicht, so habt ihr zumindest in einem gut austauschbaren Format eure Runtastic-Dateien gebackupt. :-)
10. Andere Dienste als Strava nutzen dieses Format ebenfalls, sodass ihr die .tcx Dateien auch bei einem ganz anderen Dienst hoch laden könnt. Hauptsache, ihr habt sie erst mal aus dem bösen Runtastic heraus geladen und sie gehören euch. Es sind ja auch eure Daten, nicht deren.
11. Bei Strava legt man sich einen kostenlosen Account an und kann direkt mit dem Upload beginnen. Ich bin sozusagen gewechselt.

*Thats all for now, bitte sehr.*

---

1. 
Das ist natürlich nur ein dummer Spruch, wir bei thafaker.de hassen es, wenn Praktikten für dämliche Aufgaben misbraucht werden. [↩︎](#fnref1)
