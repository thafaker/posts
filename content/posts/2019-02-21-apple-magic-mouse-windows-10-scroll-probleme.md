---
title: [UPDATE] Apple Magic Mouse - Windows 10 Scroll Probleme
slug: apple-magic-mouse-windows-10-scroll-probleme
date_published: 2019-02-21T18:01:00.000Z
date_updated: 2024-01-22T05:43:01.000Z
tags: anleitung, howto, how to, bigmac, windows 10, magicmouse, updated
---

**Ihr** habt euch auf eurem *Mac Pro* (oder iMac oder Macbook) Windows 10 installiert und alles ist toll. Dann aber stellt ihr fest, dass die *Apple Magic Mouse* nicht richtig funktioniert. 

Ihr habt sie über Bluetooth gepaired. [[1]](#fn1) Zwar könnt ihr klicken und sie benutzen, aber die *Scroll-Funktion* liegt brach. Das nervt, gerade weil man heutzutage praktisch überall scrollen muss. Aber zum Glück gibt es einfache Abhilfe: [[2]](#fn2)

1. Ladet euch das [Bootcamp Treiber Paket](https://support.apple.com/kb/dl1720?locale=en_US) von Apple herunter. In meinem Falle war es das hier `BootCamp5.1.5621.zip`.
2. Entpackt die ZIP-Datei.
3. Öffnet das entpackte Archiv und wechselt in den Pfad:`\BootCamp5.1.5621\BootCamp\Drivers\Apple` und installiert folgende Datei: `AppleWirelessMouse64.exe`
4. Deaktiviert die Maus am Schalter (Magic Mouse 1), aktiviert sie wieder und schon sollte die Scrollfunktion zur Verfügung stehen. Sinnvoll ist es hierzu, noch eine alternative Maus angeschlossen zu haben, um den Rechner Bedienbar zu halten.

![Windows BootCamp Treiber Magic Mouse](__GHOST_URL__/assets/2019/02/treiber.jpg)

### For our english speaking audience

1. Download the latest boot camp support sw
2. The latest I can find as follow: [https://support.apple.com/kb/DL1837?viewlocale=en_US&locale=en_US](https://support.apple.com/kb/DL1837?viewlocale=en_US&amp;locale=en_US)
3. Unzip the file...bootcamp5.1.5769.zip
4. locate and run AppleWirelessMouse64.exe under the following folder to run the driver installation...
5. `bootcamp5.1.5769.zip\BootCamp\Drivers\Apple`
6. Done. You should have your scrolling working for the Apple magic mouse.

[**Update**] Christian schrieb in einem Kommentar folgendes:

> In meinem Fall war die Lösung: AppleWindowsSupport$WinPEDriver$\AppleWirelessMouse\AppleWirelessMouse.inf
> 
> Rechtsklick, Installieren, Maus Aus- und Einschalten

Das wars auch schon wieder :-)

*Bis bald.*

---

**Artikelbild**: Photo by [Michał Kubalczyk](https://unsplash.com/photos/zjn17WVQAZ4?utm_source=unsplash&amp;utm_medium=referral&amp;utm_content=creditCopyText) on Unsplash.

---

1. 
Der Code lautet gemeinhin *0-0-0-0* oder *1-2-3-4*. [↩︎](#fnref1)

2. 
Out-Of-The-Box wäre natürlich noch schöner, aber oft kann man einfach nicht alles haben. [↩︎](#fnref2)
