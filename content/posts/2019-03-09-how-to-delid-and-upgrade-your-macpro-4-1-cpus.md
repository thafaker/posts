---
title: How To Delid and Upgrade your MacPro 4,1 CPUs
slug: how-to-delid-and-upgrade-your-macpro-4-1-cpus
date_published: 2019-03-09T18:21:00.000Z
date_updated: 2019-12-15T16:14:01.000Z
tags: macpro, bigmac, anleitung, howto, how to, cpu, delid, köpfen, deckel, delidding, xeon, cpus, x5680
---

In diesem Artikel möchte ich kurz von dem verwegenen Plan und seiner Durchführung berichten, wie ich mir zwei **Xeon X5680 CPUs** mit *3,33 GHz* und 6 Kernen kaufte, diese Prozesorren von ihrem Heatspreader (vulgär: köpfen) befreite und sie in meinen MacPro 4,1 einbaute, der nunmehr 12 Kerne und 32 GB Ram hat. Über das kleine Upgrade des RAMs habe ich an [dieser Stelle](__GHOST_URL__/als-ich-neulich-den-arbeitsspeicher-erweiterte/) berichtet. 

Apple verbaut in seinem Dual-Prozessor MacPro 4,1 nur CPUs ohne Heatspreader. [[1]](#fn1) Das liegt an der Hitzeentwicklung und dem Kühlkonzept des Dual Mac Pro 4,1 von 2009. Normalerweise aber haben die Prozessoren immer einen Deckel drauf. Damit der DIE [[2]](#fn2) nicht kaputt geht. Das ist der eigentlich Kern des Prozessors. Damals, zu Athlon XP Zeiten, als der DIE frei zugänglich war, da haben viele Endbenutzer ihre CPUs geschrottet weil sie bei der Montage des Kühlkörpers (oder wie auch immer) den Prozessor zerstörten. So entschieden die Hersteller, einen Deckel drauf zu setzen. Den sogenannten *IHS*, **I**ntegrated **H**eat **S**preader. Wir müssen diesen IHS also zwangsläufig entfernen damit unsere neuen CPUs die wir upgraden, nahtlos in unserem Mac Pro funktionieren. Doch dazu später mehr.

![Intel Xeon CPUs - unten ohne IHS, oben mit IHS](__GHOST_URL__/content/images/2019/04/xeon5520-delid-xeon5680-lidded2-1.JPG)Intel Xeon CPUs - unten ohne IHS, oben mit IHS

Auf diesem Bild sieht man unten zwei XEON CPUs ohne Heatspreader (die originalen CPUs Apple), diese sind delidded, oben sieht man zwei XEON CPUS mit Heatspreader (die Neuen). Der Mac Pro 4,1 ist wie gesagt so konzipiert, dass man nur CPUs ohne IHS nutzen kann [[3]](#fn3). Diese gibt es jedoch nicht einfach so zu kaufen. Möchte man nun seinen Dual Mac Pro aufrüsten, so steht man vor dem Problem diese IHS entfernen zu müssen, damit auch die neuen Prozessoren:

- korrekt und wie ursprünglich von Apple designed gekühlt werden
- die Bauhöhe des Prozessorboards mit dem Kühlkörper noch passt

Denn wenn der Heatspreader noch auf der CPU sitzt erhöht sich die Bauhöhe des Prozessor-Boards und passt schlechter in den Mac Pro. Weiterhin kann bei Montage des Kühlkörpers die CPU mit IHS zerstört werden, die Pins können abbrechen und natürlich ist die Kühlleistung mit IHS schlechter, als ohne. Viele Overclocker-Websites preisen schon immer das Delidding (so heißt das nämlich, wenn man den IHS entfernt) der CPUs an. Sie behaupten an dieser Stelle einen Temperatur-Vorteil von 10 - 20 Grad. Das ist enorm und gerade wenn man seine CPU übertakten will, ist es besser so wenig wie möglich Wärme zu produzieren.

Das wollen wir jedoch nicht. Wir wollen aber, dass unser Mac Pro nach dem Upgrade (ich upgrade von 2 x 2,26 GHz Xeon E5520 auf 2 x 3,33 GHz Xeon X5680) absolut stabil läuft, nicht übermäßig viel Hitze produziert und dadurch weiterhin angenehm leise bleibt. Mit mehr Power. Zumindest soweit wie möglich. Denn die alte CPU hat 80 Watt, die neue bis zu 130 Watt Wärmeverlustleistung. Diese Hitze muss natürlich raus. Und genau deshalb entfernen wir von unseren neuen Xeon CPUs die Deckel. Hier gibt es übrigens eine [Übersicht mit sämtlichen kompatiblen Prozessoren](https://forums.macrumors.com/threads/mac-pro-cpu-compatibility-list.1954766/) im Mac Pro 4,1 sowie 5,1. Demnach ist völlig klar dass ich nun den zweitstärksten Prozessor verbaut habe, der möglich ist. Schneller ist nur der X5690, der allerdings pro Stück gern mal bis zu 200€ kostet und sich für mich kosten/nutzen-mäßig nicht rechnet

### Mac Pro 4,1 und 5,1 2009 2010 2012 (Käsereibe)

Die Mac Pros 4,1 und 5,1 sind hardwareseitig nahezu identisch. Weiterhin sind auch der Mac Pro 2009, 2010 oder 2012 absolut identisch. Innerlich. Allerdings kann der Mac Pro 4,1 2009 von Werk aus nicht die modernen Prozessoren und Speicher verwenden, wie es der Mac Pro 2012 kann. Jedoch sind die Upgrades die Apple seinen Macs spendierte nur softwaretechnischer Natur. Das heißt, man kann mit einem Firmware-Upgrade einen MacPro 4,1 von 2009 auf die Situation eines Mac Pro 5,1 von 2012 bringen. [Hier (archiviert)](http://web.archive.org/web/20180218110056/http://forum.netkas.org:80/index.php/topic,852.0.html) ist beschrieben wie das geht. Und die können beispielsweise die *Westmere CPUs* mit je 6 Kernen nutzen. Und 128 GB Arbeitsspeicher (im DUAL CPU Mac) mit 1333 MHz adressieren. **Hammer**.

Grund genug also, sich günstig einen Mac Pro 4,1 mit zwei Prozessoren auf eBay zu kaufen und diesen aufzurüsten. 

Dieser Geheimtipp ist allerdings schon lange keiner mehr und so rufen die alten Mac Pro mittlerweile auch dementsprechende Preise auf dem Gebrauchtwarenmarkt auf. *Zurecht*. Denn der Mac Pro ist aufrüstbar, hat sehr viel Leistung, ist modular und hat ein großartiges Design. Aber ich komme ins Schwärmen…

### How To Mac Pro 4,1 CPU Delidding (Wie man seine CPU köpft)

![Mac Pro 4,1 geöffnet, mit Prozessorboard](__GHOST_URL__/content/images/2019/04/mac_pro_open.png)Mac Pro 4,1 geöffnet, mit Prozessorboard

Prozessorboard aus dem Mac Pro holen.

![processor-board_assembled](__GHOST_URL__/content/images/2019/04/processor-board_assembled.JPG)DUAL Prozessorboard Mac Pro 4,1 mit 4 x Speicher

Nun sollte man die Kühlkörper abschrauben. Am besten immer über Kreuz. Dazu benötigt ihr einen ziemlich langen Inbus der Größe 3.

![processorboard-cooler](__GHOST_URL__/content/images/2019/04/processorboard-cooler.JPG)Prozessorboard mit entferntem Kühlkörper

Wenn ihr beide Kühlkörper entfernt habt, sieht das ganze so aus. Rechts befindet sich CPU A und links CPU B. An dieser Stelle muss ich noch mal über das geile Kühlkonzept seitens Apple schwärmen. Schaut euch diese Grazie an.

![heatsinkB](__GHOST_URL__/content/images/2019/04/heatsinkB.JPG)Kühlkörper mit Lüfter

Die beiden großen Kühlkörper mit innenliegendem Ventilator und dem fetten Kupfer-Wärmeleiter sorgen dafür, dass die Prozessoren angenehm kühl bleiben und die Hitze schnell abtransportiert wird.

![kupfer-heatsink](__GHOST_URL__/content/images/2019/04/kupfer-heatsink.jpg)Kupfer-Heatsink

Es folgt eine Detailaufnahme der originalen CPU ohne IHS, wie sie von Apple verbaut wurde:

![processor_board-cpub](__GHOST_URL__/content/images/2019/04/processor_board-cpub.jpg)CPU B ohne Kühlkörper

Es ist an dieser Stelle angeraten, die alten Wärmeleitpasten-Überreste am Kupfer-Kühlkörper restlos zu entfernen. Diese sind nach Jahren des Betriebs fest sowie brüchig geworden und leiten keine Wärme mehr ab.

### Köpfen der CPU

Der kniffligste Part vor dem die meisten Menschen zurecht die größte Angst haben. Der Schritt wo man den IHS (Deckel) von der CPU entfernt. Dieser ist sehr fest angebracht und es gibt verschiedene Wege zum Ziel.

Für mich war das auch einfach eine Kostenfrage. Zahle ich für zwei geköpfte CPUs ohne IHS 180€ (z.B. [hier](https://www.ebay.de/itm/2x-Intel-Xeon-X5680-3-33-GHz-no-ohne-IHS-Matched-Pair-fur-Apple-Mac-Pro-4-1-2009/361753825971?hash=item543a3552b3:g:HO4AAOSwNRdX78VP)) oder zahle ich für zwei CPUs mit IHS nur 90€. Weiterhin liebe ich den Mac Pro ja gerade dafür, dass man im Gegensatz zu allen anderen Macs (vor allem iMac etc.)  alles selber machen kann. Und so habe ich mich nicht gescheut meine CPUs selber zu köpfen.

![Oben die beiden neuen CPUs XEON x5680 mit IHS](__GHOST_URL__/content/images/2019/04/xeon5520-delid-xeon5680-lidded2-1.JPG)Oben die beiden neuen CPUs XEON x5680 mit IHS

Die oberen beiden Prozessoren sind die neuen XEON X5680, die noch geköpft werden müssen. Es gibt wie gesagt verschiedene Möglichkeiten dies zu tun, man kann beispielsweise mit Rasierklingen arbeiten ([hier](https://www.youtube.com/watch?v=WoLkniC_JiE) eine Anleitung mit Rasierklingen und Hitze), die CPU und den Deckel erhitzen und so zum Ziel kommen, oder man nimmt einen Schraubstock, klemmt die CPU ein und erhöht langsam aber steig den Druck, bis es plopp macht und man die CPU vom Heatspreader befreit hat. Ich rate euch, [folgendes Video](https://www.youtube.com/watch?v=yP8FpwrGeTk) sehr gewissenhaft anzuschauen, dies klärt eigentlich alles auf.

![x5680-vice](__GHOST_URL__/content/images/2019/04/x5680-vice.JPG)Bild 1: XEON CPU delid in Vice

Das sieht dann ungefähr wie auf Bild 1 und 2 aus.

![x5680-vice_2](__GHOST_URL__/content/images/2019/04/x5680-vice_2.JPG)Bild 2: XEON CPU delid in Vice

Wichtig ist, dass man die CPU folgendermaßen in den Schraubstock einspannt, damit man keine Parts unter dem IHS zerstört weil man den IHS falsch entfernt:

![So muss die CPU in die Klemme eingespannt werden.](__GHOST_URL__/content/images/2019/04/how-to-vice.JPG)So muss die CPU eingespannt werden.

Und wenn man alles richtig gemacht hat, dann sieht das Ergebnis so aus, wie bei mir. Der Deckel ist sauber vom Prozessor getrennt. Den Prozess seht ihr übrigens wie zuvor schon beschrieben sehr anschaulich in [folgendem Video](https://www.youtube.com/watch?v=yP8FpwrGeTk), so brachial war das bei mir übrigens nicht. Keine Ahnung warum das hier so schlimm aussieht. Vielleicht hatte der protagonist auch einfach nur keine Kraft.

![delidded_cpuA_x5680](__GHOST_URL__/content/images/2019/04/delidded_cpuA_x5680.jpg)Vom Headtspreader IHS getrennter Xeon X5680

Jetzt geht es darum die Überreste des Klebers auf der CPU vom IHS zu entfernen, das sollte man ganz vorsichtig mit einem scharfen Messer, ich habe einen Cutter genutzt, durchführen. Und vorsicht, nichts abschneiden was da noch so drauf ist. Rot wegschneiden, bei den grünen Bereichen höllisch aufpassen.

![delidded_both_x5680](__GHOST_URL__/content/images/2019/04/delidded_both_x5680.JPG)die rot markierten Klebereste des IHS entfernen, die grün markierten Teile beachten!

Weiterhin ist anzuraten, auch die alte Wärmeleitpaste auf dem DIE zu entfernen und später neue aufzutragen. Diese leitet die Abwärme aus dem Prozessorkern in den Kupferkühler und weiter über die Lamellen aus dem Gehäuse des Macs. Das ist also ein wichtiger Part.

Am Ende wird alles wieder ordentlich zusammen gesetzt, der Mac Pro neu gestartet und hoffentlich meldet er sich mit einem freundlichen Login-Screen. [[4]](#fn4)

![about_mac_done](__GHOST_URL__/content/images/2019/04/about_mac_done.png)Mein Mac Pro mit 2x6-Kern XEON und 32 GB Ram, eine Höllenmaschine.

![geekbench](__GHOST_URL__/content/images/2019/04/geekbench.png)
Geekbench
![macpro](__GHOST_URL__/content/images/2019/04/macpro.png)

An dieser Stelle haben wir die schwierigste Operation im Upgrade-Prozess unseres Big Macs abgeschlossen. *Das wars auch schon wieder, bis bald.*

---

**Artikelbilder**: (C) Jan Montag 2019

---

1. 
Bei Single-CPU MacPro 4,1 ist das nicht so. Beim Mac Pro 5,1 mit Dual CPU ist das auch nicht so. Diese Anleitung betrifft also nur den Mac Pro 4,1 Dual CPU. [↩︎](#fnref1)

2. 
Ein **Die** ist in der Halbleiter- und Mikrosystemtechnik die Bezeichnung eines einzelnen, ungehäusten Stücks eines Halbleiter-Wafers. Ein solches Die wird üblicherweise durch Sägen oder Brechen des fertig bearbeiteten Wafers in rechteckige Teile (dicing) gewonnen. In der Regel befindet sich auf einem Die ein Bauteil, z. B. ein Transistor, Leuchtdiode, oder eine komplexe Baugruppe, z. B. integrierter Schaltkreis, ein Mikrosystem. ([Quelle](https://de.wikipedia.org/wiki/Die_(Halbleitertechnik))) [↩︎](#fnref2)

3. 
Sicher wird es irgendwo im Netz auch Menschen geben, die im Dual Mac Pro 4,1 ihre CPUs mit Heatspreader benutzen und den IHS nicht entfernt haben, aber wenn wir uns schon ein mal die Mühe machen, dann können wir es auch einfach richtig machen, nicht wahr? [↩︎](#fnref3)

4. 
[Hier](https://browser.geekbench.com/v4/cpu/14643774) findet ihr mein Geekbench-Ergebnis, über 25.000 Geekbench Punkte. Unglaublich, vorher hatte ich knapp 13.000. Das ist ein enormes Ergebnis. Es gibt noch immer nicht viele Macs die schneller sind. [↩︎](#fnref4)
