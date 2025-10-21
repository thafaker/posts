---
title: Wie ich auszog meinen MacPro zu warten und ihn kaputt und wieder ganz machte
slug: wie-ich-auszog-meinen-macpro-zu-warten-und-ihn-kaputt-und-wieder-ganz-machte
date_published: 2019-09-20T12:32:20.000Z
date_updated: 2024-01-29T09:02:00.000Z
tags: bigmac, prozessorboard, bent lga pins, verbogen, xeon, macpro, video
---

Ich hatte meinen **MacPro4,1** damals aufgerüstet (Link zu meinem [Ultimate Guide to MacPro](__GHOST_URL__/ein-kleiner-abriss-zu-meinem-mac-pro-bigmac-2/)), so trug es sich zu, und beim Köpfen der neuen Prozessoren [[1]](#fn1) stellte ich fest, dass die alte Wärmeleitpaste über die Jahre ziemlich fest und angebacken war und ich diese erneuern sollte. 

Da ich nun aber wissen wollte ob alles funktioniert baute ich den Mac kurzerhand so zusammen und… dabei blieb es dann auch. Der MacPro war wieder ordentlich angeschlossen und unter dem Schreibtisch verstaut, sodass der Wunsch ihn da erneut heraus zu holen und alles abzubauen nicht sehr groß war. Zumal alles lief. Aber die Wärmeleitpaste samt Zubehör hatte ich schon hier liegen und diese sah mich Monat für Monat vorwurfsvoller an. Bis ich gestern endlich auf die Idee kam den Mac zu reinigen und im Zuge dessen auch die Wärmeleitpaste der beiden Prozessoren zu erneuern.

![Bildschirmfoto-2019-09-20-um-10.50.20](__GHOST_URL__/content/images/2019/09/Bildschirmfoto-2019-09-20-um-10.50.20.png)*Der Ausbau meines MacPro. CPU-Upgrade hat funktioniert*

### Eine verhängnisvolle Idee.

Ich habe den Mac also abgebaut und alles auseinander genommen. *Ganz klassisch*. Die vier Festplatten raus, die PCIe-NVME-SSD ([Link](__GHOST_URL__/nvme-ssd-in-macpro4-1/)) raus, die Grafikkarte ([Link](__GHOST_URL__/wie-man-eine-pc-grafikkarte-fur-den-mac-um-flasht-efi-rom/)) raus, das Prozessorboard raus und erst mal alles sauber pusten. Ahhh, das Prozessorboard mit den beiden 3,33 GHz LGA 1366 XEON Prozessoren ([Link](__GHOST_URL__/how-to-delid-and-upgrade-your-macpro-4-1-cpus/)), das Ding was ich *verwärmeleitpasten* möchte, sehr gut.

![zwei geköpfte XEON CPUs mit alter Wärmeleitpaste](__GHOST_URL__/content/images/2019/04/xeon5520-delid-xeon5680-lidded2-1.JPG)*zwei geköpfte XEON CPUs mit alter Wärmeleitpaste*

Es lief eigentlich alles gut, so wie geplant. Ich nahm mir genug Zeit und Ruhe, schraubte die großen Kühlkörper ab und entnahm vorsichtig die beiden Prozessoren. Nun begann ich mit der *rituellen Waschung* der Prozessor-DIEs und versucht mit Alkohol die alte Wärmeleitpaste zu entfernen. Was gar nicht so leicht war. Die Paste war wirklich hart und angebacken, wie eine zweite echte Schicht. Ich war hier besonders vorsichtig und auch nicht so erfolgreich, aber immerhin besser als vorher.

![](__GHOST_URL__/content/images/2019/04/delidded_cpuA_x5680.jpg)

Bei den **LGA-Boards** wie sie die XEONs u.a. im MacPro benutzen, sind die Pins nicht mehr am Prozessor, sondern am Board selber verbaut. Ich setzte die Prozessoren vorsichtig ein, fügte Wärmeleitpaste hinzu und verschraubte die Kühlkörper. Dann kam der Zusammenbau und die Anspannung war groß, aber nach dem Einschalten ertönte der Gong und der Bildschirm zeigte den Apfel-Bootscreen. Alles cool. *Dachte ich…*

Denn nach dem Login stellte ich fest, dass der RAM-Riegel zwei nicht mehr erkannt wird. Von 4 x 8 GB-RAM-Modulen wurden nur 3 erkannt und ich verfügte plötzlich nur noch über 24 GB Ram. Nach endlosem Ein- und Ausbau der Module war klar: nicht der RAM ist defekt, sondern die Bank.

So folgte ein erneuter Ausbau der CPUs, kurzer Check und ein erneuter Einbau. und dann kam der Hammer. Jetzt wurde bei CPU A keiner der RAM-Riegel mehr erkannt. Sie waren alle nicht mehr ansprechbar, wohl aber lief der Mac noch, mit RAM in CPU B, zum Glück. Als ich den Mac nun abermals zerlegt kam die grausige Wahrheit ans Licht: die Pins auf dem Prozessor-Board von CPU A waren verbogen. Durch verbogene Pins kann der ganze Prozessor Schaden nehmen. Es kann aber auch *nur* dazu führen, dass z.B. der RAM nicht mehr erkannt wird, so wie bei mir.

Ich weiß bis heute nicht wie es zu diesen verbogenen Pins kommen konnte. Vielleicht war der Prozessor nicht völlig korrekt aufgesetzt, vielleicht war es zuviel Wärmeleitpaste und hat nach Verschraubung des Kühlkörpers dazu geführt, dass der Prozessor zu viel Druck und Kontakt hatte und so die Pins verbog. Es bleibt mir ein Rätzel. Nach kurzer Recherche im Netz habe ich erkannt, dass dies den Totalschaden meines Macs bedeuten kann. Denn ein neues Prozessorboard kostet gern über 400€, z.B. [hier](https://www.ebay.de/itm/Apple-Mac-Pro-4-1-2009-A1289-630-9402-8-Core-2-26GHz-CPU-Tray/153647309744?hash=item23c617e3b0:g:b-0AAOSwQXZdgfGq). Also beschäftigte ich mich nun notgedrungen damit, wie man diese Pins wieder gerade biegen kann. Bei mir sah das ungefähr so aus:

![Bildschirmfoto-2019-09-20-um-13.08.40](__GHOST_URL__/content/images/2019/09/Bildschirmfoto-2019-09-20-um-13.08.40.png)

Und folgendermaßen sollte es aussehen, wenn alles in Ordnung ist.

![1024px-Intel_Socket_1155](__GHOST_URL__/content/images/2019/09/1024px-Intel_Socket_1155.jpg)

Der nächste Schritt war, an eine Lupe zu gelangen. Wer hat schon eine Lupe zu Hause? Eine brauchbare Lupe? *Wir nicht*. Und auch niemand sonst. Aber hatte ich eine Uhrenmacherlupe, die man sich ins Auge klemmt.

![IMG_0586](__GHOST_URL__/content/images/2019/09/IMG_0586.JPG)

Mit dieser Lupe, ca. 2 Stunden Zeit und mehreren Try-And-Error-Durchläufen ist es mir tatsächlich gelungen, die Pins wieder so gerade zu biegen, als das mein MacPro wieder läuft. Ein Wunder. Ich hatte Tränen in den Augen.

Und ich schwöre feierlich: nie wieder will ich Hand an die Prozessoren legen, NIE WIEDER. Hier gibt es übrigens ein [Beispielvideo](https://www.youtube.com/watch?v=MX3ppQdwH-k).

PS: Hier geht es zu meinem [Geekbench-Ergebnis](https://browser.geekbench.com/v4/cpu/14643774)[[2]](#fn2), ich finde 26.000 Punkte für einen Computer von 2009 unglaublich gut.

![IMG_1297-1](__GHOST_URL__/content/images/2019/09/IMG_1297-1.jpeg)Mein geöffneter MacPro4,1

Es folgt ein kurzes Video, welches ich während dieser Misere gedreht - und jetzt erst fertig geschnitten - habe. Es ist nur ein kleiner Zeitvertreib, die wichtigen Infos stehen ohnehin in diesem Blogbeitrag.

---

1. 
Köpfen (eng. *Delidding*) bedeutet, den integrierten Heatspreader einer CPU abzunehmen. Das ist notwendig bei den MacPro4,1, sonst passen die Kühlkörper nicht auf den Rechner. [↩︎](#fnref1)

2. 
Geekbench ist ein betriebssystem-übergreifender Benchmark zum Vergleich von Computern. [↩︎](#fnref2)
