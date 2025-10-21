---
title: [SICHERHEIT] Ransomware auf dem Mac erkennen (UPDATE)
slug: sicherheit-ransomware-auf-dem-mac-erkennen
date_published: 2016-04-24T06:00:43.000Z
date_updated: 2018-08-22T09:39:28.000Z
tags: sicherheit, security, osx, apple, mac, software, free, download, RansomeWhere?, ransomware, update
---

Da ja auch die OS X-Gemeinde nicht vor den letzten großen Überschwemmungen an Erpressungstrojanern [gefeit (archiviert)](http://web.archive.org/web/20160403223755/http://thafaker.de/tag/keranger/) war, hat die Softwareschmiede *Objective See* (nette Anspielung auf die Programmiersprache Objective-C von Apple) nun eine kleine Software entwickelt, die auf dem Mac verdächtige Prozesse erkennt und entfernt, wenn diese aktiv sind. 

Die **RansomWhere?** genannte Anwendung beobachtet, ob verdächtige Systemprozesse Dateien verschlüsseln wollen und informiert den Nutzer über diesen Vorgang. Dieser kann den Prozess dann beenden oder – falls es sich um eine gewollte Verschlüsselung von Dateien durch ein legitimes Programm handelt – auch zulassen.

![](__GHOST_URL__/content/images/2016/04/alert.png)

Die Software erkennt allerdings keine bereits befindlichen Dinge in diese Richtung, sondern überwacht im Hintergrund und schlägt Alarm, sobald sich etwas verdächtiges tut. [...] RansomWhere? prüfe nur Verschlüsselungsvorgänge in den Verzeichnissen des Nutzers, schränkt Entwickler Wardle ein. Zudem kann es ein Erpressungstrojaner schaffen, mehrere Dateien zu verschlüsseln, bevor das Programm den Warnungsdialog anzeigt. Und natürlich könne eine Ransomware gezielt versuchen, die Prüfroutinen des Tools zu umgehen. [...]

Aber an sich eine gute Idee die man mit steigender Bedrohung auch bei OS X eigentlich im Hintergrund laufen lassen sollte.

### Download

- [Website des Herstellers](https://objective-see.com/products/ransomwhere.html)
- *Aktuelle*[**Version 1.1.0** für OS X ab 10.10](https://bitbucket.org/objective-see/deploy/downloads/RansomWhere_1.1.0.zip)
- *alte*[**Version 1.0** für OS X 10.10](https://bitbucket.org/objective-see/deploy/downloads/RansomWhere_1.0.0.zip)

([via](http://www.heise.de/mac-and-i/meldung/Tool-RansomWhere-soll-Mac-Nutzer-vor-Erpressungstrojanern-schuetzen-3180128.html))
