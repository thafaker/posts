---
title: Kernel 4.1.15 für Utilite Pro
slug: kernel-4-1-15-fur-utilite-pro
date_published: 2023-01-18T16:43:43.000Z
date_updated: 2024-08-21T15:25:30.000Z
tags: utilite pro, arm, linux, kernel 4.1.15, anleitung, how to, howto, updated
---

**UPDATE **2024-06-04 Ich habe diesen Artikel aktualisiert und vor allem alle defekten Links der Patches und Kernel Sources repariert.

---

Ich betreibe einen kleinen, sehr kleinen ARM-basierten Linux Server. Das Ding nutzt zum Booten "Das U-Boot" ([Link](https://de.wikipedia.org/wiki/Das_U-Boot)), einen speziellen Bootloader. Intern werkelt eine kleine 32-GB SSD und er verfügt über HDMI, 2 x LAN diverse USB und verbraucht unglaublich wenig Strom. Er nutzt einen Freescale Cortex-A9 (1,2 GHz, 4 Kerne) und 2 GB Ram. Perfekt und immer noch genug für einen Linux Server ohne GUI. *Eigentlich*. 

Der [Utilite Pro (archiviert)](http://web.archive.org/web/20230206201311/https://fitpc.com/shop/product/121259) genannte Industriecomputer wurde ursprünglich mit einem Ubuntu 12.04 ausgeliefert. Auf solch spezieller Hardware läuft natürich kein Mainline-Kernel und so ist ein Update schwierig. Es ist unmöglich einfach ein Ubuntu zu aktualisieren, eigentlich ist es sogar schon nicht so einfach überhaupt ein System auf die Kiste zu kriegen, wir arbeiten auf völlig anderer Architektur. Auch muss man sich mit einem RS232 Serial Cable verbinden, braucht noch einen USB-RS232 Adapter (oder einen sehr alten Client) und eine Terminal-Software, um überhaupt etwas sehen zu können. 

*Es ist schwierig*. Allerdings habe ich es geschafft das System auf ein Ubuntu 14.04 zu aktualsieren um dann festzustellen, dass damit der ausgelieferte Kernel 3.0.X nicht mehr funktioniert, weil ihm ein grundlegendes Feature fehlte. Für diese spezielle Hardware benötigt man neben den Kernel Sources und all den speziellen Patches die nur für diese Machine existieren, auch noch ein DTS und PTB File, quasi das Hardware-Layout. Das alles liegt mir nach langem Suchen vor und so versuche ich, einen "aktuelleren" (der aktuelle Longterm Kernel ist 5.15.88 und der aktuelle Stable ist 6.1.6) Kernel zu kompilieren, denn ein Upgrade auf Ubuntu 22.04 schlug fehl, weil mein damals kompiliereter Kernel 3.1.X abermals wichtige Feaures missen lässt, die nun aber mandatory sind damit Apache etc. pp. überhaupt noch funktioneren. Es ist zum Verrücktwerden.

Ich muss also einen Kernel 4.1 kompilieren. 4.1.15 ist das letzte mit den Patches etc. kompatible Gespann, was ich auf GIT finden konnte. Jetzt möchte ich aufschreiben, was ich getan habe - und ob es überhaupt funktioniert.

Grundlage ist mein Utilite Pro mit Ubuntu 20.04.05, einem selbst kompilierten Kernel 3.1 und dem Willen, einen modernen Kernel zu bauen. Wenigstens ein bisschen moderne, damit das Utilite auch noch mit Ubuntu 22.04 läuft, dem aktuellen LTS. 

Beachtet: wir arbeiten auf dem Utilite Pro auf dem ein aktuelles Linux läuft und wollen hier einen neuen alten Kernel kompilieren. Das heißt wir kompilieren auf ARM und brauchen so auch ARM Software, die APT Quellen etc. sind also Ports, nur falls ihr euch später wundert.

## Ressourcen

- **Die Kernel-Sources**: [https://github.com/varigit/linux-2.6-imx](https://github.com/varigit/linux-2.6-imx) // und hier als [ZIP](http://thafaker.crabdance.com/files/utilite/linux-2.6-imx-imx-rel_imx_4.1.15_1.1.0_ga-var02.zip)
- **Kernel Patches**: [Alle Patches in einer Datei](http://thafaker.crabdance.com/ftp/utilite/linux-4.1.15-cm-fx6-8.0.patch) // [Die Patches einzeln als ZIP](http://thafaker.crabdance.com/ftp/utilite/patches.zip)

[

linux-4.1.15-cm-fx6-8.0

Alle Patches in einer PATCH Datei

linux-4.1.15-cm-fx6-8.0.patch

158 KB

.a{fill:none;stroke:currentColor;stroke-linecap:round;stroke-linejoin:round;stroke-width:1.5px;}download-circle
](__GHOST_URL__/content/files/2024/06/linux-4.1.15-cm-fx6-8.0.patch)

[

linux-2.6-imx-imx-rel_imx_4.1.15_1.1.0_ga-var02

Die Kernel Sources als ZIP Datei von GitHUB

linux-2.6-imx-imx-rel_imx_4.1.15_1.1.0_ga-var02.zip

156 MB

.a{fill:none;stroke:currentColor;stroke-linecap:round;stroke-linejoin:round;stroke-width:1.5px;}download-circle
](__GHOST_URL__/content/files/2024/06/linux-2.6-imx-imx-rel_imx_4.1.15_1.1.0_ga-var02.zip)

[

patches

Alle Patches als einzelne PATCH Files in einer ZIP

patches.zip

67 KB

.a{fill:none;stroke:currentColor;stroke-linecap:round;stroke-linejoin:round;stroke-width:1.5px;}download-circle
](__GHOST_URL__/content/files/2024/06/patches.zip)

## How To Anleitung

Um das Vorgehen kurz zu beschreiben: wir klonen uns das GIT Verzeichnis auf unser Linux. Dann applizieren wir alle Utilite Patches. Dann laden wir die Utilite Pro Config für den Kernel, damit der Kernel korrekt eingestellt ist. An dieser Stelle kann man natürlich weitere Änderungen am Kernel konfigurieren. Dann kompilieren wir den Kernel, die Module, installieren diese nebst Firmware etc., dann bauen wir unser zImage aus dem Device Tree Blob und letztendlich installieren wir den Kernel nach /boot.

1. Legt euch ein Arbeitsverzeichnis an, in welchem ihr kompilieren wollt. Wechselt in das Verzeichnis.
2. Ladet euch den Patch (oben unter Ressources) herunter. Speichert ihn in eurem Arbeitsverzeichnis oder nutzt wget: 
`wget`[`http://thafaker.crabdance.com/ftp/utilite/linux-4.1.15-cm-fx6-8.0.patch`](__GHOST_URL__/content/files/2024/06/linux-4.1.15-cm-fx6-8.0.patch)
3. Ladet euch den Kernel von Github in euer Arbeitsverzeichnis:
`git clone `[`https://github.com/varigit/linux-2.6-imx.git`](https://github.com/varigit/linux-2.6-imx.git)` kernel`
4. Wechselt in den herunter geladenen Kernel
`cd kernel`
5. Patcht aus dem Kernel Verzeichnis heraus:
`patch -p1 < ../linux-4.1.15-cm-fx6-8.0.patch`
Eventuell gibt es hier auch die ein oder andere Fehlermeldung. Die Patches waren ursprünglich für Kernel 3., aber grundsätzlich sollte das funktionieren.
6. Jetzt ist unser Kernel vorbereitet, um für das Utilite Pro kompiliert zu werden

Jedoch gibt es an dieser Stelle ein Problem: Kernel 4.1.15 ist ziemlich alt. Zum Zeitpunkt der Erstellung dieses Artikels nutzen die Distributionen gcc in Version 9 und höher. Der alte Kernel lässt sich nicht mit einem so neuen gcc kompilieren. Wir brauchen also neben dem aktuellen GCC ein altes GCC nur für unseren Kernel 4.1. Garantiert funktionieren wird GCC-4.9; dieses lässt sich unter Ubuntu 18.04 und höher jedoch nicht mehr nachinstallieren. Wir müssen uns eines Tricks bedienen. Wir erweitern unseren Paketmanager APT um die alten Quellen von Ubuntu Xenial und installieren so **gcc-4.9**; nicht schön, aber immerhin funktioniert es. 

1. Folgendes in Terminal: 
`sudo nano /etc/apt/sources.list`
2. Tragt in der Datei dann folgende Paketquellen zusätzlich ein, unten drunter:
3. `deb `[`http://ports.ubuntu.com`](http://ports.ubuntu.com)`xenial main
deb `[`http://ports.ubuntu.com`](http://ports.ubuntu.com)`xenial universe`
4. Eventuell beschwert er sich, dass ihm die GPG-Keys fehlen und er die APT-Quellen nicht nutzen kann. Versucht folgenden Befehl:
`sudo apt-key adv --keyserver keyserver.ubuntu.com --recv-keys 40976EAF437D05B5`
sowie
`sudo apt-key adv --keyserver keyserver.ubuntu.com --recv-keys 3B4FE6ACC0B21F32`
damit sollte er die fehlenden GPG Schlüssel importieren und kann fortan die Quellen mit APT nutzen.
5. gefolgt von einem `sudo apt update`
6. Jetzt haben wir die alten Quellen eingelesen und können mit dem Befehl:
`sudo apt install gcc-4.9`
den GGC in Version 4.9 nur zur Kompilation des Kernels installieren.
7. Mit einem Befehl innerhalb des Kernel-Verzeichnisses können wir ihm von nun an sagen, dass wir anstelle von gcc-9 den alten gcc-4.9 nutzen möchten. Damit klappt die Kompilierung. Der Befehl der hinter make angehangen wird, lautet:
`CC=gcc-4.9` gefolgt vom eigentlich Befehl.

Wir befinden uns in unserem git geklonten oder als zip herunter geladenen kernel 4.1.15 Verzeichnis, es sollte `kernel` heißen.

1. Wir laden die **Defconfig** (Default Konfiguration) des Utilite Pro Linux-Kernels mit folgendem Befehl:

    make CC=gcc-4.9 cm_fx6_defconfig

Wenn wir an dieser Stelle Bock haben, können wir mit dem Befehl

    make menuconfig

ein entspanntes Kernel-Menü auf ncurses-Basis öffnen, um weitere Einstellungen sehr komfortabel vorzunehmen. Wir müssen aber nicht. Der Kernel läuft auch nur mit der Defconfig. 

2. Dann erstellen wir die Module und das Kernel-Image, mit dem Schalter -j4 sagen wir, dass er auf 4 Kernen kompilieren soll. Die Durchführung dauert auf dem Utilite Pro dennoch eine Ewigkeit. Ca. 70 Minuten für den Kernel und noch mal etwas mehr für die Module.

    make CC=gcc-4.9 -j4 zImage modules
    

3. Jetzt wird es Zeit, die kompilierten Module zu installieren. Alle Befehle als root.

    sudo make modules_install
    

4. Wir installieren die Firmwares (Es kann sein dass es die Firmware im Kernel 4.1 nicht mehr gibt, Firmwares werden über die Distributionen verteilt, dann wird make hier einen Fehler liefern, das ist in Ordnung):

    sudo make firmware_install
    

5. Wir installieren die Header:

    sudo make headers_install

6. Jetzt bauen wir den Device Tree Blob. Ursprünglich beinhaltete das Kernelimage auch die Beschreibung der vorhandenen Hardware. Das ist unflexibel und deshalb wurde diese Beschreibung in eine externe Datei gepackt. Bei ARM Devices ist das fast immer nötig. Das hat zudem den grossen Vorteil, dass auch U-Boot die gleiche Information über die Hardware nutzen kann.

    make CC=gcc-4.9 imx6q-sbc-fx6m.dtb imx6dl-sbc-fx6m.dtb

Der erste Device Tree Blop (dtb) `imx6q-sbc-fx6m.dtb` ist für den Utilite Pro, die zweite `imx6dl-sbc-fx6m.dtb` für den normalen Uilite, jenach dem, welchen ihr nutzt.

7. Jetzt packen wir das Kenel zImage und den DTB zusammen und bauen daraus ein einzelnes File, welches unter `/tmp` landet (wir befinden uns noch immer im Kernel-Verzeichnis):

    cat arch/arm/boot/zImage arch/arm/boot/dts/imx6q-sbc-fx6m.dtb > /tmp/zImage-cm-fx6

zImage und DTB für den Utilite Pro

Das wars, wir sind fertig. Jetzt kopieren wir das zImage und das DTB File in unsere Boot-Partition. Das Kernel-Image muss folgenden Namen haben: 
* `zImage-cm-fx6`
Das DTB muss folgenden Namen haben:
* `cm-fx6.dtb`
![Utilite Pro mit 4.1.15 Kernel zImage und DTB](__GHOST_URL__/content/images/2023/01/zImage_und_DTB.png)Utilite Pro mit 4.1.15 Kernel zImage und DTB
Nach einem Reboot startet euer Utilite mit dem neuen Kernel. Herzlichen Glückwunsch dazu.

### Ressources
[

Installing Ubuntu 14.04 on the utilite computer from scratch · umiddelb/armhf Wiki

interesting stuff about arm devices (Utilite, SolidRun, Odroid) - Installing Ubuntu 14.04 on the utilite computer from scratch · umiddelb/armhf Wiki

![](https://github.com/fluidicon.png)GitHubumiddelb

![](https://opengraph.githubassets.com/b858bb9577a493deeb3424e30362891a4b5174b09af7412d59fe9c6bd33eb3af/umiddelb/armhf)
](https://github.com/umiddelb/armhf/wiki/Installing-Ubuntu-14.04-on-the-utilite-computer-from-scratch)[

GitHub - varigit/linux-2.6-imx: Variscite public linux-2.6-imx.git

Variscite public linux-2.6-imx.git. Contribute to varigit/linux-2.6-imx development by creating an account on GitHub.

![](https://github.com/fluidicon.png)GitHubvarigit

![](https://opengraph.githubassets.com/03de52ddec706006b087324497960b2643d64bb57fcf7178244da3b45d158a3e/varigit/linux-2.6-imx)
](https://github.com/varigit/linux-2.6-imx)
