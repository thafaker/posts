---
title: Temperatur von macOS / OSX übers Terminal auslesen
slug: temperatur-von-macos-osx-ubers-terminal-auslesen
date_published: 2018-12-18T22:20:00.000Z
date_updated: 2019-04-06T11:34:16.000Z
tags: macos, apple, macpro, terminal, homebrew
---

**Neulich** wollte ich die Temperatur-Daten meines iMacs auslesen, da dieser bedingt durch seinen fetten **Core i7** (2.93 GHz) ja doch ziemlich viel Power hat und dadurch Wärme entwickelt. Da ich mir nicht sicher bin ob mein iMac nicht auf ein Temperaturproblem hat, interessierten mich diese Werte. Jedoch wollte ich dafür kein kommerzielles Produkt erwerben, dafür interessiert mich die Temperatur dann doch nicht dauerhaft genug - aber zum Glück gibt es hier Abhilfe. 

Da ich ohnehin ein Freund des Terminals bin und auf meinem *macOS* auch immer ein *Homebrew*[[1]](#fn1) ([Link](https://brew.sh)) läuft und ich allerlei *Terminal-Krimskrams* (TM) durchführe, ist mir eine Lösung für die Konsole gerade recht. `iStats` ist hier das Zauberwort.

    Jans-iMac:~ apfelhammer$ sudo gem install iStats
    

Nach Eingabe des root-Kennworts folgen ein paar Installationsmeldungen:

    Fetching: sparkr-0.4.1.gem (100%)
    Successfully installed sparkr-0.4.1
    Fetching: parseconfig-1.0.8.gem (100%)
    Successfully installed parseconfig-1.0.8
    Fetching: iStats-1.6.1.gem (100%)
    Building native extensions.  This could take a while...
    Successfully installed iStats-1.6.1
    Parsing documentation for sparkr-0.4.1
    Installing ri documentation for sparkr-0.4.1
    Parsing documentation for parseconfig-1.0.8
    Installing ri documentation for parseconfig-1.0.8
    Parsing documentation for iStats-1.6.1
    Installing ri documentation for iStats-1.6.1
    Done installing documentation for sparkr, parseconfig, iStats after 0 seconds
    3 gems installed
    

Und es wurden 3 gems [[2]](#fn2) installiert. Ein beherztes `iStats` brachte bei mir noch nicht die perfekten Ergebnisse, aber immerhin wurde überhaupt schon etwas dargestellt.

    Jans-iMac:~ apfelhammer$ iStats
    --- CPU Stats ---
    CPU temp:               -127.0°C    ▁▂▃▅▆▇
    
    --- Fan Stats ---
    Total fans in system:   3           
    Fan 0 speed:            1001 RPM    ▁▂▃▅▆▇
    Fan 1 speed:            1116 RPM    ▁▂▃▅▆▇
    Fan 2 speed:            940 RPM     ▁▂▃▅▆▇
    
    --- Battery Stats ---
    No battery on system
    
    For more stats run `istats extra` and follow the instructions.
    

Wer weitere Werte auslesen möchte, muss zunächst das eigene System mit `iStats scan` einlesen. Danach kann man einzelne Werte mit `iStats enable $key` aktivieren oder gleich alle mit `iStats enable all`. Alle weiteren Optionen finden sich mit `iStats -h`.

![iStat nach dem Befehl iStat scan](__GHOST_URL__/assets/2018/12/istat.png)

Mein iMac lieferte hier jedoch dutzende Ergebnisse und so konnte ich nicht einfach alle Werte bestätigen, sondern wählte die für mich sinnigsten aus.

*Das wars, bis bald*.

---

**Artikelbild**: (C) Das ist mein eigener Screenshot.

---

1. 
Homebrew ist eine freie/quelloffene Paketverwaltung, die die Installation von Software auf dem Betriebssystem macOS vereinfacht. Die Paketverwaltung wurde ursprünglich von Max Howell geschrieben. Sie erlangte starke Verbreitung in der Ruby-on-Rails-Szene und wurde für ihre Erweiterbarkeit gelobt. [↩︎](#fnref1)

2. 
Gems ist das offizielle Paketsystem für die Programmiersprache Ruby. Es stellt ein Paketformat, ein Werkzeug zur Verwaltung von Paketen und ein Repositorium für deren Verteilung zur Verfügung. Mit ihm hat der Anwender die Möglichkeit, mehrere (zum Beispiel ältere oder jüngere) Versionen eines Programmes, Programmteiles oder einer Bibliothek gesteuert nach Bedarf einzurichten, zu verwalten oder auch wieder zu entfernen. [↩︎](#fnref2)
