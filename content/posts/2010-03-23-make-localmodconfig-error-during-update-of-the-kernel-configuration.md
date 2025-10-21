---
title: make localmodconfig *** Error during update of the kernel configuration.
slug: make-localmodconfig-error-during-update-of-the-kernel-configuration
date_published: 2010-03-23T18:23:45.000Z
date_updated: 2018-08-22T09:38:24.000Z
---

Wer wie ich gerade einen Kernel kompilieren will und später feststellt, dass dieser immer noch total fett ist und tausende unnütze Module mitschleppt und Sachen unterstützt die niemand mehr braucht, habe ich einen Tipp. Ich bin nämlich gestern beim rumsurfen auf folgenden Artikel bei [Heise.de](http://www.heise.de/open/artikel/Konfiguration-Storage-Audio-und-Video-870447.html) gestoßen, der ziemlich viel versprechend klingt:

> Mit Hilfe [des neuen Make-Target](http://git.kernel.org/git/?p=linux/kernel/git/torvalds/linux-2.6.git;a=commitdiff;h=281c9dadc31ffd9f3cf637553134fefe75e849da) "localmodconfig" können Kernel-Tester nun relativ einfach eine zur eingesetzten verwendeten Distribution und Hardware passende Kernel-Konfiguration erstellen, bei der keine unnötigen Module kompiliert werden. Als Ausgangsbasis dient die Konfigurationsdatei des gerade laufenden Kernels; jedoch werden alle Module deaktiviert, die zu diesem Zeitpunkt nicht geladen sind.

Das heißt also, dieser Befehl lädt die vom laufenden Kernel aktuelle Konfigurationsdatei und schaut dann nach, was gerade wirklich geladen ist. Dann deaktiviert er den ganzen Kram in der Config und man baut sich einen Kernel, der nur das beinhaltet, was der Rechner wirklich braucht. Allerdings muss man bedenken, dass gerade nicht angeschlossene USB-Geräte die demzufolge auch nicht geladen sind, eben auch nicht berücksichtigt werden.

Mir egal, ich wollte das natürlich machen. Und Bingo, ein Problem: Ich habe also den aktuellsten Kernel 2.6.33.1 ([hier](http://www.kernel.org/pub/linux/kernel/v2.6/linux-2.6.33.1.tar.bz2)) geladen, ihn ordentlich nach /usr/src entpackt und per Symlink auf `/usr/src/linux` verlinkt. Wenn ich nun aber `make localmodconfig` laufen lies, quittierte er den Dienst immer mit diesem Fehler.

>     *** Error during update of the kernel configuration.

Nach diverser *googlelei* stieß ich letztendlich auf [folgende Website](https://patchwork.kernel.org/patch/76729/), auf welcher es einen Patch zum Fehler gibt.

> If someone downloads a brand new kernel and runs localmodconfig or localyesconfig, the ending result will report:
> 
> *** Error during update of the kernel configuration.
> 
> This is because localmodconfig and localyesconfig must create the include/generated directory to place the autoconf.h file.

Ich habe also den folgenden [Patch](https://patchwork.kernel.org/patch/76729/raw/) herunter geladen, im Verzeichnis /usr/src gespeichert und mit folgendem Kommando aus dem Verzeichnis `/usr/src/linux` gepatcht:
`patch -p 1 -i ../1-4-kconfig-Create-include-generated-for-localmodconfig.patch`

Und wieder Bingo, das hat funktioniert. Ein weiterer Aufruf von `make localmodconfig` brachte diesmal keinen Fehler mehr und der Kernel kompiliert bereits (natürlich nach einem `make xconfig`), hoffentlich funktionsfähig, mit minimalem Ballast.
![kernel.compiling.putty](//picdump.thafaker.de/2010/03/kernel.compiling.putty_thumb.png)
