---
title: Wie cool ist eigentlich UTM, der freie QEMU basierte Virtualisierer für macOS
slug: wie-cool-ist-eigentlich-utm
date_published: 2024-05-29T14:27:43.000Z
date_updated: 2024-05-29T15:24:09.000Z
tags: qemu, utm, apple silicon, sun solaris 9, vintage computing
---

### Table Of Content

1. Wie cool ist eigentlich UTM, der freie QEMU basierte Virtualisierer für macOS
2. [How To Install Windows XP with UTM on macOS with Apple M Chips](__GHOST_URL__/how-to-install-windows-xp-with-utm-on-macos-apple-m-chips/)

---

**UTM** ist gerade auf Macs mit Apple Silicon, also M1, M2 oder M3 Chip eine absolut empfehlenswerte - weil besonders einfach zu bedienende - Virtuelle Maschine mit der man **emulieren** und *virtualisieren* kann. 

UTM nutzt das Hypervisor-Virtualisierungs-Framework von Apple, um ARM64-Betriebssysteme auf Apple Silicon mit nahezu nativer Geschwindigkeit auszuführen. Auf Intel-Macs kann das x86/x64-Betriebssystem virtualisiert werden. Darüber hinaus ist eine Emulation mit geringerer Leistung verfügbar, um x86/x64 auf Apple Silicon sowie ARM64 auf Intel auszuführen. 

*Virtualisieren* bedeutet, man kann ARM Software wie Windows for ARM oder macOS direkt betreiben, emulieren bedeutet, man kann eine Vielzahl von Prozessoren benutzen und auf diesen die dazugehörige Software laufen lassen. Mit Software meine ich Betriebssysteme und im Speziellen meine ich hier für mich vor allem Vintage OS. Neben Windows 95 oder einem XP (auf x86) kann man auch sowas wie Solaris 9 auf echter SPARC Prozessor-Hardware emulieren und benutzen, als säße man direkt vorm eigenen Blech.

**Und das finde ich großartig. **

Hintergrund von **UTM** ist das bereits Jahrzehnte gut abgegangen **QEMU**[[1]](#fn1) in einer speziell für den Mac angepassten, besonders einfach zu benutzenden Version. QEMU emuliert neben SPARC auch Systeme mit den folgenden Prozessorarchitekturen: x86 (x86-32 und x86-64), PowerPC (32- und 64-Bit), ARM (32- und 64-Bit), Alpha, CRIS, HPPA, LatticeMico32, m68k bzw. Coldfire, MicroBlaze, MIPS, Moxie, Nios II, SH-4, S/390, Sparc32/64, TILE-Gx, TriCore, OpenRISC, RISC-V, Unicore und Xtensa (Stand 2019).

UTM ist kostenlos und steht [hier](https://mac.getutm.app) zum Download zur Verfügung, kann aber auch zur Unterstüztung direkt im [Mac App Store](https://apps.apple.com/us/app/utm-virtual-machines/id1538878817) für 9,99 gekauft werden.

Nicht falsch verstehen, QEMU kann schon immer all diese Systeme auf all diesen Systemen emulieren und ist genau dafür großartig. Das besondere an UTM ist jedoch, dass es z.B. viele vorkonfigurierte Systeme gibt, die speziell auf dem M-Macs laufen und plug'n'play wie damals Soundkarten unter Windows 98 problemlos funktionieren. Ich habe hierzu Solaris und ReactOS ausprobiert, das freie Windows 2000 binärkompatible System.

---

1. 
QEMU (von englisch „Quick Emulator“) ist eine freie Virtualisierungssoftware, die die gesamte Hardware eines Computers emuliert und durch die dynamische Übersetzung der Prozessorinstruktionen des Gastprozessors (englisch guest) in Instruktionen für den Wirtprozessor (englisch host) eine sehr gute Ausführungsgeschwindigkeit erreicht. [↩︎](#fnref1)

### Solaris 9
![UTM emulation SPARCStation 5 with Sun Solaris 9](__GHOST_URL__/content/images/2024/05/Bildschirmfoto-2024-05-29-um-16.03.12.png)UTM emulation SPARCStation 5 with Sun Solaris 9 ![Sun Solaris 9 CDM Login under UTM](__GHOST_URL__/content/images/2024/05/Bildschirmfoto-2024-05-29-um-16.13.34.png)Sun Solaris 9 CDM Login under UTM
### ReactOS
![ReactOS Boot Screen under UTM](__GHOST_URL__/content/images/2024/05/Bildschirmfoto-2024-05-29-um-16.23.29.png)ReactOS Boot Screen under UTM![Bootet ReactOS under UTM with Device Driver Installation Menu](__GHOST_URL__/content/images/2024/05/Bildschirmfoto-2024-05-29-um-16.24.34.png)Bootet ReactOS under UTM with Device Driver Installation Menu
## Ressourcen

- [UTM Website](https://mac.getutm.app)
- [UTM Download](https://github.com/utmapp/UTM/releases/latest/download/UTM.dmg) (DMG File)
- [UTM Download von fertigen virtuellen Maschinen](https://mac.getutm.app/gallery/)
- [UTM Download Solaris 9 ](https://mac.getutm.app/gallery/sun-solaris-9)
