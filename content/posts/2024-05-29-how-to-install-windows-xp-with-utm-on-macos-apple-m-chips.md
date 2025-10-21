---
title: How To Install Windows XP with UTM on macOS with Apple M Chips
slug: how-to-install-windows-xp-with-utm-on-macos-apple-m-chips
date_published: 2024-05-29T15:22:55.000Z
date_updated: 2024-05-31T06:54:29.000Z
tags: vintage computing, utm, qemu, anleitung, howto, how to
---

### Table Of Content

1. [Wie cool ist eigentlich UTM, der freie QEMU basierte Virtualisierer für macOS](__GHOST_URL__/wie-cool-ist-eigentlich-utm/)
2. How To Install Windows XP with UTM on macOS with Apple M Chips

---

In diesem Beitrag habe ich bereits über den großartigen Emulator UTM berichtet - und wie einfach er die Welt macht. In diesem Artikel möchte ich nun Schritt für Schritt beschreiben, wie man Windows XP installiert - mit voller Grafik und Netzwerkunterstützung. Ihr werdet euch wundern wie großartig das Internet mit dem Internet Explorer 6 aussieht (man sieht aufgrund fehlendem SSL nämlich nichts mehr)

Aber genug geredet, wenn ihr euch UTM herunter geladen habt, geht es nun los.

### How To Windows XP on UTM Apple Silicon M Chip

1. Ihr ladet und installiert UTM [hier](https://github.com/utmapp/UTM/releases/latest/download/UTM.dmg) (und könnt [hier](__GHOST_URL__/wie-cool-ist-eigentlich-utm/) darüber lesen).
2. Ihr ladet euch die für Windows XP [vorbereitete Virtuelle Maschine](https://github.com/utmapp/vm-downloads/releases/download/windows-template/windows-xp-x64-utm.zip) (diese ist noch ohne Windows XP, das muss man erst installieren).
3. Ihr entpackt die WinXP VM
4. Ihr startet UTM und zieht euch die VM hinein 

![](__GHOST_URL__/content/images/2024/05/Bildschirmfoto-2024-05-29-um-16.59.30.png)
1. Ihr geht zu [Archive.org](https://archive.org/details/windows-xp-professional-sp-3-nov-2013-inc-sata-drivers) und ladet euch die [Windows XP ISO](https://archive.org/download/windows-xp-professional-sp-3-nov-2013-inc-sata-drivers/en_windows_xp_professional_64-bit_dvd.iso). Hier sind schon diverse Treiber und Service Pack 3 enthalten, ein guter Start für ein neues Windows XP `en_windows_xp_professional_sp3_Nov_2013_Incl_SATA_Drivers.iso` 
2. Ihr editiert die virtuelle Maschine mit Rechtsklick --> Edit

![](__GHOST_URL__/content/images/2024/05/Bildschirmfoto-2024-05-29-um-17.01.16.png)Rechtsklick EDIT der virtuellen Maschine
1. Dort wählt ihr beim zweiten IDE Laufwerk die zuvor bei Punkt 5 herunter geladene ISO Datei eurer Windows XP CD aus.

![](__GHOST_URL__/content/images/2024/05/Bildschirmfoto-2024-05-29-um-17.02.12.png)Auf Durchsuchen klicken und die ISO auswählen
1. Dann startet ihr eure Virtuelle Maschine und er sollte in den blauen Setup Screen von Windows XP booten. Installiert Windows XP mit den Standard-Einstellungen.

![Setup of Windows XP in UTM](__GHOST_URL__/content/images/2024/05/Bildschirmfoto-2024-05-29-um-17.06.01.png)Setup of Windows XP in UTM
1. Wählt aus, dass er eure 20 GB Festplatte mit NTFS formatieren soll. Danach kopiert Setup seine Dateien von der CD (ISO Abbild) auf die Festplatte. 

![Windows XP Setup Installation Process](__GHOST_URL__/content/images/2024/05/Bildschirmfoto-2024-05-29-um-17.11.30.png)Windows XP Setup Installation Process
1. Irgendwann ist das Setup durch und ihr solltet ungefähr folgendes Bild sehen:
2. Für eine bessere Treiberunterstützung solltet ihr euch die SPICE Tools ISO von UTM herunter laden. [Hier](https://docs.getutm.app/guest-support/windows/#download). ([Direktlink](https://github.com/utmapp/qemu/releases/download/v7.0.0-utm/spice-guest-tools-0.164.4.iso))
3. Benutzt das CD-Icon oben in der Toolbar um die XP ISO auszuwerfen und die SPICE ISO einzulegen und installiert die SPICE Tools.

![Icon zum Wechsel der eingelegten CD / ISO Abbild.](__GHOST_URL__/content/images/2024/05/Bildschirmfoto-2024-05-31-um-08.48.55.png)Icon zum Wechsel der eingelegten CD / ISO Abbild.![](__GHOST_URL__/content/images/2024/05/Bildschirmfoto-2024-05-31-um-08.53.28.png)
1. Ihr seid fertig und habt ein Windows XP auf eurem Apple Silicon Mac 😃
2. Warum meine Nummerierung wieder bei 1 und nicht 11 weiter gemacht hat, weiß ich übrigens auch nicht.

*Viel Spaß mit eurem Vintage OS 😄*
