---
title: [HowTo] redsn0w 0.9.6 Jailbreak jetzt mit One-Klick Tethered Boot
slug: howto-redsn0w-0-9-6-jailbreak-jetzt-mit-one-klick-tethered-boot
date_published: 2011-01-05T09:25:01.000Z
date_updated: 2018-08-22T09:38:43.000Z
---

In einem Update zur bestehenden Version redsn0w 0.9.6, mit der neuere  Geräte bislang nur den *tethered Jailbreak* erhalten, versucht das  DevTeam, die lange Wartezeit bis zum echten *untethered Jailbreak* mit  einer neuen Funktion zu verkürzen: Über Kommandozeilen-Argumente via Shell kann  man, wenn man z.B. nur normal tethered ((**tethered**: bei jedem Neustart des iDevices neu durchzuführen, es bootet nicht von allein)) booten möchte, die Prozedur mit  der Auswahl der aktuellen IPSW-Datei + gewünschter Aktion überspringen  und direkt die Aktion ausführen.

An einem Mac sieht das ganze zB. für einen iPod Touch 4G mit iOS 4.2.1 so aus:
`open ~/Desktop/redsn0w.app —args -j -i ~/Desktop/iPod4,1_4.2.1_8C148_Restore.ipsw`

(Annahme: Sowohl redsn0w als auch die IPSW-Datei liegen auf dem Desktop)

Für ein iPhone (oder das iPad...) muss man den Namen der Datei entsprechend anpassen.

Gleich vier Argumente hat das DevTeam angelegt:

> -j to ask redsn0w to “Just boot now tethered for now”
> -i  to specify your reference IPSW
> -o for old-bootrom iPod touch 2G and iPhone 3GS
> -b  to specify your own boot logo png
