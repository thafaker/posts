---
title: Linux auf dem iMac G3
slug: linux-auf-dem-imac-g3
date_published: 1970-01-01T00:00:00.000Z
date_updated: 2025-08-17T09:46:56.000Z
draft: true
---

Ich möchte ein mal mehr aus dem Zauberwald des [Vintage Computings](__GHOST_URL__/tag/vintage-computing/) berichten, denn das bereitet mir Freude. Neben dem Amiga oder dem C=64 betreibe ich ja auch einen PowerPC G5 genannten PowerMac (der hier eine [eigene Website](https://apfelhammer.de) hat) und heute, da geht es um meinen wunderschönen iMac G3. Dieser läuft ziemlich gut mit der letzten Version vom klassischen Mac OS, MacOS9.22

Grund genug also, auf diesem Gerät ein modernes Linux laufen zu lassen. Wie das gehen soll? Nun, es gibt enthusiastische Computer-Freunde, die ihr Linux nicht nur auf klassischer x86 oder anderer zeitgenössischer Architektur laufen lassen, sondern ihre Kernel und Treiber auch in anderen Geschmacksrichtungen übersetzen.

Gemeint ist der legendäre PowerPC Prozessor von IBM (und einem Konsortium), den Apple in seine Macs bis hin zur legendären Käsereibe und dem Powermac G5 benutzte. Dann kam der Switch zu Intel weil es IBM bis zum Schluss nicht schaffte, eine energieeffiziente Version seiner CPU für Notebooks zu entwickeln. Powerbooks mit G5 wären der Hammer gewesen. Kamen aber nie und deshalb Core2Duo von Intel 😄

Wenn du also Linux auf einem iMac G3 zum Laufen bringen willst, dann ist das im Kern ein Dreiklang aus Geduld, Know-How — und ein bisschen Mut zur Unbequemlichkeit. Im Folgenden erzähle ich, was typischerweise nötig ist, welche Distributionen sich bei Bastlern bewährt haben und was du am Ende erwarten darfst.

---

## Aus dem Zauberwald des Vintage-Computings — Wie ich Linux auf meinem iMac G3 zum Leben erwecke

Der iMac G3 steht bei mir wie ein farbiger Pilz im Zauberwald: durchsichtiges Plastik, organische Rundungen, so viel Stil, dass man ihn am liebsten in eine Glaskugel stellen möchte. Er trägt Mac OS 9.22 wie ein altes Abendkleid — sauber, vertraut, vollständig. Und doch kribbelt es: ich will ihm eine zweite, andere Seele schenken. Linux, pur und sparsam, damit das Gerät nicht nur museal daliegt, sondern wieder arbeitet. Nicht als Verstoß gegen Nostalgie, sondern als Fortsetzung — eine Renaissance in einem anderen Gewand.

Im Folgenden beschreibe ich, wie du das praktisch anstellst. Ich mische erzählerische Farben mit klaren Handreichungen: Backups, ISO brennen, ins Open Firmware gelangen, booten, Kernel-/Treiberwahl, Xorg-Fallbacks und Troubleshooting. Du sollst am Ende wissen, was zu tun ist — und warum.

## Erst die Vorsicht: Backup & Inventur

Bevor du irgendetwas veränderst: sichere deine Mac-OS-9-Daten. Classic-Mac-Dateien lassen sich leicht über ein externes Laufwerk oder über Netzwerk kopieren. Wenn du Dual-Boot willst (MacOS9 ↔ Linux), ist eine klare Partitionstabelle wichtig. Notiere Modelljahr und Revision deines iMac (Aufkleber unter dem Fuß oder „About this Mac“), denn manche iMac-G3-Revisionen unterscheiden sich bei Boot-ROM und Peripherie-Chips.

Kurzcheck (sehr praktisch):

- Boot-CD-Leser funktioniert? Ja/Nein
- Modelljahr notiert? (z. B. „iMac G3 (Bondi Blue) 1998“)
- Ethernet funktioniert unter Mac OS? (Ja → gute Chance, dass Linux-Treiber vorhanden sind)

## ISO brennen — so bringst du ein PowerPC-Installationsmedium

Für PowerPC-iMacs brauchst du ein ISO-Image, das für die **powerpc/ppc**-Architektur gebaut ist — z. B. Debian powerpc-Netinstall oder ein spezielles PPC-Live. Moderne Distributionen beschränken manchmal PPC-Builds; für Vintage-Projekte sind ältere stabile Images oder Community-Builds oft die beste Wahl.

Beispiele, wie du eine ISO auf CD brennst (je nach Systeme, die du gerade hast):

Auf macOS (Terminal)

`# schnelles Brennen einer ISO (hdiutil erkennt Medium)`
hdiutil burn /Pfad/zur/debian-powerpc.iso

Auf einem Linux-PC (wodim oder growisofs)

`# mit growisofs (DVD) - für CD ggf. cdrecord/wodim nutzen`
growisofs -Z /dev/sr0=/Pfad/zur/debian-powerpc.iso

`# oder mit wodim (CD)`
wodim dev=/dev/cdrom -v /Pfad/zur/debian-powerpc.iso

Auf Windows: Nutze ein Brennprogramm wie ImgBurn (Image -> Write image file to disc).

Hinweis: Viele iMac G3-Modelle booten zuverlässig von CD, USB-Boot ist oft nicht möglich oder sehr hardwareabhängig. Deshalb: CD-R/DVD-R ist der pragmatische Weg.

## Ins Open Firmware kommen — die kleine Zauberformel

PowerPC-Macs haben Open Firmware (OF) oder proprietäre Boot-ROMs. Bei vielen NewWorld-iMacs (die bekannteren bunten iMac G3) erreichst du die OF so:

- Schalte den Mac aus.
- Schalte ihn ein und halte sofort **⌘ (Command) + ⌥ (Option) + O + F** gedrückt.

Wenn du statt OF die Option hast, beim Booten die **C**-Taste zu halten, startet der Mac oft direkt von einem bootfähigen CD-Medium — das ist der einfachste Weg.

In Open Firmware kannst du überprüfen, von welchem Gerät gebootet wird und einfache Boot-Befehle eingeben. Zwei typische Wege, CD zu booten:

1. Einfacher: CD einlegen und beim Start **C** drücken (falls das funktioniert).
2. Wenn C nicht hilft: im OF-Prompt `boot cd:` oder `boot cd:,\yaboot` probieren (je nach Image). Achtung: die genaue Pfadsyntax hängt vom Image ab — gib diese Befehle als Beispiele, nicht als unfehlbare Regel.

Beispiel (Open Firmware):

ok
`boot cd`:

Falls du unsicher bist: notiere dir vorher, wie dein OF-Prompt aussieht, und halte ein zweites Terminal parat (z. B. Smartphone), um nach Fehlermeldungen zu googeln.

## OldWorld vs. NewWorld — kurz, weil es wichtig ist

- **OldWorld** (ältere Beige-G3s): Hier war oft BootX nötig (ein Mac-seitiger Bootloader). Die Methode unterscheidet sich — du brauchst meistens Mac OS als Stufe-1-Loader.
- **NewWorld** (bunte iMac G3, die meisten Bondi/Slot-Loading Modelle): Einfacher CD-Boot, yaboot als Bootloader ist üblich.

Wenn dein iMac MacOS9 hat und kein Mac OS X, ist die Chance groß, dass er NewWorld ist — aber prüfe das im Zweifel. Wenn OldWorld: plane, eventuell erst ein passendes Mac-OS-CD-Image oder BootX zu verwenden, bevor du Linux startest.

## Welche Distribution — eine pragmatische Empfehlung

- **Debian (powerpc)**: stabil, gut dokumentiert, oft die erste Wahl für Vintage-PPC.
- **Gentoo**: für Tüftler; alles selbst bauen, maximale Kontrolle und Performance, aber zeitintensiv.
- **NetBSD/OpenBSD**: wenn du portabilität und funktionierende Basis-Tools willst (keine Linux-Abhängigkeit).
- **Leichte Linuxes / minimal**: für Desktop-Experimente (tinywm, fluxbox) sehr passend.

Wenn du nur ssh/console willst: nimm ein minimales System. Für Desktop: wähle einen sehr leichten Fenstermanager (fluxbox, fvwm) statt modernen GNOME/KDE.

## Kernel & Treiber — worauf achten (konkret, aber nicht overkill)

Viele Dinge funktionieren „out of the box“ — Ethernet zuerst, Grafik danach. Bei einem iMac G3 ist das typische Vorgehen:

1. Starte das Install-Medium, bring ein Basissystem online (oder installiere auf Platte).
2. Prüfe Hardware-Erkennung: `dmesg`, `ifconfig -a` / `ip link`, `lspci -v` (wenn vorhanden).
3. Grafik: Falls die GPU ein ATI Rage128 (häufig bei iMac G3) ist, ist der klassische Xorg-Treiber `r128`. Falls Nvidia/Matrox, gibt es jeweils `nv`/`mga`. Wenn Treiber fehlen, nutze `fbdev` als Fallback.

Beispiel: Minimal-Xorg-Config mit Framebuffer (Fallback)

Section "Device"
  Identifier "FBdev"
  Driver "fbdev"
  Option "ShadowFB" "true"
EndSection

1. Wenn du selber den Kernel baust (z. B. bei Gentoo), aktiviere:
- PowerPC support (arch=powerpc, PPC32 für iMac G3)
- Framebuffer support (`CONFIG_FB` and vendor-specific framebuffers optional)
- Netzwerktreiber für das erkannte Chipset (z. B. `via-rhine`, `3c59x`, `tulip` – je nach Hardware)
- USB (falls du USB-Tastatur/Maus nutzt)

Wenn du nicht sicher bist, nimm erst ein vorgefertigtes Kernel-Image einer Distro; später kannst du feinjustieren.

## Praktische Kommando-Beispiele während der Installation

Nach dem Booten vom Install-Medium:

`# Prüfe Netzwerk-Interfaces
ip link` show

`# Falls Ethernet nicht automatisch konfiguriert wird (Debian Beispiel)`
dhclient eth0

`# Logs prüfen`
dmesg | less

Wenn X nicht startet, teste Framebuffer:

`# Fallback-Test: starte Xorg mit minimaler Konfiguration`
X -config /etc/X11/xorg.conf &> /tmp/xorg.log
`tail` -n 200 /tmp/xorg.log

## Besonderheiten beim iMac G3 — typische Stolperfallen & Lösungen

- **Kein USB-Boot**: Viele G3-iMacs können nicht von USB booten. Plane CD/DVD oder FireWire-Boot (FireWire-Festplatte kann auf manchen Modellen booten).
- **WLAN**: Onboard-WLAN gab es meist nicht — USB-WLAN-Dongles sind nur bedingt geeignet (Treiber). Ethernet ist dein verlässlicher Freund.
- **Sound**: Funktioniert oft mit OSS/ALSA-Treibern, aber Mixer-Einstellungen sind manchmal nötig.
- **3D-Beschleunigung**: Meist Fehlanzeige oder sehr begrenzt. Plane mit 2D+/Framebuffer.
- **Tastatur/Maus**: Achte, falls PS/2-Adaptionen im Spiel sind, auf korrekte Treiber; USB-Peripherie funktioniert in den meisten Installationen, sobald USB-Support im Kernel aktiv ist.

## Dual-Boot vs. Native Installation — Tipps

Wenn du Mac-OS-9 behalten willst:

- Erstelle eine eigene Partition für Linux (z. B. mit einem Partitionstool unter Mac OS oder mit dem Installer).
- Installiere einen Bootloader, der Dual-Boot ermöglicht (bei NewWorld oft yaboot; bei OldWorld BootX). Notiere dir die Schritte, damit du bei Problemen Mac-OS-9 wiederherstellen kannst.

Wenn du Linux als Einziger haben möchtest:

- Eine komplette Neuinstallation ist sauberer; stelle sicher, dass du ein Notfall-Mac-Medium hast, falls du später zum Classic zurückkehren willst.

## Kurzes Troubleshooting — schnell & pragmatisch

- **Bootet nicht von CD** → Prüfe CD auf anderem Rechner; brenne mit niedrigerer Geschwindigkeit; versuche „C“ zu halten oder OF → `boot cd:`.
- **Kein Netzwerk** → `dmesg` lesen; Chipset notieren; passenden Kernelmodule-Namen suchen (`lsmod` / `modprobe modulename`).
- **X startet nicht** → pruefe `/var/log/Xorg.0.log` bzw. `tail` darauf; starte X mit `-retro`/`-novtswitch` falls nötig; nutze `fbdev`.
- **Tastatur/Mouse spinnen** → USB im Kernel aktivieren, oder temporär Tastatur am Mac OS testen.

## Was du am Ende haben wirst — und warum es sich lohnt

Wenn alles läuft, sitzt du vor dem bunten Gehäuse, und das System antwortet. Es ist kein Hochglanz-Laptop-Eindruck, es ist ein meditatives Arbeiten: langsame, aber beständige Antwortzeiten, ein Terminal, das sich anfühlt wie eine kleine Werkstatt, ein Netzwerk, das dich mit anderen Maschinen verbindet. Du bekommst:

- ein stabil laufendes Terminal/SSH-System,
- einen leichten Desktop (fluxbox, icewm) für Retro-Anwendungen,
- viel Lerngewinn und die Freude, einer alten Maschine neues Leben einzuhauchen.

## Kurze Checkliste (konkret zum Abhaken)

- Backup Mac OS gemacht ✅
- PowerPC-ISO besorgt (Debian/Gentoo/NetBSD) ✅
- ISO auf CD gebrannt (hdiutil / growisofs / ImgBurn) ✅
- CD einlegen und beim Start **C** halten (oder Open Firmware: ⌘+⌥+O+F) ✅
- Installation durchführen, Basissystem testen (`dhclient`, `dmesg`) ✅
- X mit `fbdev` als Fallback einrichten, leichte WM installieren ✅
