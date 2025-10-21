---
title: Funktioniert Linux auf meinem Macbook Pro 2016?
slug: funktioniert-linux-auf-meinem-macbook-pro-2016
date_published: 2017-04-14T17:30:49.000Z
date_updated: 2018-08-22T09:37:37.000Z
tags: macbook pro, 13", touchbar, linux, unix, macbook pro 2016, retina
---

Da ich über ein Macbook Pro 2016 mit Touchbar verfüge, frage ich mich, ob Linux auf der Kiste rennt. Warum? - werden da manche fragen. Nun… weil ich schon seit urzeiten mit Linux abhänge, meist auf Servern, aber oft auch mal privat. Außerdem bereitet es mir oft auch Freude, mir auf dem Desktop wieder mal ein Linux zu erarbeiten. 

Aber wie auch immer meine privaten Hintergründe sein mögen, gedacht - gesucht. Und folgende Ressource im Netz gefunden, die sich genau mit der Frage beschäftigt: was läuft eigentlich Linux auf dem aktuellen Macbook Pro 2016. Kurz gesagt… *es sieht ziemlich schlecht aus*.

![](__GHOST_URL__/content/images/2017/04/powerbook-1.jpg)

## [Link](https://github.com/Dunedan/mbp-2016-linux)

### What works

- Booting (i.e Grub etc)
- Recognizes disk on MacBookPro13,3; MacBookPro13,2 and MacBookPro13,1 need kernel patch
- Keyboard, touchpad, and basic touchbar functionality
- HiDPI detection
- Accelerated video
- Screen brightness control
- WiFi in a very limited fashion
- USB
- Sensors (install lm_sensors package)

### What doesn't work

- Suspend/Resume
- Keyboard backlight (always off)
- Audio (two cards show up, and intel driver is loaded, but no sound)
- Camera

### Untested

- Thunderbolt
- DisplayPort
- Bluetooth

**Artikelfoto**: (C) [Foto (archiviert)](http://web.archive.org/web/20161028064806/http://pinillos.org/wheezy-powerbook)
