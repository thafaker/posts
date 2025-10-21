---
title: "macOS: in ZIP Archive blicken"
slug: macos-in-zip-archive-blicken
date_published: 2019-06-20T18:33:43.000Z
date_updated: 2019-06-20T18:34:45.000Z
tags: zip, quicklook, finder, macos, how to, howto, anleitung
---

Ja ja, dieser Titel lässt ebenfalls tief blicken :-) Soll er aber gar nicht. Allerdings finde ich hin und wieder mal auf irgendeiner meiner Festplatten Dateien mit dem kryptischen Titel "Archiv.zip" oder "Sicherung-2018.zip" und weiß an dieser Stelle oftmals nicht, was da drin ist. Dann sind diese Dateien aber oft auch gleich 10 GB groß und ich habe eigentlich wenig Lust, diese zu entpacken - nur um festzustellen, dass es *Tand*[[1]](#fn1) ist.

Grund genug also, sich hier einer Alternative zu bedienen. Unter macOS respektive OSX gibt es verschiedene Möglichkeiten, sich den Inhalt einer ZIP-Datei anzeigen zu lassen. Die einfachste Variante ist über das Terminal.

### ZIP Archive via Terminal anzeigen

Öffnet das Terminal und gebt folgende Befehl ein:

`zipinfo archivename.zip`

Der Befehl listet euch dann ungefähr folgendes auf:

    $ zipinfo archive.zip
    Archive: archive.zip 1743 bytes 5 files
    -rw-r--r-- 2.1 unx 4068 bX defN 11-May-13 14:25 magicsample.conf
    -rw-r--r-- 2.1 unx 204 bX defN 16-May-13 09:38 magicfile
    -rw-r--r-- 2.1 unx 132 bX defN 21-May-13 12:44 testingsomething.txt
    5 files, 4486 bytes uncompressed, 991 bytes compressed: 77.9%
    

Das geht ganz gut, man tippt zipinfo ins Terminal und zieht die gewünsche Datei ins Terminal, klickt ENTER und schon weiß man, was drin steckt. Aber so easy wie unter Windows, mit WinRAR etc., ist das nicht.

### ZIP Archiv Integration in Finder via Quicklook

Sinn macht es, direkt im Finder einen Blick in ZIP-Files werfen zu können. Allgemein praktisch ist Quicklook, ein Feature des Finder was es erlaubt, gewisse Dateien per Leertaste anzuzeigen. Eine schnelle Vorschau der Datei, sozusagen. Bei MP3s kann man kurz hinein hören, bei Bildern wird dieses angezeigt, genau so bei Websites wenn man eine URL per Leertaste aufruft… und hier wäre es gut, wenn Quicklook auch gleich in ZIP-Files blicken könnte.

1. Ladet euch [BetterZip](http://macitbetter.com/BetterZip-Quick-Look-Generator/) herunter
2. Entpackt das ZIP-Archive, HAHA :-)
3. Schiebt die App in euren Applications-Folder und startet sie, danach könnt ihr sie direkt wieder beenden.
4. Fortan habt ihr das ZIP-Plugin für Quicklock aktiviert.

![quicklook_betterzip](__GHOST_URL__/content/images/2019/06/quicklook_betterzip.png)

---

1. 
Tand ist eine altertümliche Bezeichnung für ein hübsches, nutzloses Ding, das keinen Wert hat. [↩︎](#fnref1)
