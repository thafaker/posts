---
title: Wie man eine PC Grafikkarte für den Mac um flasht - EFI Rom
slug: wie-man-eine-pc-grafikkarte-fur-den-mac-um-flasht-efi-rom
date_published: 2019-02-06T20:16:00.000Z
date_updated: 2024-11-13T13:25:47.000Z
tags: vga, geforce, nVidia, 680gtx, anleitung, howto, how to, bigmac, flash, efi bios
---

Wie ich an [passender Stelle](__GHOST_URL__/der-legendare-macpro-kasereibe/) bereits verkündet habe, bin ich Besitzer eines **Mac Pro**. Und als Dieser ist es nun meine forschende Aufgabe, mich mit der *Upgrade-Fähigkeit* zu beschäfitgen. Denn eines der Hauptmerkmale des Mac Pro, neben seinem zeitlosen Design, ist zweifelsohne seine Fähigkeit, wie ein ganz normaler Workstation-PC aufgerüstet werden zu können. Bei Bedarf. *USB 3.1*? Kein Problem. *Mehr Ram*? Natürlich, 64 oder 128 GB? Ach so, und neue *Prozessoren*? Wie viel hätten Sie denn gern, 2 Stück mit 3,46 Ghz? Natürlich, 12 Kerne, darunter darf es nicht sein! Ach und die Grafikkarte auch? Oh, darüber müssen wir genauer reden…

Und schon sind wir beim Thema. [[1]](#fn1) Denn Grafikkarten für Apple-Geräte sind besonders, denn Grafikkarten für Apple-Hardware haben immer auch ein EFI-Firmware-Image, damit sie am Mac richtig funktionieren. Ohne dieser spezielle Software funktionieren sie zwar auch, aber erst wenn das Betriebssystem fertig geladen ist, also beim Login-Bildschirm. Das ist an sich nicht so problematisch, aber wenn man sein System neu aufspielen möchte, wenn man den Bootmanager zur Wahl der Festplatte (hat man etwa eine Dualboot-Installation mit Windows oder Linux auf seinem Mac) wählen möchte - das alles geschieht vor dem Betriebssystem und benötigt eine Mac-kompatible Grafikkarte. Eine MAC-Edition.

![MacPro 6,1 with Dual Screen Setup](__GHOST_URL__/assets/2019/02/desktop.jpg)
MacPro 6,1 with Dual Screen Setup
Nun ist es so dass vor langer Zeit mal jemand eine spezielle Mac-Version einer EVGA nVidia Geforce GTX 680 mit 2 und 4 GB-Ram nahm, das ROM extrahierte und sich wenig später heraus stellte, dass nun nahezu alle PC-kompatiblen nVidia Geforce GTX 680 Grafikkarten mit dieser Firmware geflashed werden können - und sich fortan wie eine echte EVGA Mac-Edition verhalten. Also einen Boot-Screen haben etc. pp.; Und so habe auch ich das getan. Ich habe mir für 30€ eine gebrauchte Geforce GTX 680 Grafikkarte (ich glaube meine ist von Gainward) auf eBay-Kleinanzeigen organisiert, 2048 MB Ram Version, die zugehörige Firmware geladen, das Tool zum flashen installiert - und fertig war meine original Mac-Edition Geforce 680 GTX! Sie läuft im System. Wunderschön. Es gibt keinerlei Probleme. Und sie hat noch richtig Dampf, also für so eine alte Karre!

![About This Mac](__GHOST_URL__/assets/2019/02/geforce680gtx.png)
About This Mac
Und das beste: diese Grafikkarte hat nativen macOS 10.14 Mojave Support für diese Grafikkarte, ihr könnt also nach dem Flashing sofort beginnen, Mojave zu installieren, ihr seid **Metal-Kompatibel**!

![Nativer Metal Support für macOS Mojave](__GHOST_URL__/assets/2019/02/heavymetal.png)
Nativer Metal Support für macOS Mojave
ACHTUNG. ANLEITUNG AUF EIGENE GEFAHR. Wir übernehmen keine Haftung.

### Anleitung How To flash Geforce for MacPro

Ihr braucht einen MacPro 3,1 oder 4,1 oder 5,1 (es funktioniert nicht mit einem MacPro 1,1 oder 2,1). Diese Anleitung führt ihr auf eigene Gefahr hin durch. Ich kann an dieser Stelle keine Verantwortung für Defekte übernehmen. Im Zeifelsfall führen sie die folgenden Schritte nicht durch!

1. Ihr braucht Windows dazu. Das nvidia-Flash-Tool funktioniert nur unter Windows. Es geht nicht mit Bootcamp oder einem Emulator (weil der auch die Grafikkarte emulieren würde); Ihr müsst richtig echt Windows auf dem Mac booten ODER die zu flashende Grafikkarte in einen Windows-PC einbauen und dort booten! Gut? Okay.
2. Die zu flashende Grafikkarte muss wie gesagt eingebaut sein! Bitte keine andere Grafikkarte gleichzeitig iengebaut lassen, nur die zu flashende GTX.
3. Bootet euren MacPro in macOS, stellt dort im Boot-Manager Windows ein und rebootet. Nun sollte das System automatisch Windows starten. Auch wenn ihr mit der PC-Grafikkarte keinen Bootscreen sehen könnt. Das ist normal.
4. Loggt euch in Windows ein :-)
5. Ladet euch die folgende Software herunter:

- Software zum Flashen: [NVflash](https://www.techpowerup.com/download/nvidia-nvflash/) (5.134)

- Für eine 4GB Karte: [4GB-Rom](__GHOST_URL__/content/images/4gb-680gtx.zip) (Diese Firmware stammt von Fl0r!an, der ist okay!)

- Für eine 2GB Karte: [2GB-Rom](__GHOST_URL__/content/images/2gb-680gtx.zip) (Diese Firmware stammt aus der originalen EVGA)

6. Entpackt `nvflash` an einen einfachen Ort, ich habe es unter
`c:\nvflash`.
7. Kopiert dort auch die richtige Firmware Datei mit hinein. Bei mir war es die 2GB-Variante. Diese hat die Endung *.bin, das ist falsch. Benennt sie nach dem Entpacken bitte in *.rom um. Die 4GB-Variante braucht ihr nicht umbenennen, die heißt schon *.rom
8. Der Ordner sollte nun folgende Dateien enthalten:

- nvflash.exe (sowie die anderen Dateien aus dem ZIP)

- gtx680mac.rom (für die 2GB Variante)

- GTX680-4GB-DVI.rom (für die 4GB Variante)

9. Öffnet die Kommandozeile von Windows, DOS lässt grüßen! Klickt auf START, gebt CMD ein und drückt Enter.
10. In dem Fenster wechselt ihr nun in das Verzeichnes, was wir oben angelegt haben.
`cd c:\nvflash`

Und drückt ENTER.
11. Sichert das aktuelle ROM was derzeit in eurer Grafikkarte steckt, damit ihr es im Bedarfsfall zurück in eure Karte flashen könnt.
`nvflash -b Backup-Worscht.rom`
12. Nun flasht ihr die 2 oder 4 GB Rom Variante in die Grafikkarte. Betet zu Krishna [[2]](#fn2).
`nvflash -4 -5 -6 gtx680mac.rom`
13. Wenn Ihr nach Bestätigung gefragt werdet, bestätigt mit YES. Wenn ihr "Warten" sollt, wartet!
14. Ihr seht eine Erfolgsmeldung. Das ganze findet in dem oben geöffneten CMD Command.Com Fenster statt. Dort stehen auch alle Meldungne drin.
15. Führt einen Reboot durch. Bei mir konnte ich direkt schon beim Reboot den Apfel sehen, das untrügliche Zeichen dafür, dass ich nun einen Boot-Screen habe und die ganze Prozedur funktioniert hat.
16. Trinkt zur Freude des Tages ein Bier. Und spielt einen EGO-Shooter.

*Das wars auch schon wieder*. Bei Fragen könnt ihr gern die Kommentarfunktion benutzen.

![Installing macOS Mojave](__GHOST_URL__/assets/2019/02/mojave.jpg)
Installing macOS Mojave
---

**Artikelbild** 1: Photo by [Reina Kouska](https://unsplash.com/photos/zPHftoPajis?utm_source=unsplash&amp;utm_medium=referral&amp;utm_content=creditCopyText) on [Unsplash](https://unsplash.com/search/photos/nvidia?utm_source=unsplash&amp;utm_medium=referral&amp;utm_content=creditCopyText).

**Artikelbild** 2: Photo by [Farzad Nazifi](https://unsplash.com/photos/p-xSl33Wxyc?utm_source=unsplash&amp;utm_medium=referral&amp;utm_content=creditCopyText) on [Unsplash](https://unsplash.com/search/photos/macpro?utm_source=unsplash&amp;utm_medium=referral&amp;utm_content=creditCopyText).

**Artikelbilder**: Die restlichen Bilder im Artikel sind Anfertigungen von mir selbst.

---

1. 
Wir sind hier ja praktisch immer beim Thema, ich weiß. [↩︎](#fnref1)

2. 
thafaker.de empfiehlt hier übrigens nun zu jedem Gott zu beten, Hauptsache die Grafikkarte nimmt keinen Schaden. [↩︎](#fnref2)

### Ressourcen

[

2gb-680gtx

ROM File for nVidia 680 GTX - 2 GB Version

2gb-680gtx.zip

173 KB

.a{fill:none;stroke:currentColor;stroke-linecap:round;stroke-linejoin:round;stroke-width:1.5px;}download-circle
](__GHOST_URL__/content/files/2024/11/2gb-680gtx.zip)

[

GTX680-4GB-ROM

ROM File for nVidia 680 GTX - 4 GB Version

GTX680-4GB-ROM.zip

173 KB

.a{fill:none;stroke:currentColor;stroke-linecap:round;stroke-linejoin:round;stroke-width:1.5px;}download-circle
](__GHOST_URL__/content/files/2024/11/GTX680-4GB-ROM.zip)

[

Kepler BIOS Tweaker v1.25

Kepler BIOS Tweaker v1.25.zip

94 KB

.a{fill:none;stroke:currentColor;stroke-linecap:round;stroke-linejoin:round;stroke-width:1.5px;}download-circle
](__GHOST_URL__/content/files/2024/11/Kepler-BIOS-Tweaker-v1.25.zip)

[

Nvidia-Inspector

Nvidia-Inspector.zip

233 KB

.a{fill:none;stroke:currentColor;stroke-linecap:round;stroke-linejoin:round;stroke-width:1.5px;}download-circle
](__GHOST_URL__/content/files/2024/11/Nvidia-Inspector.zip)
