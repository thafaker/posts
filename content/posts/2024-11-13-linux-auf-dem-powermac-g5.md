---
title: Linux auf dem Powermac G5
slug: linux-auf-dem-powermac-g5
date_published: 2024-11-13T10:46:29.000Z
date_updated: 2025-07-25T20:35:01.000Z
tags: Power Mac G5, Powermac G5, linux
---

Mein geliebter Power Mac G5 ([alle Artikel](__GHOST_URL__/tag/powermac-g5/)) bereitet mir große Freude. Er verfügt über den 2 GHz Dual Core PowerPC 970MP Prozessor ([Everymac](https://everymac.com/systems/apple/powermac_g5/specs/powermac_g5_dual_2.0.html)) und mittlerweile eine SSD für das System. Weiterhin verfügt er über 4,5 GB-Ram. Auf der SSD ist Mac OS X 10.5 Leopard installiert und auf der zweiten SSD befindet sich nichts. Ich würde an dieser Stelle empfehlen, der Einfachheit halber, Linux auf eine zweite, leere Festplatte (SSD) zu installieren. Den Bootmanager (GRUB2 oder Yaboot) korrekt zum Laufen zu kriegen ist schon schwer genug, aber dass auf einer Platte die dem Apple Partitionsschema folgt, verschiedene HFS Geheimpartitionen aufweist und auch noch ein Linux booten soll, ist einfach zu aufwändig 😄

💡

Hi, alle meine Artikel zum **Powermac G5** finden sich nun auf einer eigenen Domain namens [apfelhammer.de (archiviert)](http://web.archive.org/web/20210419155445/http://apfelhammer.de/) - Viel Spaß.

![4 GB Ram for Power Mac G5](__GHOST_URL__/content/images/2024/11/ram_powermac.jpg)4 GB Ram for Powermac G5 (C) Herr Montag
## Linux

Der Power Mac G5 mit ordentlich RAM und einer SSD ist durchaus noch in der Lage, Programme zügig auszuführen. Man kann ihn also eigentlich noch ein bisschen produktiv einsetzen, denke ich. Allerdings ist das letzte Mac OS X für PowerPC Version 10.5, Leopard und bei aller Liebe, das ist seit 2009 obsolet. Es macht zwar Spaß damit herum zu spielen, Email geht, Web schon nicht mehr und SHH nur zu wenig verschlüsselten Servern (SSH1, Telnet diesdas) - aber ernsthaft ist das nicht mehr. 

Deshalb die Idee, ein aktuelles Linux zu installieren. Ein Linux für PowerPC. Aber der 970er Prozessor ist 20 Jahre alt und wird von vielen Linux Distributionen nicht mehr unterstützt. Unoffiziell aber z.B. durch Debian. Oder das großartige T2 von Rene Rebe. Auch gibt es noch ein Adélie genanntes Linux, was ich bisher nicht kannte. Adélie ist ein unabhängiges Libre-Betriebssystem, das auf dem Linux-Kernel und der Musl-Laufzeitbibliothek basiert.

Long Story short, TL;DR: **Ich empfehle Debian 12 Sid auf dem Powermac G5**.

### T2/SDE Linux

Ich habe zunächst das spannende T2/SDE ([Link](https://t2sde.org/)) Linux von *René Rebe* in seiner Inkarnation für PPC64 installiert, aber nach der Installation Probleme mit Grub2 bekommen. Die Installation selbst lief problemlos durch, auch die Partitionierung. Grub jedoch lud nur mit minimal bash-like Terminal und ein ls zeigte sehr seltsam anmutende Devices, offensichtlich werden die Festplatten und Partitionen nicht wie sonst üblich mit (hdX,Y) angesprochen. Es ist mir nicht gelungen meine Linux Boot Partition zu identifizieren um sie händisch zu booten. Ich muss hier noch etwas mehr Zeit investieren. 

Vielleicht kann mir [dieser kürzlich gefundene Link](https://github.com/masterzorag/G5_ppc64-linux?tab=readme-ov-file) dabei helfen.

- [https://dl.t2sde.org/binary/2024/t2-24.5-ppc6432-base-desktop-glibc-gcc-970.iso](https://dl.t2sde.org/binary/2024/t2-24.5-ppc6432-base-desktop-glibc-gcc-970.iso)

### Adelie Linux 

Adélie ist ein unabhängiges Libre-Betriebssystem, das auf dem Linux-Kernel und der Musl-Laufzeitbibliothek basiert. Es unterstützt explizit alte Hardware und so werden PowerPC Prozessoren bis zum 970er (der sogar in 64 Bit) unterstützt. Man kann verschiedene Desktops auswählen und am Ende erhält man eine bootfähige [Live-CD](https://www.adelielinux.org/download/), die einen grafischen Desktop lädt und den Powermac gut funktionierend benutzen lässt. Ich habe XFCE benutzt. Eingebaut ist auch ein Installer, der sich um alles kümmert und grafisch funkioniert. Allerdings habe ich auch hier das Problem, dass die Festplatte am Ende nicht bootfähig ist, Open Firmware diese gar nicht erkennt und somit gar kein Grub oder Yaboot geladen werden kann. Mit Sicherheit ist es hier wie mit T2, ich muss einfach schauen wie genau die Boot Paritition aussehen muss, welchem Schema die Partitionstabelle entsprechen muss, welcher Boot Record wichtig ist und dann sollte das eigentlich klappen - denn die Live CD funktioniert erstaunlich komplett und korrekt. Fühlt sich gut an 😄
[

Adélie Linux | Download

![](__GHOST_URL__/content/images/icon/gen_polyguin_color_favicon.ico)Download

![](__GHOST_URL__/content/images/thumbnail/gen_polylogo_black_mono_x54.png)
](https://www.adelielinux.org/download/)
### Debian 12 SID Unstable PPC 970 64 Bit

[**UPDATE**] Ich habe meinem Powermac eine 1TB NVMe M2 SSD für den 4x PCIE Steckplatz spendiert. Leider kann der Powermac, also OpenFirmware, nicht von NVMe booten. Das ist einfach zu neue Technik, es existieren keine Treiber. Allerdings habe ich darauf trotzdem meine existierende Debian 12 Installation emigriert und eine 64 GB Swap Partition eingerichtet und eingebunden. Nach ein bisschen hin und her habe ich es geschafft, meinem Grub2 zu sagen, welches auf der ursprünglichen SATA SSD verblieben ist, Linux von der NVMe zu booten. Mega yolo. Das ganze System fühlt sich so schnell wie ein aktueller Computer an. Ein echter **Leistungsboost**. *Just for fun*. Für die 80€ hätte ich wahrscheinlich auch einen kleinen neuen Computer kaufen können, der schneller ist. Aber ohne dem Spaß dabei. Grub2 für PowerPC ist immer noch mal anders, wegen Open Firmware diesdas. Kurz zum Verständnis: *to be continued…*

[**Original**] Tatsächlich konnte ich in mehreren Versuchen keine Installation durchführen, oft konnte der Partitionierer nicht geladen werden oder andere Module schlugen ohne ersichtlichen Grund fehl. Verbraut war eine normal drehende 1 TB Sata HDD. Erst nachdem ich eine alte SATA I SSD mit 128 GB einsetzte, lief der Debian 12 Installter vollständig durch. Er legte User an, vergab Passwörter, konnte das Netzwerk einbinden, paritionierte und installierte. Nach dem Reboot konnte ich Linux via Grub starten:

    thahipster@powermac:~$ uname -a
    Linux powermac 6.11.7-powerpc64 #1 SMP Debian 6.11.7-1 (2024-11-09) ppc64 GNU/Linux

![Screenshot of neofetch Debian 12 SID Mate Desktop on Powermac G5 (C) Herr Montag](__GHOST_URL__/content/images/2024/11/neofetch_powermac_g5.png)Screenshot of neofetch Debian 12 SID Mate Desktop on Powermac G5 (C) Herr Montag
Dann allerdings scheitert der Start der grafischen Benutzeroberfläche, was an einem fehlenden NVIDIA Treiber liegt, in meinem Powermac werkelt die NVIDIA Geforce 6600 GS. Über folgenden Befehl kann man den Treiber nachinstallieren, danach starten GDM und X11.

    # freien nVidia Treiber Nouveau installieren
    sudo apt-get install xserver-xorg-video-nouveau

![Debian 12 SID bootet into GDM on Power Mac G5](__GHOST_URL__/content/images/2024/11/powermac_g5_gdm_greeter.jpg)Debian 12 SID bootet into GDM on Power Mac G5 (C) Herr Montag
Allerdings sorgt die 3D-Beschleungigung für Probleme, sodass nach dem Login in die grafische Oberfläche Artefakte und Fehler eine Arbeit damit verhindern. Die Lösung ist hier, 3D zu deaktivieren. Dadurch wird alles etwas behäbiger, aber es funktioniert immerhin:

    # 3D-Beschleunigung deaktivieren. Zunächst Config-File anlegen:
    sudo nano /etc/X11/xorg.conf.d/20-nouveau.conf
    
    # Dann folgenden Inhalt einfügen
    
    Section "Device"
       Identifier  "NvidiaGraphics"
       Driver      "nouveau"
       Option      "NoAccel"  "1"
    EndSection
    
    # Datei speichern, Power Mac neustarten - läuft

Nun läuft X11 bei mir problemlos und der Mac ist erstaunlich benutzbar, allerdings startet der Firefox nicht. Es gibt einen Speicherzugriffsfehler. *Was tun*? Selber kompilieren! Das ganze sieht so aus und lastet den Rechner auch ordentlich aus, ich weiß allerdings nicht ob das am Ende funktioniert. Es wird lange dauern.
![Putty Connection to Powermac G5, compiling Firefox for PPC970](__GHOST_URL__/content/images/2024/11/compile_ff.JPG)Putty Connection to Powermac G5, compiling Firefox for PPC970
- [https://cdimage.debian.org/cdimage/ports/12.0/ppc64/debian-12.0.0-ppc64-NETINST-1.iso](https://cdimage.debian.org/cdimage/ports/12.0/ppc64/debian-12.0.0-ppc64-NETINST-1.iso)

---

### Ressources

- **T2/SDE**: [https://dl.t2sde.org/binary/2024/t2-24.5-ppc6432-base-desktop-glibc-gcc-970.iso](https://dl.t2sde.org/binary/2024/t2-24.5-ppc6432-base-desktop-glibc-gcc-970.iso)
- **Debian 12**: [https://cdimage.debian.org/cdimage/ports/12.0/ppc64/debian-12.0.0-ppc64-NETINST-1.iso](https://cdimage.debian.org/cdimage/ports/12.0/ppc64/debian-12.0.0-ppc64-NETINST-1.iso)

[

Adélie Linux | Download

![](__GHOST_URL__/content/images/icon/gen_polyguin_color_favicon-1.ico)Download

![](__GHOST_URL__/content/images/thumbnail/gen_polylogo_black_mono_x54-1.png)
](https://www.adelielinux.org/download/)[

Adélie Linux · GitLab

The Adélie Linux project. Please visit www.adelielinux.org for more information. JS-free GitWeb.

![](__GHOST_URL__/content/images/icon/apple-touch-icon-b049d4bc0dd9626f31db825d61880737befc7835982586d015bded10b4435460.png)GitLab

![](__GHOST_URL__/content/images/thumbnail/gen_polyguin_color_gitlab.png)
](https://git.adelielinux.org/adelie)[

Power Macintosh G5 Dual Core (2.0) Specs (Late 2005, M9590LL/A, PowerMac11,2, A1117/A1177*, 2023): EveryMac.com

Technical specifications for the Power Macintosh G5 Dual Core (2.0). Dates sold, processor type, memory info, hard drive details, price and more.

![](__GHOST_URL__/content/images/icon/apple-touch-icon-1.png)Kyle Media LLC

![](__GHOST_URL__/content/images/thumbnail/everymac-logo-noshadow-1.gif)
](https://everymac.com/systems/apple/powermac_g5/specs/powermac_g5_dual_2.0.html)[

GitHub - masterzorag/G5_ppc64-linux: Linux on the PowerMac G5

Linux on the PowerMac G5. Contribute to masterzorag/G5_ppc64-linux development by creating an account on GitHub.

![](__GHOST_URL__/content/images/icon/pinned-octocat-093da3e6fa40.svg)GitHubmasterzorag

![](__GHOST_URL__/content/images/thumbnail/G5_ppc64-linux)
](https://github.com/masterzorag/G5_ppc64-linux?tab=readme-ov-file)
