---
title: Hallo, MacMini M1
slug: hallo-macmini-m1
date_published: 2020-12-11T16:22:54.000Z
date_updated: 2020-12-21T13:42:05.000Z
tags: apple silicon, M1, macmini
---

Ich konnte es nicht lassen und musste zuschlagen. Wie der Zufall es so wollte, hatte ich mich ja gerade erst von meinem geliebten MacPro6,1 aka Trashcan getrennt und somit zur Verfügung stehende Ressourcen. Ich hatte ohnehin mit einem *MacMini* geliebäugelt, aber eigentlich mit dem dato noch aktuell stärksten MacMini CoreI7 von 2018. Diese standen gebraucht für ca. 1500€ zur Debatte.

Und dann kam Apple mit seiner *OneMoreThing* Keynote zum neuen **Apple Silicon M1** Chip um die Ecke… und die Welt war eine [andere](__GHOST_URL__/bam-apples-m1-und-wie-er-die-welt-aufschreckt/). Weniger patetisch gesprochen muss man einfach konsternieren, dass ich keine andere Wahl hatte als für den Heimgebrauch einen neuen MacMini M1 anzuschaffen. Denn so viel Leistung für so wenig Geld kann mir kein anderer Mac bieten, überhaupt keiner. 
GerätPreisGeekbench SinglecoreGeekbench Multicore**Mac Mini M1** (2020)769€1738*7558*iMac 27" Core i7 4.2 (2017)ca. 2000€1119**4559**iMac 27" Core i5 3.7 (2019)ca. 2200€1131**5410**iMac 27" Core i5 3.0 (2019)ca. 1600€1011**4849**iMac 27" Core i5 3.3 (2020)ca. 1800€1149**5856**iMac 27" Core i7 3.8 (2020)ca. 2500€1217**7750**MacPro5,1 12-Core 3.33 (2009)ca. 1000€654*6752*
* Eigener Wert, siehe [Geekbench Browser Profil](https://browser.geekbench.com/user/7822)

** werte von everymac.com
![Apple MacMini M1](__GHOST_URL__/content/images/2020/12/IMG_3492.jpeg)mein Apple MacMini M1 in der Basiskonfiguration
Ich liebäugelte zwischendurch auch mit einem iMac in 27" aufgrund seines schönen 5K Displays was sicher zu überzeugen weiß. Aber um einen iMac zu finden der gebraucht schneller als mein bisheriges Setup war, brauchte es schon einiges an Geld. Und da ich nun kurzerhand an einen nagelneuen Fujitsu USB-C Thunderbolt-Monitor ([den](https://www.fujitsu.com/de/products/computing/peripheral/displays/p27-9-ts-qhd/index.html)) gekommen bin, lag der **MacMini M1** eben auf der Hand. Für knapp 800€ habe ich eine Leistung, die ich im iMac erst im 2019er I7 erreichen würde. Für ca. 2000€ gebraucht. Richtig, ich habe mich für die Grundkonfiguration entschieden. Nach sehr vielen Reviews sollte diese locker für alle meine Tätigkeiten ausreichen und da ich nicht vorhabe den Mini für 15 jahre zu nutzen, benötige ich auch keine 16 GB Ram oder 2 TB SSD. Aufgrund der OnChip-Integration kann man 8 GB Ram des M1 auch nicht mit herkömmlichen gesteckten Speicher eines Intel-Macs vergleichen, die Zugriffszeiten sind andere. 
![MacMini M1 neben Fujitsu 27&quot; Display und legendärer A1243 Tastatur](__GHOST_URL__/content/images/2020/12/IMG_3495.jpeg)MacMini M1 neben Fujitsu 27" Display und legendärer A1243 Tastatur
*Allerdings* ist hier nicht wirklich klar, wann denn die iMacs überarbeitet werden und auch mit dem Apple Silicon laufen. Ich warte lieber ab, nutze die Zeit mit dem MacMini M1 und schlage vielleicht später zu. Aber das kann gut und gerne 2 Jahre dauern, haben die iMacs ja erst in diesem Jahr ein Upgrade erfahren. Es bleibt spannend.
![BootCamp gibt es für die M1 Apple Silicon nicht mehr.](__GHOST_URL__/content/images/2020/12/Bildschirmfoto-2020-12-12-um-21.46.21.png)BootCamp gibt es für die M1 Apple Silicon nicht mehr.
Programme die noch nicht auf die ARM-Architektur des Apple Silicon hin optimiert sind, werden nahtlos im Hintergrund übersetzt. Dies funktioniert über die Rosetta2 Emulation, die es bereits beim Wechseln von PowerPC hin zu Intel gab. Das funktioniert absolut reibungslos bei einer großen Anzahl von Programmen. Startet man eine Software die noch nicht übersetzt ist, dann wird einmalig Rosetta2 installiert und steht fortan zur Verfügung.
![Apple M1 Installation von Rosetta2 für MS Office](__GHOST_URL__/content/images/2020/12/Bildschirmfoto-2020-12-11-um-17.20.55.png)Apple M1 Installation von Rosetta2 für MS Office
Ich habe den MacMini in der Basiskonfiguration gewählt. Also mit einer 256 GB SSD und 8 GB Ram. Das mag wenig klingen, allerdings kann man, wie oben schon erwähnt, aufgrund der *Unified Memory Architecture* (alles in einem Chip, keine Wege), 8 GB Ram nicht mit 8 GB Ram vergleichen. Und in der Tat, der Rechner zeigt was er kann. Er arbeitet absolut nahtlos, damit meine ich: man wartet nicht. Alles funktioniert sofort. Und das allerschönste: er ist praktisch unhörbar. Er bleibt kühl. Selbst nach einem kleinen [Cinebench R23](https://apps.apple.com/de/app/cinebench/id1438772273?l=en&amp;mt=12) Testlauf von 40 Minuten war der Lüfter praktisch nicht zu hören und der Mac nicht mal handwarm. Obwohl der Prozessor dauerhaft ausgelastet war, quasi alle Kerne auf 100% liefen. Wenn ich meine drehenden Thunderbolt-Festplatten nicht einschalte, habe ich eine absolut lautlose Workstation. Ein nicht zu unterschätzender Faktor, denn was nützt mir ein 2020er iMac mit Core-I9 Prozessor und 10 Kernen (der im Multicore 1000 Punkte schneller als der M1 ist), der aber bei kleinster Last die Lüfter aufdreht und auch ohne Belastung ständig zu hören ist? (vgl. Tests des iMacs)

Und die Geschwindigkeit. **Grundgütiger**. Der *MacMini* ist im SingleCore doppelt so schnell wie mein MacPro 2013 und überflügelt diesen sogar im Multicore um 2000 Punkte. Man merkt diese theoretische Leistungssteigerung auch praktisch im Alltag. Das geht bei Office los was noch durch Rosetta emuliert werden muss und trotzdem schneller läuft, als die native Intel-Version. Und geht weiter bis zu Videoschnitt in 4K der so leicht von der Hand geht, als würde es das System überhaupt nicht interessieren. Es gibt hier viele Möglichkeiten dies festzustellen, aber wie es sich anfühlt daran zu arbeiten, das muss man einfach selber erleben. 

Es lohnt sich, vor allem für den Preis und wenn man ohnehin einen neuen Mac anschaffen möchte, dann sollte man zum M1 greifen.

### Welche Software läuft?

- HomeBrew: läuft noch nicht, kann über [Rosetta2](https://developer.apple.com/documentation/apple_silicon/about_the_rosetta_translation_environment) genutzt werden
- Microsoft Office: über Rosetta2 ([Link](https://support.microsoft.com/en-us/office/microsoft-365-and-office-2019-support-for-apple-silicon-c55b603e-14a6-4b69-bdc0-2bb4c9a36834)) Beta nativ lauffähig
- iTerm2: optimiert für M1
- Chrome: optimiert für M1
- Geekbench: optimiert für M1
- sämtliche Apple Apps: optimiert für M1
- Microsoft Windows via BootCamp wird nicht mehr unterstützt, aber vielleicht gibt es eine native Windows for Arm Version für den M1.
- Linux für ARM und Apples M1: derzeit in frühen Betatests, aber das wird
