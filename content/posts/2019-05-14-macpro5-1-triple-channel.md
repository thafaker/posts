---
title: MacPro5,1 Triple Channel Speicher RAM
slug: macpro5-1-triple-channel
date_published: 2019-05-14T16:40:18.000Z
date_updated: 2024-09-19T11:13:56.000Z
tags: ram, mem, speicher, macpro, macpro5,1, bigmac
---

Der Mac Pro verfügt über 4 oder 8 Speicher-Slots, je nachdem ob er mit einer Single oder Dual-CPU bestückt ist. Welchen MacPro man vor sich hat, das weiß man in der Regel, macht es *monetär* doch einen erheblichen Unterschied aus. Und jeder andere kann das ganz leicht überprüfen, indem er "Über diesen Mac" aufruft.
![](__GHOST_URL__/content/images/2019/05/about_this_bigmac-1.png)Über diesen Mac: Prozessor: 2 x 3,33 GHz entspricht zwei CPUs. 
Mein Mac Pro ([Link](__GHOST_URL__/tag/bigmac/)) verfügt über zwei Prozessoren und verfügt pro CPU über 4 Speicherbänke, hat also maximal 8 Speicherbänke zur Bestückung zur Verfügung.
![](__GHOST_URL__/content/images/2019/05/Bildschirmfoto-2019-05-14-um-18.24.22.png)
### Triplechannel

Für mich war absolut logisch, diese 2 x 4 Slots auch voll zu bestücken. Allerdings ist das gar keine so gute Idee. Denn die Prozessoren im Mac Pro 5,1, sogenannte **Westmere CPUs**, bei mir 2 x Intel® Xeon® Prozessor **X5680** ([Link (archiviert)](http://web.archive.org/web/20220430033743/https://www.intel.de/content/www/de/de/products/sku/47916/intel-xeon-processor-x5680-12m-cache-3-33-ghz-6-40-gts-intel-qpi/specifications.html)), verfügen über sogenannten Triple-Channel. Jeder Prozessor kann Speicher also mit *drei Kanälen* anbinden. 
![MacPro4,1 CPU Board with RAM](__GHOST_URL__/content/images/2019/04/IMG_2742.JPG)
Die Technik, die schon beim *Dual-Channeling* eine Verdopplung der Transferrate durch zeitversetztes Zugreifen auf mindestens zwei Module funktionierte, wird nun mit drei Modulen durchgeführt, was zur Verdreifachung der Transferrate führt. Die Latenzzeiten der Speicher gehen nicht mehr stark in die Zugriffszeit ein, was zu der Leistungssteigerung führt. Damit dieses Verfahren sauber funktioniert, müssen immer drei Module gleicher Spezifikation genutzt werden.
![](https://images.unsplash.com/photo-1505424297051-c3ad50b055ae?ixlib=rb-1.2.1&amp;q=80&amp;fm=jpg&amp;crop=entropy&amp;cs=tinysrgb&amp;w=1080&amp;fit=max&amp;ixid=eyJhcHBfaWQiOjExNzczfQ)Photo by [Johannes Plenio](https://unsplash.com/@jplenio?utm_source=ghost&amp;utm_medium=referral&amp;utm_campaign=api-credit) / [Unsplash](https://unsplash.com/?utm_source=ghost&amp;utm_medium=referral&amp;utm_campaign=api-credit)
### FAZIT

Der Dual-Prozessor Mac Pro hat also zwei Speicherbänke á vier Slots, jede Speicherbank ist einer der beiden CPUs zugeordnet. Wir haben pro CPU drei Kanäle, Triple-Channel. Ich lasse also pro Speicherbank Slot 4 frei, dann funktioniert das mit dem Triple-Channel nämlich problemlos und alle 6 Speicherslots sind mit voller Geschwindigkeit angebunden. Tun wir das nicht, ist der Mac vollausgebaut am Ende sogar langsamer, weil er quasi mit drei Kanälen vier Slots biedenen muss und deshalb umher*swappt*.
![](__GHOST_URL__/content/images/2019/05/Bildschirmfoto-2019-05-14-um-18.20.22.png)Triple-Channel Bestückung in rot markiert
Mein Mac Pro wird noch 2 x 8 GB Ram erhalten, somit komme ich auf ausreichend gute 48-GB-Ram, die mir für meine Arbeiten ausreichen sollten. Zur Zeit sind die Preise recht niedrig, sodass dieses Upgrade nicht sehr teuer zu stehen kommt.

💡

**MERKE**: MacPro nicht voll bestücken, sondern den vierten Slot pro CPU frei lassen, um die volle Tripple-Channel-Geschwindigkeit des Chipsatzes ausreizen zu können.

### Ressourcen

- Hier kann man sehen, dass Tripple-Channel in vielen Fällen mehr bringt, als mehr Speicher zu haben: [http://www.barefeats.com/nehal04.html](http://www.barefeats.com/nehal04.html)
- Technische Spezifikation des Mac Pro 2012: [https://support.apple.com/kb/SP652?viewlocale=en_US&locale=en_US](https://support.apple.com/kb/SP652?viewlocale=en_US&amp;locale=en_US)
- Mein *Ultimate Guide to Mac Pro* gibt es hier: [https://thahipster.de/ein-kleiner-abriss-zu-meinem-mac-pro-bigmac-2/](__GHOST_URL__/ein-kleiner-abriss-zu-meinem-mac-pro-bigmac-2/)

An [dieser Stelle](__GHOST_URL__/nvme-ssd-in-macpro4-1/) berichte ich, wie ich meinen MacPro5,1 um NVME-SSD PCI-Express erweitert habe, um maximal Geschwindigkeit zu erzielen.

- [NVME SSD in MacPro 2009 aufwärts](__GHOST_URL__/nvme-ssd-in-macpro4-1/)
