---
title: Upgrading to NVMe SSD in MacPro2013 aka MacPro6,1 Trashcan
slug: upgrading-to-nvme-ssd-in-macpro2013-aka-macpro6-1-trashcan
date_published: 2020-08-02T21:45:00.000Z
date_updated: 2020-08-05T13:10:26.000Z
tags: nvme ssd, macpro 2013, macpro6,1, trashcan, fix.it, anleitung, how to, howto, update
---

Wir ihr wisst, ist mein **MacPro** nur mit einer *256 GB SSD* ab Werk ausgestattet, was auf Dauer doch ziemlich wenig ist. Auch und vor allem, wenn man nebenbei zusätzlich *Windows* und/oder *Linux* installieren möchte. Zum Glück hat Apple das Upgrade des internen Festspeichers definitiv mit eingeplant, denn die SSD ist sehr gut zu erreichen und der Austausch dauert keine 10 Minuten, inklusive aller Kabel die wieder angeschlossen werden müssen.
![geöffneter MacPro6,1 mit sichtbarer Apple SSD (C) thahipster.de](__GHOST_URL__/content/images/2020/08/MacPro6-1_open-1.jpg)geöffneter MacPro6,1 mit sichtbarer Apple SSD (C) thahipster.de
Allerdings hat uns Apple doch ein paar Fallen gestellt und die erste und größte ist die, dass Apple seine SSDs prorpiertär, das heißt in einem eigenen Format, herstellt und man keine schnelleren und erschwinglicheren NVMe-SSDs einbauen kann. Man musste also auf Apples eigene, sündhaft teure Lösungen (Samsung-Speicher) zurück greifen oder sich über die speziellen Drittanbieter versorgen. Alles nicht sonderlich günstig. *Zumindest bis neulich…* denn der Anschluss ist pinkompatibel und kann mit einem simplen Adapter versehen werden. Und schwupps, passen nun auch NVMe-SSDs in den MacPro2013. Und genau das habe ich getan. Neben dem Umstand, dass diese SSDs erheblich günstiger als Apples eigene Teile sind, sind sie auch erheblich schneller. Folgende GEschwindigkeit erreicht meine Apple-SSD:
![AJA SSD Test auf Apple SSD in MacPro6,1 (C) thahipster.de](__GHOST_URL__/content/images/2020/08/Bildschirmfoto-2020-08-02-um-10.33.53.png)AJA SSD Test auf Apple SSD in MacPro6,1 (C) thahipster.de
### Upgrading NVMe SSD in MacPro6,1

#### Vorbereitung

Zunächst einmal führen wir ein Backup durch, denn wir bauen den einzigen Festspeicher aus, wir kommen später also nicht mehr so einfach an die Daten die darauf lagern. 

Dann erstellen wir uns einen *bootfähigen USB-Stick* ([Link](https://support.apple.com/de-de/HT201372)), mit dem wir Catalina installieren können. Das ganze funktioniert auch mit [Mojave](https://support.apple.com/de-de/HT201372) oder [High Sierra](https://support.apple.com/de-de/HT201372). Denn nach Einbau der neuen SSD ist das System leer und der Mac wird nur ein Fragezeichen anzeigen, keine System gefunden.

ACHTUNG. ANLEITUNG AUF EIGENE GEFAHR. Wir übernehmen keine Haftung.

#### Welche NVMe SSD, welcher Adapter, was noch?

Ich habe mir folgende Teile bestellt, die mehrfach als gut funktionierend bestätigt worden sind. Für die einzige Schraube die wir zum Ausbaue der SSD lösen müssen, benötigen wir einen 8er Torx, T8H.

Folgende drei Teile* habe ich mir für das Upgrade gekauft:

- Sabrent Rocket Q 1TB NVMe PCIe M.2 2280 Interne Hochleistungs-Solid-State SSD (SB-RKTQ-1TB) ([Link](https://www.amazon.de/gp/product/B07ZZYWTBP/ref=ppx_yo_dt_b_asin_title_o01_s00?ie=UTF8&amp;psc=1))
- QNINE M.2 NVME SSD Adapter Karte für Upgrade MacBook Pro (Retina Late 2013 - Mid 2015) und MacBook Air (Mid 2013-2017) ([Link](https://www.amazon.de/gp/product/B07S9Q6TCN/ref=ppx_yo_dt_b_asin_title_o01_s00?ie=UTF8&amp;psc=1))
- ICY BOX Flacher M.2 Kühler mit 5 mm Bauhöhe für M.2 SSD (2280), Aluminium, 2x Silikon Wärmeleitpad, selbstklebend, passiv, Schwarz ([Link](https://www.amazon.de/gp/product/B0799CS5VR/ref=ppx_yo_dt_b_asin_title_o00_s00?ie=UTF8&amp;psc=1))

* Nein, das sind keine Affiliate Links sondern lediglich Beispiele, was ich mir angeschafft habe, um den Nachbau zu erleichtern.
#### Sabrent 1 TB SSD
![Sabrent 1 TB M.2 NVMe SSD (C) thahipster.de](__GHOST_URL__/content/images/2020/08/Sabrent_SSD.jpg)Sabrent 1 TB M.2 NVMe SSD (C) thahipster.de
#### Apple-NVMe-Adapter

![](__GHOST_URL__/content/images/2020/08/qnine_adapter-1.jpg)

![](__GHOST_URL__/content/images/2020/08/qnine_back.jpg)

![](__GHOST_URL__/content/images/2020/08/qnine_front.jpg)

QNine Apple <--> NVMe SSD adapter for Sabrent 1 TB (C) thahipster.de
Der Adapter und die Sabrent SSD sind zusammen genau so lang, wie es die Apple-SSD ist. Somit passt sie plug'n'play perfekt in den MacPro6,1, es gibt hier keinerlei Schwierigkeiten. Man steckt die Sabrent in den Adapter und setzt beides später in den MacPro ein. 

![](__GHOST_URL__/content/images/2020/08/Sabrent_SSD-1.jpg)

![](__GHOST_URL__/content/images/2020/08/sabrent2.jpg)

![](__GHOST_URL__/content/images/2020/08/sabrent1.jpg)

![](__GHOST_URL__/content/images/2020/08/sabrent_qnine_near.jpg)

Sabrent SSD mit QNine NVMe Adapter (C) thahipster.de
Jetzt ist es Zeit die alte SSD aus dem MacPro auszubauen. Dazu benötigen wir einen **Torx T8H** Schraubendreher und weiter nichts. Die SSD ist das lange schwarze Teil, darauf sitzt ein fester Kühlkörper. 
![Original Apple SSD in MacPro6,1 (C) thahipster.de](__GHOST_URL__/content/images/2020/08/macpro_oldssd.jpg)Original Apple SSD in MacPro6,1 (C) thahipster.de![MacPro6,1 SSD mit Torx T8H Schraubendreher (C) thahipster.de](__GHOST_URL__/content/images/2020/08/ssd_torx.jpg)MacPro6,1 SSD mit Torx T8H Schraubendreher (C) thahipster.de![Beide SSD neben einander, rechts Apple SSD, links Sabrent mit QNine Adapter (C) thahipster.de](__GHOST_URL__/content/images/2020/08/ssd_nvme_ssd.jpg)Beide SSD neben einander, rechts Apple SSD, links Sabrent mit QNine Adapter (C) thahipster.de
So zusammen gebaut wird die Sabrent SSD also in den MacPro eingesetzt. Zuvor habe ich die Apple SSD ausgebaut. Das ganze sieht dann folgendermaßen aus:

![](__GHOST_URL__/content/images/2020/08/sabrent_macpro1.jpg)

![](__GHOST_URL__/content/images/2020/08/sabrent_macpro2.jpg)

![](__GHOST_URL__/content/images/2020/08/sabrent_macpro3.jpg)

![](__GHOST_URL__/content/images/2020/08/sabrent_macpro5.jpg)

Die SSD sitzt samt Adapter perfekt im MacPro6,1 (C) thahipster.de
So sieht das Endprodukt aus. Das wars eigentlich auch schon wieder, außer natürlich dem Kühlkörper, der hier auf den Bildern noch nicht verbaut ist. Nachdem ihr die Schraube fest gezogen habt könnt ihr das Gehäuse wieder zusammen setzen, Monitor und Strom anschließen und einschalten. Lasst all eure externen Festplatten und andere Peripherie noch weg, das ist für eine Neuinstallation meist besser. 

Nach dem ersten Einschalten sollte das Apple-Fragezeichen-Symbol angezeigt werden, da kein System gefunden wird. Jetzt stecken wir den zuvor erstellten USB-Stick an, der Mac sollte automatisch booten und starten dann das **Festplatten-Dienstprogramm**. Damit formatieren wir die Sabrent SSD auf das neue **Apple File System (APFS)** und starten den Installer für Catalina. Die Installation benötigt etwas Zeit.

Nach der Installation stellen wir unser TimeMachine Backup wieder her und haben fortan einen schnellen NVMe-SSD-Speicher mit unserem bisherigen System. Super cool.

*Das wars auch schon wieder, bis bald.*

---

Ach so, uns interessiert natürlich die Geschwindigkeit der NVMe SSD. Wie wir sehen können, hat sich die Schreibgeschwindigkeit nahezu verdoppelt. Da der Mac Pro Late 2013 mittlerweile auch schon einige Jahre auf dem Buckel hat ist der SSD-Steckplatz lediglich mit **PCIe 2.0 x 4** angebunden. Das bedeutet, dass der maximale Datendurchsatz auf 1500MB/s beschränkt ist, mehr ist physikalisch nicht möglich und stellt bei mir also fast das absolute Maximum dar, was über den Anschluss überhaupt möglich ist. **Wow**!
![Sabrent 1 TB NVMe SSD in MacPro6,1 (C) thahipster.de](__GHOST_URL__/content/images/2020/08/Bildschirmfoto-2020-08-02-um-14.15.46.png)Sabrent 1 TB NVMe SSD in MacPro6,1 (C) thahipster.de
---

[**UPDATE**] Ich wollte noch kurz die Bilder mit dem Kühlkörper nachreichen, damit es vollständig ist. 

![](__GHOST_URL__/content/images/2020/08/IMG_1741.jpeg)

![](__GHOST_URL__/content/images/2020/08/IMG_1742.jpeg)

![](__GHOST_URL__/content/images/2020/08/IMG_1743.jpeg)

![](__GHOST_URL__/content/images/2020/08/IMG_1744.jpeg)

![](__GHOST_URL__/content/images/2020/08/IMG_1745.jpeg)

ICY Box 6€ Kühlkörper mit Befestigungsgummis und Leitpad. Besonders flach für den Einbau im MacPro6,1
So sieht das einzeln aus:
![](__GHOST_URL__/content/images/2020/08/IMG_1741-1.jpeg)![](__GHOST_URL__/content/images/2020/08/IMG_1742-1.jpeg)![](__GHOST_URL__/content/images/2020/08/IMG_1743-1.jpeg)![](__GHOST_URL__/content/images/2020/08/IMG_1744-1.jpeg)![](__GHOST_URL__/content/images/2020/08/IMG_1745-1.jpeg)![1 TB NVMe SSD mit Kühlkörper in MacPro6,1](__GHOST_URL__/content/images/2020/08/IMG_1746.jpeg)1 TB NVMe SSD mit Kühlkörper in MacPro6,1
---

#### Fragen und Antworten:

- [Jans Ultimate Upgrade Guide to Trashcan MacPro6,1 2013](__GHOST_URL__/ultimate-upgrade-guide-macpro6-1-aka-trashcan-2013/)
- [Windows 10 auf MacPro6,1 mit NVMe SSD installieren](__GHOST_URL__/windows-auf-dem-macpro6-1-mit-nvme-ssd-installieren/)
