---
title: Apple wechselt zu ARM
slug: apple-wechselt-zu-arm
date_published: 2020-06-24T00:14:00.000Z
date_updated: 2020-06-24T11:34:29.000Z
tags: apple, arm, wwdc 2020
excerpt: Mich interessiert hier vor allem eins, nämlich ob x86 und ARM parallel den PC-Markt nach vorne bringen können oder ob die Fragmentierung, die jetzt durch die Aufspaltung der Plattformen beginnt, das Gegenteil bewirkt. Dies ist die Frage, welche in den nächsten Jahre beantworten werden wird.
---

Wir hatten neulich noch in [einem Artikel](__GHOST_URL__/die-krasse-sache-mit-den-arms/), inspiriert von einem ARM-Notebook mit Windows eines Drittherstellers, gemunkelt, wann Apple denn endlich zu ARM-Prozessoren wechseln würde, weil sich die Zeit reif dafür anfühlt und mit Intel kein Blumentopf mehr zu gewinnen sei. Und just ist es passiert. In der gestrigen Keynote der 2020er [WWDC](https://developer.apple.com/wwdc20/) hat Apple zum Schluss genau diesen historischen Schritt vollzogen und den Wechsel von Intel zu Arm verkündet. Und eine Gänsehaut zog über meine ARMe ;-) 

> Cupertino nennt es **Apple Silicon**.

Denn mit *Rosetta 2*, *Universal Binaries* und einer flotten Übergangsphase fühlt sich das alles wie ein großes **Deja-Vu** an, denn das haben wir damals alles schon beim Wechsels von IBMs PowerPC hin zu Intels x86 erlebt. Aber genau deshalb ist Apple auch erprobt und erfahren und weiß genau, welche Stellschrauben wichtig sind um einen schnellen Wechsel zu vollführen. Eigene Anwendungen hat Apple intern längst von x86 auf ARM portiert, so läuft Final Cut Pro mit 4K-Playback von drei Streams flüssig auf Apple Silicon. Drittanwender-Anwendungen wie Adobes Lightroom und Photoshop oder Microsofts Office 365 sind ebenfalls schon angepasst. Entwickler können mit Xcode 12 und Universal 2 passende Binaries erzeugen, womit die App auf Apple Silicon und Intel x86 läuft.
![Adobes CC Suite auf Apple Silicon, hier Lightroom. (Bild: Apple)](__GHOST_URL__/content/images/2020/06/Apple-Silicon-08.png)Adobes CC Suite auf Apple Silicon, hier Lightroom. (Bild: Apple)
[…] Für Apple bedeutet der Wechsel von x86 zu ARM die volle vertikale Integration: Von der Hardware über die Firmware bis hin zum Betriebssystem samt Apps und Services kommt alles aus einer Hand. Das macht es einfacher, die einzelnen Komponenten ineinander zu verzahnen, was schlussendlich in einer geringeren Abhängigkeit von Dritten und einer höheren Gewinnmarge resultieren soll. [[Golem](https://www.golem.de/news/arm-statt-x86-was-apple-silicon-fuer-den-pc-markt-bedeutet-2006-149241.html)]

Mich interessiert hier vor allem eins, nämlich ob x86 und ARM parallel den PC-Markt nach vorne bringen können oder ob die *Fragmentierung,* die jetzt durch die Aufspaltung der Plattformen beginnt, das Gegenteil bewirkt. Dies ist die Frage, welche wahrscheinlich ganz von alleine in den nächsten Jahre beantworten werden wird. Ich bin ein Freund alter Vintage-Computer und wenn ich so an einem [Atari ST](__GHOST_URL__/atari-1040-st-in-2018/) oder [Amiga 1200](__GHOST_URL__/amiga-retro-computing/) herum spiele, da habe ich mir dieser Tage häufig schon verschiedene Hardwareplattformen herbei gewünscht, eben etwas Abwechslung, so wie damals. Seit ich zu Beginn der 90er mit Computern (386 SX 25) angefangen habe, da gab es eigentlich immer schon nur x86. *But there is more*.

Einige Dinge bleiben indes unbeantwortet: 

- Thunderbolt - diese Schnittstelle ist ja eine Kooperation zwischen Intel und Apple
- BootCamp (Windows 10 for Arm?)
- …

Apple bietet übrigens ab sofort für seine Entwickler ein Entwicklungskit auf ARM-Basis an, also mit Apple Silicon Chip. Dieser steckt in einem aktuellen Mac Mini Gehäuse, verfügt über 16 GB-Ram, eine 512 GB SSD und den Apple A12Z Chip. In folgendem [Artikel](https://www.heise.de/news/Entwickeln-fuer-ARM-Was-in-Apples-Transition-Kit-steckt-4793374.html) wird verdeutlicht, was es damit auf sich hat. […] Die Kosten für die Teilnahme am DTK, das auch Beta-Software samt Tools, Zugriff auf virtuelle Entwickler-Labore, die technische Dokumentation, ein privates Forum sowie Support bei der Entwicklung beinhaltet, liegen bei 500 US-Dollar. In Deutschland liegen die Kosten bei 539 Euro inklusive Mehrwertsteuer. Trotzdem bleibt der Mac nur geliehen.
![So ähnlich sieht der Mac-Mini for ARM aus: Macmini8,1, Mac Mini Unibody A1993. (C) CC BY-SA 4.0](__GHOST_URL__/content/images/2020/06/1280px-Mac_Mini_-2018-.jpg)So ähnlich sieht der Mac-Mini for ARM aus: Macmini8,1, Mac Mini Unibody A1993. (C) [Derorgmas](https://commons.wikimedia.org/wiki/User:Derorgmas)[CC BY-SA 4.0](https://creativecommons.org/licenses/by-sa/4.0)
Übrigens hat Apple noch viele weitere Dinge vorgestellt, die auch alle spannend sind, hauptsächlich Software wie das neue **macOS Big Sur** (mac OS 11), aber mich nicht im geringsten so sehr interessieren, wie der Wechsel der Architektur.
