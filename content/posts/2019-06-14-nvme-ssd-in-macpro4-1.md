---
title: NVME SSD in MacPro 2009 aufwärts
slug: nvme-ssd-in-macpro4-1
date_published: 2019-06-14T14:56:21.000Z
date_updated: 2020-07-17T09:27:37.000Z
tags: bigmac, cMP, mac pro, nvme ssd, anleitung, howto, how to
---

Auch wenn durch die [Vorstellung des MacPro7,1](__GHOST_URL__/macpro7-1-die-neue-kasereibe/) aka 2019 die Räder der Zeit endlich weiter drehen, vor allem nach der sprichwörtlichen Müllsache des MacPro TrashCan von 2013, bleibt der MacPro von 2009 auch weiterhin attraktiv. Zum einen weil die Leistung eines Vollausbaus auch heute noch für viele Anwendungen ausreicht und zum anderen, weil nicht jeder gleich 6000€ Startpreis berappen kann, um den neuen Mac Pro zu erwerben.

Grund genug für mich und meinen kleinen classic MacPro (cMP), diesen um eine neue Komponente zu erweitern, die nicht sonderlich teuer in den Geldbeutel schlägt: der Einbau einer NVME-SSD als Startvolume.

NVMe (Non-Volatile Memory Express) ist derzeit das Non-Plus-Ultra wenn es um Festplatten geht. Dies liegt an der unglaublichen Geschwindigkeit, die NVMe erzielen kann. Zum Beispiel eine aktuelle *970 Evo von Samsung*, diese erreicht unglaubliche 2237 MB/s lesend und 1405 MB/s schreibend, das ist drei bis viermal so schnell wie die Schreib/Lesegeschwindigkeit von  SATA. Weiterhin scheint NVMe auch schneller beim 4k Random read/write Zugriff. NVMe ist so konzipiert dass es ausschließlich über PCIe läuft und folgt sozusagen ACPI nach. Aber wie dem auch sei, macOS und so auch der MacPro haben nicht immer NVMe untersützt. 

Erst mit macOS 10.13 wurden NVMe SSDs unterstützt, allerdings nur als Massenspeicher im System, jedoch nicht bootfähig. Was schade ist, klar will man sein System auf so nem flotten Teil installieren. Aber da Apple mit der Veröffentlichung von einem neuen, modularen MacPro nicht voran kam und der 2013er MacPro ein ziemliches Desaster darstellter, spendierte Apple dem MacPro ab 2009 tatsächlich noch mal ein neues Bootrom (140.0.0.0) mit dem es möglich wurde, native von NVMe zu booten. Yeah. Und so sind wir hier. Mit einem MacPro 2009 der ordentlich aktualisiert worden ist, um nun als System auf NVMe zu installieren. 

### NVMe im MacPro ab 2009 (4,1; 5,1)

Weil der PCIe-Anschluss im MacPro nur 2.0 kann, schafft er im maximalen Datendurchsatz nur ca. 1500 MB (mit einer non-switched Adapterkarte). Aus diesem Grund habe ich keine extra teure 970er EVO SSD mit maximaler Performance gekauft, sondern auf mein Budget geachtet. Mittlerweile gibt es die empfehlenswerte Crucial P1 NVMe SSD mit 1TB Speicher für knapp 115€ auf Amazon. Da wir noch eine PCIe-Steckkarte für die SSD benötigen, habe ich hier eine für 15€ drauf gepackt und noch einen kleinen Kühlkörper geordert, weil die SSDs doch recht heiß werden und dann ihre Geschwindigkeit herunter drosseln. Alles in allem habe ich folgende Teile gekauft (keine Affiliate-Links):

- Crucial P1 1TB NVMe SSD ([Link](https://www.amazon.de/gp/product/B07J2Q4SWZ/ref=ppx_yo_dt_b_asin_title_o00_s00?ie=UTF8&amp;psc=1))
- ICY PCIe-Adapter für die NVMe ([Link](https://www.amazon.de/gp/product/B01N1YVYLE/ref=ppx_yo_dt_b_asin_title_o00_s00?ie=UTF8&amp;psc=1))
- Kühlkörper ICY Box ([Link](https://www.amazon.de/gp/product/B077MRDK16/ref=ppx_yo_dt_b_asin_title_o00_s00?ie=UTF8&amp;psc=1))

Zunächst wird die NVMe-SSD mit dem passiven Kühlkörper versehen und dann in die PCI-Karte eingesetzt.
![](__GHOST_URL__/content/images/2019/06/ausgepackt.JPG)oben: PCI-Adapter-Karte; rechts: NVMe SSD; links: Kühlkörper
Kühlkörper an SSD befestigen. Zum Schluss wird die SSD mit einer kleinen Schraube fixiert, fertig.

![](__GHOST_URL__/content/images/2019/06/cooler-ssd-1.JPG)

![](__GHOST_URL__/content/images/2019/06/k-hlor.JPG)

![](__GHOST_URL__/content/images/2019/06/k-hler-seitlich.JPG)

![](__GHOST_URL__/content/images/2019/06/nvme-cooler_-ounter_into_pcie.JPG)

![](__GHOST_URL__/content/images/2019/06/PCIE_Karte.JPG)

SSD mit Kühlköprer versehen und in PCI-Adapter einsetzen
Nun wird die PCI-Adapter-Karte in den obersten x4 / RAID Port des Mac Pro eingesetzt, sozusagen unter die Festplatten. Wen das bezüglich sich entwickelnder Abwärme stört, der kann auch den Port darunter, x4, nutzen.
![](__GHOST_URL__/content/images/2019/06/PCIE-x4-RAID.jpeg)geöffneter MacPro: PCI-Karte wird in x4/RAID eingesetzt
Das ganze sieht dann so aus. Nun kann die Seitenklappe des Macs wieder eingesetzt und der Rechner angeschlossen werden.
![](__GHOST_URL__/content/images/2019/06/pci-karte-eingebaut.JPG)
Wenn der Mac nun bootet und sein ursprüngliches System startet, sollte eine Meldung erscheinen, dass ein Datenträger nicht initialisiert werden kann. Das ist korrekt, denn die NVMe-SSD ist weder partitioniert noch formatiert. Öffnen wir nun das Festplattendienstprogramm, wird uns eine externe Platte mit 1 TB Speicher angezeigt, das ist unsere NVMe. 

Folgender Screenshot zeigt einen ersten kurzen Test den ich durchgeführt habe. Die Werte können sich sehen lassen, beschreiben sie doch das mögliche Maximum was PCIE 2.0 kann.
![](__GHOST_URL__/content/images/2019/06/NVME_Speedtest.png)Speedtest der NVMe SSD im x4 Port MacPro 2009
Diese können wir nun formatieren und als Speicher benutzen, oder wir installieren einfach macOS 10.14 Mojave auf ihr und nutzen Sie als Bootplatte, so wie ich das getan habe. Mein MacPro 2009 bootet von dieser NVMe dank Apple, die den MacPros ab 2009 ein Bootrom spendierte, was einen NVMe Boot unterstützt.

Leider soll ab der kommenden Version macOS 10.15 Catalina schluss mit der Unterstützung des MacPro sein, was ich sehr bedauere. Ich hoffe an dieser Stelle sehr, dass es Hackern wie dem Dosdude gelinkt, 10.15 doch installierbar zu machen.

So sieht die installierte Karte übrigens unter macOS 10.14 aus:
![](__GHOST_URL__/content/images/2019/06/Bildschirmfoto-2019-06-15-um-23.04.20.png)About this Mac: NVMExpress Karte mit Crucial M2.SSD
Das wars auch schon wieder, wir sind fertig und unser MacPro5,1 bootet von (s)einer NVMe-SSD!

---

[**Seltsam: Nachtrag**] Bei einer späteren Neuinstallation gab es bei mir eine Besonderheit. Ich wollte einen *CleanInstall* durchführen und habe den Mojave-Installer vom USB-Stick gebootet, wie man das eben so macht. Soweit nicht ungewöhnlich. Das lief auch alles ganz unproblematisch durch, allerdings konnte ich das System nicht installieren, weil meine Grafikkarte nicht Metal-Komatibel ist. Der Fehler bezog sich explizit auf meine Grafikkarte. Ich erhielt im Installer eine Fehlermeldung die darauf hin wies. Ich betreibe in dem MacPro jedoch eine **nVidia Geforce 680 GTX Mac Edition** ([Link](__GHOST_URL__/wie-man-eine-pc-grafikkarte-fur-den-mac-um-flasht-efi-rom/)), diese ist explizit Metal-Kompatibel. Es läuft ja auch schon 10.14 auf meinem System was ebenfalls zwingend Metal voraussetzt. Ich kann aus macOS heraus eine Neuinstallation auf die NVMe-SSD durchführen, das ist kein Problem, das habe ich jetzt auch getan, aber ich kann es nicht vom USB-Stick im CleanInstall durchführen. Seltsam. Vielleicht weiß jemand, woran das liegen könnte? Neulich ging das noch.

---

### Links

- [MacRumors: PCIe M.2 NVMe on MacPro](https://forums.macrumors.com/threads/pcie-m-2-nvme-on-macpro.2030791/)
- [MacRumors: Boot OSX on an NVMe Card](https://forums.macrumors.com/threads/boot-osx-on-a-nvme-card.1967790/)
- [Beettech: The Ultimate Guide to Apple’s Proprietary SSDs](https://beetstech.com/blog/apple-proprietary-ssd-ultimate-guide-to-specs-and-upgrades) (notably no info directly to classic Mac Pros but a good overview of Mac NVMe)
- [Google Docs:Step by Step Guide NVMe firmware upgrade](https://docs.google.com/document/d/1WNkM9LuGPq1sArO9EedWBHYq14NU7m-mDBLAWWJipyM/)
- [MacRumors: Entire thread related to the 5.1 ROM hack for NVMe.](https://forums.macrumors.com/threads/mp51-0084-b00-rom-dump-request.2119496/)
- [MacRumors: Blade SSDs - NVMe & AHCI](https://forums.macrumors.com/threads/blade-ssds-nvme-ahci.2146725/)
- [MacRumors: MP5,1: Mojave 10.14.1 DP3 BootROM 140.0.0.0.0 has native NVMe support!!!](https://forums.macrumors.com/threads/mp5-1-mojave-10-14-1-dp3-bootrom-140-0-0-0-0-has-native-nvme-support.2132317/)
- [Post with instructions (and download URL) to Bios](https://forums.macrumors.com/threads/mp5-1-mojave-10-14-1-dp3-bootrom-140-0-0-0-0-has-native-nvme-support.2132317/page-63#post-26635969)
- [Install Instructions (with pictures)](https://forums.macrumors.com/threads/mp5-1-mojave-10-14-1-dp3-bootrom-140-0-0-0-0-has-native-nvme-support.2132317/page-63#post-26636147)
