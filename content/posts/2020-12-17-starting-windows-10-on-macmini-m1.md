---
title: Windows 10 on MacMini M1
slug: starting-windows-10-on-macmini-m1
date_published: 2020-12-17T20:22:37.000Z
date_updated: 2020-12-19T12:22:08.000Z
tags: apple m1, apple silicon, M1, windows 10 for arm, arm, macmini, qemu, how to, howto, anleitung
excerpt: In dieser Anleitung beschreibe ich, wie man Windows 10 for ARM auf einem aktuellen Mac mit dem neuen AppleSilicon M1 Chip installieren kann. Die Aufgabe gestaltet sich leichter als gedacht, weil sehr viele Aufgaben bereits vorher durch kluge Hacker durchgeführt worden sind.

Viel Spaß :-)
---

Ich konnte nicht wiederstehen und habe mir einen [MacMini M1](__GHOST_URL__/hallo-macmini-m1/) in der Standardkonfiguration (256GB SSD, 8GB-Ram) gekauft, weil ich den neuen Chip so spannend finde. Und weil mich die Eurphorie der ersten Stunde angesteckt hat, wollte ich all die vielen positiven Reviews wenigstens selbst bestätigen können.

Und ich kann. Das Gerät ist unglaublich gut. Unglaublich schnell. Und es funktioniert für dieses frühe Stadium auch schon wirklich stabil. Aber über all die Vorteile wie Wärmeentwicklung, Geschwindigkeit und Rosetta2 ist an anderen Stellen bereits viel geschrieben worden, sodass ich an dieser Stelle nicht noch mal ausholen möchte. Aber ich möchte etwas anderes tun. Nämlich mit dem Mac etwas rumspielen. Was also liegt näher als Windows 10 zu installieren? Nichts, genau :-)

# Windows 10 for Arm on Apple Silicon

Alexander Graf ([Twitter (archiviert)](http://web.archive.org/web/20201219103601/https://twitter.com/_AlexGraf)) hat QEMU soweit gepatcht, dass es auf Apples M1 läuft. Weiterhin gibt es Windows 10 for ARM als Developer Review zum kostenlosen Download, eine Registrierng bei Microsoft ist jedoch nötig. Wenn man alles zusammen hat, kann man anfangen das Ganze zum Laufen zu bringen.

## Voraussetzung

1. Mac mit M1 Chip (Macbook Pro, MacBook Air, MacMini)
2. Windows 10 for Arm virtual Disk Image
3. QEMU gepatchet

### Downloads

1. Ladet qemu-m1.zip von dieser Quelle: [https://mega.nz/file/QYB0QTrC#p6IMBJlFqqNKuGonwrDkPOVKQj8yHCVgiLOYVaGvs4M (archiviert)](http://web.archive.org/web/20230509125116/https://mega.nz/file/QYB0QTrC), Die ZIP beinhaltet pre-built Versionen von qemu-system-aarch64, efi-virtio.rom, und QEMU_EFI.fd. (All diese sind Open Source und man kann sie auch selber bauen, muss man aber eben nicht. Hier der [Link zum selber Bauen](https://forums.macrumors.com/threads/success-virtualize-windows-10-for-arm-on-m1-with-alexander-grafs-qemu-hypervisor-patch.2272354/))
2. Ladet das *Windows Insider Preview ARM64* (das ist Windows for ARM) von Microsoft unter [https://www.microsoft.com/en-us/software-download/windowsinsiderpreviewARM64](https://www.microsoft.com/en-us/software-download/windowsinsiderpreviewARM64), das ist ein VHDX Image. Ihr benötigt dazu einen Microsoft Account und müsst euch für Developer registrieren, was kostenlos ist.

### Weiter gehts

- Entpackt die qemu-m1.zip
- Kopiert das VHD Image von Windows 10 for ARM in den entpackten QEMU Ordner
- Öffnet das Terminal und navigiert zum entpackten QEMU-Order.

    cd ~/Downloads/qemu-m1

- Startet QEMU und die virtuelle Maschine. Kopiert den unten stehenden Code ins Terminal Fenster. (kopiert den gesamten Block auf einmal),und drückt Enter:

    DYLD_LIBRARY_PATH=. \
    ./qemu-system-aarch64 \
    -M virt \
    -accel hvf \
    -m 5G \
    -smp 4 \
    -cpu max \
    -device ramfb \
    -serial stdio \
    -drive file=Windows10_InsiderPreview_Client_ARM64_en-us_20231.VHDX,if=none,id=NVME1 \
    -device nvme,drive=NVME1,serial=nvme-1 \
    -device nec-usb-xhci \
    -device usb-kbd \
    -device usb-tablet \
    -device intel-hda -device hda-duplex \
    -drive file=vars-template-pflash.raw,if=pflash,index=1 \
    -bios QEMU_EFI.fd

- Achtung: Es kann unter Umständen folgende Meldung erscheinen:

![](__GHOST_URL__/content/images/2020/12/Bildschirmfoto-2020-12-17-um-21.17.04.png)
- Klickt okay und geht folgendermaße vor: Öffnet die Systemeinstellungen und wechselt zum Reiter "Sicherheit". Dort hebt ihr mit dem Schlosssysmbol den Schutz auf und erlaubt das Öffnen von "qemu-system-aarch64" mit "Trotzdem erlauben". 

![](__GHOST_URL__/content/images/2020/12/Bildschirmfoto-2020-12-17-um-21.18.10.png)
- Ich musste das ganze 6 mal durchführen, für jede einzelne Bibliothek.
- Im Anschluss sollte der obere Befehl funktionieren und das Setup, Window-Installer starten :-)

![Starten der Installation von Windows 10 for Arm on Apple M1](__GHOST_URL__/content/images/2020/12/Bildschirmfoto-2020-12-17-um-21.20.54.png)Starten der Installation von Windows 10 for Arm on Apple M1
- Installiert Windows 10 und führt das Setup zu den Telemtriedaten etc. aus. Viel Glück.

![QEMU auf Apple MacMini M1 mit Windows 10](__GHOST_URL__/content/images/2020/12/Bildschirmfoto-2020-12-17-um-21.25.09-1.png)QEMU auf Apple MacMini M1 mit Windows 10![](__GHOST_URL__/content/images/2020/12/Bildschirmfoto-2020-12-17-um-21.30.26.png)![thahipster.de auf Windows for Arm on MacMini M1](__GHOST_URL__/content/images/2020/12/Bildschirmfoto-2020-12-18-um-11.43.14.png)thahipster.de auf Windows for Arm on MacMini M1
Work In Progress

### Windows Auflösung auf 1024x768: setzen​

1. Windows herunter fahren.
2. qemu-system-aarch64 > Quit QEMU > Quit.
3. Startet Windows mit dem gleichen Befehl wie oben, also folgendem:

    DYLD_LIBRARY_PATH=. \
    ./qemu-system-aarch64 \
    -M virt \
    -accel hvf \
    -m 5G \
    -smp 4 \
    -cpu max \
    -device ramfb \
    -serial stdio \
    -drive file=Windows10_InsiderPreview_Client_ARM64_en-us_20231.VHDX,if=none,id=NVME1 \
    -device nvme,drive=NVME1,serial=nvme-1 \
    -device nec-usb-xhci \
    -device usb-kbd \
    -device usb-tablet \
    -device intel-hda -device hda-duplex \
    -drive file=vars-template-pflash.raw,if=pflash,index=1 \
    -bios QEMU_EFI.fd

4. Wenn QEMU die Startoptionen zeigt "Start boot option", drückt ihr schnell die Escape-Taste, ihr landet im QEMU Bios.
5. Wechselt mit den Pfeiltasten zu "Device Manager", drückt Enter, und geht zu "OVMF Platform Configuration", wieder Enter. Es ist normal dass das alles ganz langsam funktioniert.
6. Wählt <640x480> und stellt auf 1024x768.
![QEMU Bios](__GHOST_URL__/content/images/2020/12/Bildschirmfoto-2020-12-18-um-09.31.05.png)QEMU Bios
7. Drückt F10 oder FN + F10 zum Speichern.
8. Geht mit ESC zurück ins Hauptmenü.
9. Wählt "Continue", drückt Enter und er sollte Windows booten..
10. Nach dem Start von Windows fahrt ihr es erneut herunter
11. qemu-system-aarch64 > Quit QEMU > Quit.
12. Startet QEMU mit dem Kommando von oben, es sollte nun 1024er Auflösung bereit stehen. Nicht viel, aber immerhin etwas :-)

### Internet für Windows 10 aktivieren, Netzwerkkarte installieren

1. Ladet euch die *virtio driver ISO* von [https://fedorapeople.org/groups/vir...o/virtio-win-0.1.190-1/virtio-win-0.1.190.iso](https://fedorapeople.org/groups/virt/virtio-win/direct-downloads/archive-virtio/virtio-win-0.1.190-1/virtio-win-0.1.190.iso) herunter.
2. Verschiebt den Download in den entpackten qemu-m1 Ordner.
3. Startet Windows 10 und öffnet CMD, command.com, rechts klick und als Administrator ausführen
4. Klickt “Yes” im UAC prompt.
5. Erlaubt Test-Treiber mit folgendem Befehl in der DOS Eingabeaufforderung:

    bcdedit -set TESTSIGNING ON

6. Fahrt Windows herunter
7. beendet QEMU.
8. Startet QEMU, diesmal mit dem folgenden Boot-Befehl:

    DYLD_LIBRARY_PATH=. \
    ./qemu-system-aarch64 \
    -M virt \
    -accel hvf \
    -m 5G \
    -smp 4 \
    -cpu max \
    -device ramfb \
    -serial stdio \
    -drive file=Windows10_InsiderPreview_Client_ARM64_en-us_20231.VHDX,if=none,id=NVME1 \
    -device nvme,drive=NVME1,serial=nvme-1 \
    -device nec-usb-xhci \
    -device usb-kbd \
    -device usb-tablet \
    -device intel-hda -device hda-duplex \
    -drive file=vars-template-pflash.raw,if=pflash,index=1 \
    -drive file=virtio-win-0.1.190.iso,media=cdrom,if=none,id=cdrom -device usb-storage,drive=cdrom \
    -net nic,model=virtio \
    -net user \
    -bios QEMU_EFI.fd

9. Nachdem Windows wieder gestartet ist, loggt ihr euch ein und führt einen Rechtsklick auf das Start Menü aus. Dann wählt ihr “Device Manager”.
10. Im Bereich “Other devices”, scrollt ganz nach unten.
11. Ihr führt einen Rechtsklick auf das aller untertest “Unknown device” durch > Update drivers > Browse my computer for drivers > Browse.
12. Dann wählt ihr das virtuelle CD-Laufwerk mit der ISO aus, die wir gerade herunter geladen hatten, diese sollte eingelegt sein (D > virtio-win > OK > Next > Allow.
13. Nachdem alles installiert wurde, habt ihr einen Red Hat Netzwerktreiber und die virtuelle Maschine sollte Internet haben :-)
![Windows 10 for Arm auf MacMini M1 zeigt thahipster.de](__GHOST_URL__/content/images/2020/12/Bildschirmfoto-2020-12-18-um-08.41.26.png)Windows 10 for Arm auf MacMini M1 zeigt thahipster.de

![](__GHOST_URL__/content/images/2020/12/Bildschirmfoto-2020-12-17-um-21.16.30.png)

![](__GHOST_URL__/content/images/2020/12/Bildschirmfoto-2020-12-17-um-21.17.04-1.png)

![](__GHOST_URL__/content/images/2020/12/Bildschirmfoto-2020-12-17-um-21.18.10-1.png)

![](__GHOST_URL__/content/images/2020/12/Bildschirmfoto-2020-12-17-um-21.20.54-2.png)

![](__GHOST_URL__/content/images/2020/12/Bildschirmfoto-2020-12-17-um-21.25.09-2.png)

![](__GHOST_URL__/content/images/2020/12/Bildschirmfoto-2020-12-17-um-21.26.30.png)

![](__GHOST_URL__/content/images/2020/12/Bildschirmfoto-2020-12-17-um-21.29.00.png)

![](__GHOST_URL__/content/images/2020/12/Bildschirmfoto-2020-12-17-um-21.30.26-1.png)

![](__GHOST_URL__/content/images/2020/12/Bildschirmfoto-2020-12-17-um-21.32.25.png)

Via: 
[

[SUCCESS] Virtualize Windows 10 for ARM on M1 with Alexander Graf’s qemu hypervisor patch

I was able to successfully virtualize Windows 10 for ARM on M1 with Alexander Graf’s QEMU hypervisor patch. Screenshot: How to virtualize Windows 10 on M1:1. Download qemu-m1.zip from https://mega.nz/file/QYB0QTrC#p6IMBJlFqqNKuGonwrDkPOVKQj8yHCVgiLOYVaGvs4M or this forum attachment. It...

![](https://images.macrumors.com/images-new/favicon.ico)MacRumors Forums1958llakin

![](https://forums.macrumors.com/attachments/qemu-windows-10-png.1682350/)
](https://forums.macrumors.com/threads/success-virtualize-windows-10-for-arm-on-m1-with-alexander-grafs-qemu-hypervisor-patch.2272354/)
