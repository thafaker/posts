---
title: Ultimate Powermac G5 Guide
slug: ultimate-powermac-g5-guide
date_published: 2025-03-14T21:45:33.000Z
date_updated: 2025-05-27T13:55:44.000Z
tags: Powermac G5, powermac, Power Mac G5
---

Ich kam neulich auf die Idee, mich mal wieder mit alten Macs zu beschäftigen. Und damit meine ich nicht classic Mac OS 9 Macs wie meinen iMac G3, sondern eher die letzten der PowerPC Generation. Ich hatte neulich schon mal über den [PowerPC 970 Prozessor geschrieben](__GHOST_URL__/wie-gut-war-der-powerpc-970-prozessor-wirklich-ein-historischer-blick/), wie er historisch im Vergleich gewirkt hat und dabei Lust bekommen, mir einen Powermac G5 zuzulegen. Ein Apple Cinema HD 23" Display (damaliger [Testbericht](https://www.zdnet.de/39126546/augenweide-apple-cinema-hd-display-23-zoll/)) habe ich noch und das passt perfekt zum Powermac G5. *Gesagt*. **Getan**. Und nun besitze ich einen Powermac G5 (Powermac11,2 ([Link](https://everymac.com/ultimate-mac-lookup/?search_keywords=PowerMac11,2))) mit *Dual Core PowerPC 970* Prozessor und *2 GHz*.

💡

**Hinweis**
Alles was ich zum Thema Powermac G5, PowerPC und Linux schreibe, könnt ihr drüber auf Apfelhammer.de nachlesen. Dort habe ich das jetzt verortet. [**https://apfelhammer.de** (archiviert)](http://web.archive.org/web/20210419155445/http://apfelhammer.de/)

![Apple Cinema HD Display auf Holztisch mit Apple Keyboard und Kopfhörer sowie weißen iPod](__GHOST_URL__/content/images/2024/11/Apple_Cinema_display_aluminum-2004-07-23.jpg)Apple Cinema HD Display (C) [CC-BY-SA 2.0](https://commons.wikimedia.org/wiki/File:Apple_Cinema_display_aluminum-2004-07-23.jpg)
Die anderen G5 verfügten über entweder eine Dual CPU Konfigurationen (es gab auch einen 600 MHz Frontsidebus 1,8 GHz Single) und manchmal gab es sie mit herkömmlichem 32-Bit PCI (und AGP Steckplatz) oder PCI-X (64 Bit), mein Powermac der letzten Iteration jedoch verfügt über PCI-Express Steckplätze ([Spezifikation 1.0](https://de.wikipedia.org/wiki/PCI_Express)) und lässt sich deshalb in gewisser Weise aufrüsten, was mich sehr interessiert. Wir sprechen hier immerhin über einen Computer aus dem Jahr 2004. Und von einer Prozessor-Architektur, der Apple schon sehr lang den Rücken gekehrt hat und die nurmehr noch in Servern von IBM Verwendung fand. Und überhaupt.

*Was will ich damit*? Ich möchte spielen! *Ganz klar*. Es ist ein kleines Hobby-Projekt. Ich mag alte Computer. Das reicht zu Geräten der 80er Jahre zurück. Und der Powermac G5 ist ein *impressive Monster*. Ich hatte zunächst überlegt, ob es sich lohnt den legendären wassergekühlten Quad Core (2 x PPC 970MP CPUs mit 2 Cores) Powermac G5 zu suchen, aber der ist erstens sehr rar, zweitens gibt es fast immer Probleme mit der Flüssigkeitskühlung (Leckage) und drittens ist er extrem laut - sodass mir schnell die Lust daran vergehen würde. Und so ist der 2 GHz völlig in Ordnung, der 2,3 GHz ist nämlich recht selten.
![Powermac G5 Dual Core PPC 970, geöffnet](__GHOST_URL__/content/images/2024/11/ppc_g5_mac_dc_open.png)Powermac G5 Dual Core PPC 970, geöffnet
Der Powermac kann auf **16 GB Ram** aufgerüstet werden, was enorm für seine Zeit ist. Denkbar ist auch eine **NVME-SSD** im PCIE 4x Steckplatz was schier unfassbar ist, mit einem Datendurchsatz von 700 MB pro Sekunde zu arbeiten und natürlich das Upgrade der Grafikkarte auf eine **NVIDIA Geforce 7800 GTX** 512 MB, die man selbst auf Mac-OpenFirmware flashen kann. 

Alles das möchte ich gern  betreiben und beschreiben. *And so it goes.*

---

## Ultima Powermac G5 Upgrade Guide

1. Upgrade to NVME SSD 512 GB / 1 TB
2. Upgrade Graphics Card
3. Upgrade RAM to Maximum
4. Ressources
5. Files

---

### Vorwort

Es gab im Laufe der Zeit verschiedene Powermac G5 Modelle, die allesamt im legendären Käsereibe-Gehäuse steckten, sich aber wie beim MacPro Nachfolger teils erheblich unterschieden:

- Power Mac G5 (PCI) - Modell M9031LL/A (Juni 2003)
- Power Mac G5 (PCI-X) - Modell M9032LL/A (2004)
- Power Mac G5 (Early 2005) - Modell PowerMac7,3
- Power Mac G5 (Late 2005) - Modell PowerMac11,2

Ich besitze einen PowerMac11,2, die letzte (und modernste) Variante. In Sachen Geschwindigkeit gab es keine riesigen Unterschiede. der Powermac G5 mit Dual Prozessor 2 GHz ist in etwas so schnell wie der Late 2005 mit 2 GHz Dual Core CPU.

### 1. Upgrade to NVMe-SSD 512 GB

**Nur **der Powermac G5 *Late 2005* (11,2) besitzt PCI-Express Steckplätze und ist somit in der Lage, neben einer x16 Grafikkarte auch andere PCIE Karten aufzunehmen. Möglich ist eine USB 3.2/-C Steckkarte oder eine NVMe-SSD mit 512GB oder 1 TB als Massenspeicher. Tatsächlich kann im Powermac G5 ein x4 NVMe-Adapter mit M.2 verbaut werden (PCIE Generation 1.0), der bis zu 460 MB/Sec Datenübertragung erreicht, was unfassbar schnell für einen 2005er Computer ist. Ich habe mich für folgendes Setup entschieden:

- 512 GB NVMe M.2 SSD, 512GB, PCIe 3x4 ([Amazon Link](https://www.amazon.de/gp/product/B0CPHTF13D/ref=ox_sc_act_title_1?smid=AHM9DWTS356WD&amp;psc=1)*)
- M.2 NVME auf PCIe 3.0 x4 Adapter mit Aluminium-Kühlkörper ([Amazon Link](https://www.amazon.de/GLOTRENDS-PA09-HS-NVMe-Adapter-Kühlkörper/dp/B07FN3YZ8P/ref=pd_bxgy_d_sccl_1/258-3948167-2267634?pd_rd_w=HIYuf&amp;content-id=amzn1.sym.5eda1a26-aae5-46aa-95ea-198f43dc011e&amp;pf_rd_p=5eda1a26-aae5-46aa-95ea-198f43dc011e&amp;pf_rd_r=H6RTD8F2EVZW9PH0VFTP&amp;pd_rd_wg=RAtB4&amp;pd_rd_r=92cda931-9276-4223-b024-fe46048d988a&amp;pd_rd_i=B07FN3YZ8P&amp;psc=1)*)

Ich habe das bisher nur unter Linux getestet, dort funktioniert die "Festplatte" ohne Probleme. Wie sich das unter Mac OS X 10.4 / 10.5 verhält, werde ich nachreichen. Wenn das Laufwerk formatiert ist, kann man es also ganz normal, aber unglaublich schnell, benutzen 😄
* We do not use affiliate links!
#### 1.2 Boot from NVMe-SSD
![Foto einer normalen, drehenden Festplatte. Es ist eine IDE-HDD.](__GHOST_URL__/content/images/2024/11/hdd.jpg)Foto einer normalen, drehenden Festplatte. Es ist eine IDE-HDD.
Leider kann der Power Mac G5 **nicht** nativ von einer PCIE-NVMe booten, da die OpenFirmware diese Technologie nicht unterstützt. Auch beim MacPro wurde dies erst mit Firmware 144.0.0.0 [offiziell durch Apple](__GHOST_URL__/nvme-ssd-in-macpro4-1/) nachgerüstet. Eine NVMe-SSD kann zwar mit einem PCIE-Adapter im Power Mac G5 verwendet werden, jedoch nur als sekundärer Speicher.

Falls man eine SSD für das Betriebssystem verwenden möchte, ist es am besten, eine SATA-SSD über einen SATA-PCIe-Controller zu installieren. Diese Lösung bietet eine hohe Geschwindigkeit, und man kann von ihr booten, da sie mit der G5-Firmware kompatibel ist.

Für eine leistungsfähige Speicherlösung und eine beschleunigte Boot-Zeit die auch unter Mac OSX funktioniert, könnte man also Folgendes tun:

- **eine SATA-SSD** installieren (möglichst über eine PCIe-Karte mit SATA-Anschluss).
- **NVMe-SSD** (falls installiert) als sekundären Speicher für Daten und Programme, die hohe Lese- und Schreibraten benötigen – verwenden, das Betriebssystem muss von der SATA-SSD starten musst.

Falls du mit Linux experimentierst, gibt es Workarounds und Anpassungen, um die NVMe als Datenträger anzusprechen, aber für den Systemstart bleibt SATA die beste Option. Weiterhin denkbar wäre unter Linux, eine SATA-SSD für den GRUB/YABOOT Bootloader zu verwenden, der dann auf die NVME-SSD verweist. Das könnte klappen.

#### 1.3 Große Probleme mit normalen SATA SSDs

Ich habe den Powermac mit eine originalen drehenden Apple *gebrandeten* Festplatte erhalten, diese wollte ich aber aus Geräusch- und stromverbräuchlichen Gründen gegen eine SSD austauschen und holte kurzerhand eine günstige aktuelle 240 GB SSD über Amazon, irgendwas *No Name*. Und siehe da: der Installer von MacOS 10.5 erkannte die SSD nicht, dann doch, dann konnte ich installieren aber ich konnte niemals booten. Dann war die SSD wieder verschwunden. Die SSD selbst war in Ordnung, es ist offenbar die alte Firmware des Macs, der Controller oder irgendwas mit der Firmware der SSD, aber sie funktioniere nicht. 

Da ich aber gern ein echtes Mac OS X 10.5 und Linux für PPC auf dem Gerät haben wollte, sollte das schon funktionieren. Die SSD ist dann auch der Startpunkt, auf ihr befinden sich die Mac OS X Partition und Grub, sodass man von der SSD via Grub dann das Linux auf der NVMe-SSD booten kann. *Anysways*…

Ich organisierte mir dann richtig alte originale SATA I SSDs mit 128 GB aus der damaligen Zeit und versuchte es erneut. Von drei dieser SSDs funktionierte schließlich nur eine einzige dauerhaft und zufriedenstellen. Prinzipiell sind aber alle drei in Ordnung. Ich will mit diesem langen Text nur darauf hinweisen, dass ein Powermac G5 keineswegs einfach so mit einer SATA SSD zusammen arbeitet und es immer mal zu nicht lösbaren Konflikten kommen kann. Letztendlich hilft hier nur ausprobieren, oder bei einer echten, drehenden HDD zu bleiben.

### 2. Upgrade Graphics Card
![black fan device close-up photography](https://images.unsplash.com/photo-1555618568-bdf0a992c512?crop=entropy&amp;cs=tinysrgb&amp;fit=max&amp;fm=jpg&amp;ixid=M3wxMTc3M3wwfDF8c2VhcmNofDV8fGdyYXBoaWNzJTIwY2FyZHxlbnwwfHx8fDE3MzA5ODM3NzN8MA&amp;ixlib=rb-4.0.3&amp;q=80&amp;w=2000)Photo by [Christian Wiediger](https://unsplash.com/@christianw) / [Unsplash](https://unsplash.com/?utm_source=ghost&amp;utm_medium=referral&amp;utm_campaign=api-credit)
Wenn es um das Thema *Schnellste Grafik im Powermac* geht, müssen wir immer die Benuztung von Mac OS X von der von Linux unterscheiden. Unter Mac OS X benötigen wir eine Grafikkarte mit einem Mac OS X (respektive Open Firmware) kompatiblen BIOS, damit diese Grafikkarte korrekt funktioniert. Wenn ich Linux verwende, wird auch eine herkömmliche PC-Grafikkarte erkannt und kann verwendet werden. 

Es gibt nur eine handvoll von Treibern in Mac OS X 10.4 / 10.5, ich muss also dafür zwiwngend eine Grafikkarte aus der Zeit verwenden. Zu erwähnen sind hier die nVidia 7800 GTX oder die ATI Radeon X1900 Grafikkarten. Prinzipiell funktioniert jede Grafikkarte, die damals auch im Powermac ausgeliefert wurde.

Von der einen oder anderen Mac kompatiblen Grafikkarte wurde das Mac-Bios extrahiert und als ROM gepsichert und im Netz zum Download angeboten. Mit Software zum Flashen ist es möglich, dieses ROM wieder in eine kompatible Grafikkarte zu bringen. Das heißt bei weiterer Überlegung also, dass ich mir eine für den Mac prinzipiell kompatible Grafikkarte (wie die nVidia 7800 GTX) als PC-Version günstiger (weil viel häufiger vorhanden) kaufen kann, um sie dann selbst auf eine Mac-Version um zu flashen. Das funktioniert in der MacPro Intel Welt, das funktionierte davor schon in der Powermac G5 Welt. 

💡

Allerdings werden diese sehr alten Grafikkarten so oder so rar. Ich sollte mich jetzt darum kümmern, denn die Karten steigen von nun an nur noch im Preis, werden aber nicht mehr günstiger.

Bei der Wahl des richtigen Macintosh-kompatiblen BIOS ist die Größe des Video-Arbeitsspeichers zu beachten. Ich kann kein ROM einer 256 MB Version in meine 512 MB Grafikkarte flashen oder umgekehrt, auch wenn beide eine ATI Radeon 1900 oder eine Geforce 7800 GT(X) sind. 

Ich habe eine nVidia Geforce 7800 GTX mit 512 MB als PC-Version gekauft und diese mit folgendem BIOS-Rom auf Macintosh geflashed. 

#### Graphic Boards to flash and work with G5 (PCI-E)

- **nVidia 7800 GTX 512 MB** - soll einhellig die beste und schnellste Option für den Powermac G5 Late 2005
- **nVidia Quadro FX 4500** - ist das professionelle Ende der Fahnenstange für den Powermac G5 - es kursieren Gerüchte nur 4500er mit beidseitigem RAM könnten geflashed werden - das stimmt nicht. Man benötigt nur das richtige ROM für seine Variante. Alle Quadros sind kompatibel und können im G5 genutzt werden
- **ATI X 1900 XT** - etwas langsamer als die 7800 GTX

### 3. Upgrade RAM to Maximum

Hier ist eine Übersicht der maximalen RAM-Kapazitäten und -Module für die verschiedenen Power Mac G5 Modelle, damit man sich auf eBay und Co die richtigen Riegel besorgen kann:

#### Power Mac G5 (PCI) - Modell M9031LL/A (Juni 2003)

- **Prozessor:** Single 1,6 GHz oder 1,8 GHz; Dual 2,0 GHz
- **Maximaler RAM:** 4 GB
- **RAM-Steckplätze:** 4 (PC-2700 oder PC-3200 DDR SDRAM)
- **Module:** Bis zu 1 GB pro Modul

#### Power Mac G5 (PCI-X) - Modell M9032LL/A (2004)

- **Prozessor:** Dual 1,8 GHz oder 2,0 GHz
- **Maximaler RAM:** 8 GB
- **RAM-Steckplätze:** 8 (PC-3200 DDR SDRAM)
- **Module:** Bis zu 1 GB pro Modul

#### Power Mac G5 (Early 2005) - Modell PowerMac7,3

- **Prozessor:** Dual 2,3 GHz oder 2,7 GHz
- **Maximaler RAM:** 8 GB
- **RAM-Steckplätze:** 8 (PC-3200 DDR SDRAM)
- **Module:** Bis zu 1 GB pro Modul

#### Power Mac G5 (Late 2005) - Modell PowerMac11,2

- **Prozessor:** Dual-Core 2,0 GHz, 2,3 GHz oder Quad 2,5 GHz
- **Maximaler RAM:** 16 GB
- **RAM-Steckplätze:** 8 (PC2-4200 DDR2 SDRAM)
- **Module:** Bis zu 2 GB pro Modul

Diese Power Mac G5 Modelle sind unterschiedlich in ihrer RAM-Unterstützung, basierend auf ihrer internen Architektur und Prozessorvariante. Das spätere Modell PowerMac11,2 war das leistungsstärkste in der Serie, mit Unterstützung für mehr RAM und schnellerem DDR2 SDRAM.

---

### 4. Ressources
[

This Is Apfelhammer!

![](__GHOST_URL__/content/images/icon/logo_256x256.png)

![](__GHOST_URL__/content/images/thumbnail/herrmontag.JPG)
 (archiviert)](http://web.archive.org/web/20210419155445/http://apfelhammer.de/)[

Wie gut war der PowerPC 970 Prozessor wirklich? - Ein kleiner historischer Blick

Der PowerPC 970 Prozessor, der im Powermac G5 (the real original “Käsereibe”) in verschiedenen Inkarnationen eingesetzt wurde, war in seiner Zeit tatsächlich ein beeindruckendes Stück Technologie. Er basierte auf IBMs POWER4-Architektur und brachte einige der fortschrittlichsten Technologien der damaligen Zeit auf den Desktop. Hier sind einige wichtige Aspekte seiner Leistungsfähigkeit

![](__GHOST_URL__/content/images/icon/logo.png)thahipster.deHerr Montag

![](__GHOST_URL__/content/images/thumbnail/photo-1621768216002-5ac171876625)
](__GHOST_URL__/wie-gut-war-der-powerpc-970-prozessor-wirklich-ein-historischer-blick/)[

Power Macintosh G5 Dual Core (2.0) Specs (Late 2005, M9590LL/A, PowerMac11,2, A1117/A1177*, 2023): EveryMac.com

Technical specifications for the Power Macintosh G5 Dual Core (2.0). Dates sold, processor type, memory info, hard drive details, price and more.

![](__GHOST_URL__/content/images/icon/apple-touch-icon.png)Kyle Media LLC

![](__GHOST_URL__/content/images/thumbnail/everymac-logo-noshadow.gif)
](https://everymac.com/systems/apple/powermac_g5/specs/powermac_g5_dual_2.0.html)[

Mac OS X 10.5.8 with modern Browser

![](__GHOST_URL__/content/images/icon/logo_256x256-1.png)

![](__GHOST_URL__/content/images/thumbnail/herrmontag-1.JPG)
 (archiviert)](http://web.archive.org/web/20250327133503/https://apfelhammer.de/mac-os-x-1058-with-modern-browser.html)[

Augenweide: Apple Cinema HD Display (23 Zoll)

Apples Cinema HD-Display mit einer beeindruckenden Diagonalen von 23 Zoll ist sicherlich alles andere als preiswert und bietet dafür vergleichsweise wenige Extras, dennoch zieht es jeden bereits beim ersten Anblick in seinen Bann.

![](__GHOST_URL__/content/images/icon/apple-touch-icon-180x180.png)ZDNet.deZDNet.de Redaktion

![](__GHOST_URL__/content/images/thumbnail/zdnet-logo.png)
](https://www.zdnet.de/39126546/augenweide-apple-cinema-hd-display-23-zoll/)[

Im Test vor 15 Jahren: Die GeForce 7800 GTX 512 mit Nachbrenner

Die GeForce 7800 GTX 512 mit mehr Grafikspeicher und höheren Taktraten überzeugte mit brachialer Leistung und leiser Kühlung.

![](__GHOST_URL__/content/images/icon/favicon.svg)ComputerBaseRobert McHardy

![](__GHOST_URL__/content/images/thumbnail/article-1280x720.cfd78330.jpg)
](https://www.computerbase.de/2020-11/geforce-7800-gtx-512-test-rueckblick/)[

PowerMac G5 Quad “The New Blood Mod” - A guide to flushing, modifying and refilling the dual-pump cooling system.

Hi all, this is a guide to my personal modifications to the Apple PowerMac G5 Quad rev.2 “dual-pump Delphi”, pictured above. I will do my best to be thorough in my descriptions. Sadly I do not have pictures of my process in this version of the guide but I will be repeating this mod on another…

![](__GHOST_URL__/content/images/icon/68kmla-512.png)68kMLACircuitBored

![](__GHOST_URL__/content/images/thumbnail/6263.jpg)
](https://68kmla.org/bb/index.php?threads/powermac-g5-quad-the-new-blood-mod-a-guide-to-flushing-modifying-and-refilling-the-dual-pump-cooling-system.37474/)[

Snow Leopard on Unsupported PowerPC Macs

[ ©© Ltshears, Wikimedia Commons] A CLOUDED LEOPARD:
Mac OS X 10.6 Snow Leopard Developer Previews on PowerPC
WikiPost last updated: 11 April 2022 OVERVIEW We’re exploring how to run early builds of Snow Leopard on (later) G4 and G5 PowerPC Macs. This WikiPost outlines testing methods to…

![](__GHOST_URL__/content/images/icon/favicon.ico)MacRumors ForumsLarsvonhier

![](__GHOST_URL__/content/images/thumbnail/1280px-CloudedLeopard.jpg)
](https://forums.macrumors.com/threads/snow-leopard-on-unsupported-powerpc-macs.2232031/)
---

### 5. Files

[

nVStrap

nVStrap.zip

467 KB

.a{fill:none;stroke:currentColor;stroke-linecap:round;stroke-linejoin:round;stroke-width:1.5px;}download-circle
](__GHOST_URL__/content/files/2024/11/nVStrap.zip)

[

nVidia GeForce 7800 GTX 512 MB Version PowerPC

GeForce 7800GTX.zip

30 KB

.a{fill:none;stroke:currentColor;stroke-linecap:round;stroke-linejoin:round;stroke-width:1.5px;}download-circle
](__GHOST_URL__/content/files/2024/11/GeForce-7800GTX.zip)

[

ATI Radeon X1950XT 256MB Version PowerPC

X1950MAC.ROM.zip

17 KB

.a{fill:none;stroke:currentColor;stroke-linecap:round;stroke-linejoin:round;stroke-width:1.5px;}download-circle
](__GHOST_URL__/content/files/2024/11/X1950MAC.ROM.zip)

[

G5 Quadro FX 4500 Flash Tools (alle Varianten) 

MIrror: https://drive.google.com/file/d/1dtOsQECfPCax3j2Dp-5XuY56orua6M9L/view?pli=1

G5 Quadro FX 4500 Flash Tools.zip

939 KB

.a{fill:none;stroke:currentColor;stroke-linecap:round;stroke-linejoin:round;stroke-width:1.5px;}download-circle
](__GHOST_URL__/content/files/2024/11/G5-Quadro-FX-4500-Flash-Tools.zip)
