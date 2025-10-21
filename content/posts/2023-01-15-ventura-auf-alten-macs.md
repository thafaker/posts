---
title: Ventura auf MacPro 2013
slug: ventura-auf-alten-macs
date_published: 2023-01-15T11:58:13.000Z
date_updated: 2023-01-15T14:44:43.000Z
tags: trashcan, macos ventura, OpenCore, legacy patcher
---

Hallo Freunde betagter Macs, [macOS 13 Ventura](https://www.apple.com/de/macos/ventura/) gibt es nun einige Zeit, jedoch ließ Apple mit diesem Release mal wieder einige schöne alte Macs außen vor. Nicht zuletzt den (in meinen Augen absolut) großartigen [Mac Pro 2013](__GHOST_URL__/tag/trashcan/), liebevoll auch *TrashCan* genannt.

Immer gab es bisher findige Hacker, die sich damit nicht abfinden wollten und an einer Lösung arbeiten, um die neue Betriebssystem-Software auch auf älteren Macs laufen zu lassen. Und so ist es auch diesmal. 
Das großartige Open Core, wir erinnern uns daran, dass wir es auf dem [Mac Pro 5,1 einsetzten](__GHOST_URL__/macos-10-15-catalina-auf-macpro5-1/), um nicht mehr unterstützte Betriebssysteme (Mac OS 10.15) lauffähig zu machen, ist noch immer das Mittel der Wahl. Jedoch ist der Support für den 2013er Mac Pro (noch) nicht vollständig, was aufgrund der speziellen Hardware und dem Weglassen von wichtigen Treibern seitens Apples nicht verwunderlich ist. Mit dem aktuellen Release von **OpenCore Legacy Patcher 0.5.X** gelingt eine Clean Install auf einem Mac Pro 2013, jedoch gilt es folgende Umstände zu beachten:

- Power Support, throttling der CPUs klappt nicht
- GPU Encode/Decode (Legacy GCN support for Macs) ([hier](https://github.com/dortania/OpenCore-Legacy-Patcher/issues/1008))

Das sind grundlegende Features, ohne die ein MacPro 2013 nicht mehr so agiert, wie er das sonst tut: leise und effizient seine Arbeit verrichten. Bis diese Probleme nicht gelöst sind, rate ich für Arbeitsmaschinen von einem Upgrade ab, wenn man jedoch gern spielt und nicht darauf angewiesen ist, dann kann man das gern machen: es wird sehr wahrscheinlich keinen Schaden geben.

### Ressourcen

- [Open Core Legacy Patcher Guide](https://dortania.github.io/OpenCore-Legacy-Patcher/)
- [Supported Models](https://dortania.github.io/OpenCore-Legacy-Patcher/MODELS.html)
