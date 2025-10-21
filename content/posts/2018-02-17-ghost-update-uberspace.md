---
title: Ghost Update Uberspace - Ghost 1.X auf Ghost 2.0 aktualisieren
slug: ghost-update-uberspace
date_published: 2018-02-17T15:19:53.000Z
date_updated: 2024-02-21T18:11:41.000Z
tags: ghost, anleitung, how to, howto, ghost 1.0, uberspace, fix.it
excerpt: anleitung ghost 1.0 und höher update uberspace in nur 6 schritten.
---

[**UPDATE**] Ghost läuft in der aktuellen Version 5 nicht mehr auf dem *Uberspace*. Ich habe eine Anleitung verfasst, wie man Ghost kostenlos auf einem Oracle Server installieren kann.

[https://thahipster.de/wie-man-sich-kostenlos-zwei-virtuelle-server-instanzen-mit-ubuntu-22-04-klickt-und-betreibt/](__GHOST_URL__/wie-man-sich-kostenlos-zwei-virtuelle-server-instanzen-mit-ubuntu-22-04-klickt-und-betreibt/)

In dieser Anleitung möchte ich noch einmal ganz kurz erläutern, wie man sein Ghost 1.X Weblog ohne Update-Script per Hand ganz schnell aktualisieren kann. Getestet habe ich dieses Vorgehen mit Ghost 1.11. auf Ghost 1.21.3; Quick'n'Dirty Update eines installierten Ghost auf nem Uberspace. Wir gehen davon aus, dass Ghost strikt nach der [Anleitung](https://wiki.uberspace.de/cool:ghost) aus dem Uberspace-Wiki installiert wurde! 

[**UPDATE** 22.08.2018] Diese Anleitung eignet sich ebenfalls, sein bereits laufendes Ghost 1.X auf das neue [Ghost 2.0](__GHOST_URL__/ghost-2-0-ist-da/) zu aktualisieren.

![Code on a computer](https://images.unsplash.com/photo-1504164996022-09080787b6b3?ixlib=rb-0.3.5&amp;q=80&amp;fm=jpg&amp;crop=entropy&amp;cs=tinysrgb&amp;w=1080&amp;fit=max&amp;ixid=eyJhcHBfaWQiOjExNzczfQ&amp;s=0c69f6a40c3ac6916798876ae67a8b8d)
Photo by [Markus Spiske](https://unsplash.com/@markusspiske?utm_source=ghost&amp;utm_medium=referral&amp;utm_campaign=api-credit) / [Unsplash](https://unsplash.com/?utm_source=ghost&amp;utm_medium=referral&amp;utm_campaign=api-credit)

Ghost hat eigentlich eine eigene Update-Funktion in der Ghost-CLI[[1]](#fn1), die aber auf dem Uberspace nicht funktionert. Daher rührts, das händische Vorgehen.

### How To Update Ghost Uberspace < 1.0

1. 
Per SSH mit dem Uberspace verbinden und ein Update eures Ghost-Verzeichnisses durchführen. (Ghost ist installiert im Home-Verzeichnis im Ordner `ghost`).
`cd ~`
`cp -r ghost ghost-backup-$(date +%F@%T)`

2. 
… in das Ghost verzeichnis wechseln:
`cd ~/ghost`

3. 
Das neueste Ghost herunter laden und entpacken (zwei Zeilen Code, nacheinander ausführen):
`curl -L [https://ghost.org/zip/ghost-latest.zip](https://ghost.org/zip/ghost-latest.zip) -o ghost-latest.zip`
`unzip ghost-latest.zip`

4. 
Jetzt die ganzen neuen Abhängigkeiten aktualisieren…:
`npm install --python="/usr/local/bin/python2.7" --production`

5. 
Wichtig, die Datenbank migrieren, hier gab es bei mir oft Probleme, allerdings ist meine Datenbank auch heftig groß… Artikel seit 2005.
`NODE_ENV=production knex-migrator migrate`

6. 
Wenn das ohne fehler durchgelaufen ist, am Ende Ghost neu starten:
`svc -du ~/service/ghost`

Wahlweise kann man mit einem freundlichen
`tail -f ~/service/ghost/log/main/current`

zuschauen, was geht und ob alles funktioniert. Hier sollten keine Errors auftauchen.

**PS**: Es gibt ein vollautomatisches [Update-Script (archiviert)](http://web.archive.org/web/20200619190548/https://www.peleke.de/ghost-1-0-aktualisierung-bei-uberspace/) für den Uberspace, welches diese Schritte automatisiert.

---

1. 
Command Line Interface, [hier](https://docs.ghost.org/docs/ghost-cli) stehen weitere Informationen. [↩︎](#fnref1)
