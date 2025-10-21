---
title: HSTWB Installer unter WinUAE
slug: hstwb-installer-unter-winuae
date_published: 2024-01-26T10:25:50.000Z
date_updated: 2024-01-26T12:31:31.000Z
tags: HSTWB, anleitung, howto, how to, amiga os 3.2, winuae, vintage computing, whdload
---

In diesem Artikel beschreibe ich den Weg, wie man den HSTWB Installer konfigurieren muss und was die einzelnen Einstellungsmöglichkeiten bedeuten, damit wir am Ende ein lauffähiges Amiga OS auf unserem 16 GB Image vorfinden, welches wir dann auf die CF-Karte übertragen können, um es in den echten Amiga einzusetzen.
![](__GHOST_URL__/content/images/2024/01/Bildschirmfoto-2024-01-26-um-11.25.23.png)
## Table of Contents

1. [HSTWB: Installiere WHDLoad unter AMIGA OS für AMIGA 1200 via WinUAE](__GHOST_URL__/installiere-whdload-unter-amiga-os-3-1-4-fur-amiga-1200/)
2. **HSTWB Installer clickthrough unter WinUAE**

---

### **HSTWB Installer clickthrough unter WinUAE**

Im ersten Teil dieser zwei Artikel haben wir alles vorbereitet, jetzt haben wir WinUAE gestartet und laufen durch den Setup Prozess. Kurz zu meiner Situation hier:

- Amiga 1200 mit Turbokarte und 128 MB Ram
- WHDLoad mit Spielen
- Kickrom 1.3, 3.1 und 3.2
- AmigaOS 3.2
- WinUAE unter Windows 11

Es ist natürlich auch ein Amiga 500 möglich, es gibt zwei Startfiles for WinUAE respektive FSUAE, ich wählte zum Start A1200.

**Lets go**

Drückt Enter
![](__GHOST_URL__/content/images/2024/01/Bildschirmfoto-2024-01-26-um-09.22.50.png)
HSWTB durchsucht nun die in [Artikel 1](__GHOST_URL__/installiere-whdload-unter-amiga-os-3-1-4-fur-amiga-1200/) gefüllten Ordnern nach den Installationsdisketten. Ich habe mein Amiga OS 3.2 legal erworben und verfüge dadurch über alle ADF Diskettenimages, die ich hinein kopiert habe. Diese wird er finden und für die Installation nuten. Denkbar ist hier auch Amiga OS 3.0, 3.1…

![](__GHOST_URL__/content/images/2024/01/Bildschirmfoto-2024-01-26-um-09.22.55.png)

![](__GHOST_URL__/content/images/2024/01/Bildschirmfoto-2024-01-26-um-09.23.29.png)HSTWB hat Amiga OS 3.2 gefunden. ![](__GHOST_URL__/content/images/2024/01/Bildschirmfoto-2024-01-26-um-09.23.47.png)MD5 only reicht, sonst braucht er unfassbar lange.![](__GHOST_URL__/content/images/2024/01/Bildschirmfoto-2024-01-26-um-09.24.06.png)Er hat mein Amiga OS 3.2 erkannt und wird dieses installieren.![](__GHOST_URL__/content/images/2024/01/Bildschirmfoto-2024-01-26-um-09.24.11.png)Da ich einen A1200 nutze, installiere bitte auch die Module dafür. Das ändert sich je nach Maschine.
Im nächsten Schritt sucht er nach den Kickroms, die wir bereit stellen. Wir erinnern uns, dass das Amiga OS auf ROM-Bausteinen und den Disketten basiert. Ich habe das legale 3.2 Kickrom mit dem Kauf erworben, weiterhin konnte ich aus meinem Amiga 500 das Kickrom mit einem Tool extrahieren, ebenso das Amiga OS 3.1 Kickrom, welches ursprünglich be meinem Amiga 1200 dabei war. Dafür gibt es viele [Anleitungen](http://ale.emuunlim.com/guides/get-kick-rom.shtml) im Netz. Natürlich kann man sich die Kickroms sicher auch irgendwo herunter laden, wenn man danach sucht.
![](__GHOST_URL__/content/images/2024/01/Bildschirmfoto-2024-01-26-um-09.24.22.png)![](__GHOST_URL__/content/images/2024/01/Bildschirmfoto-2024-01-26-um-09.24.56.png)Ja, Farben installieren, Glow Icons sind schön.![](__GHOST_URL__/content/images/2024/01/Bildschirmfoto-2024-01-26-um-09.25.00.png)Das möchte ich persönlich nicht, denn interlaced flimmert so extrem auf meinem 1084S Monitor, dass ich sofort Augenkrebs bekommen würde. Ich sage hier nein, ihr dürft auch Ja sagen.![](__GHOST_URL__/content/images/2024/01/Bildschirmfoto-2024-01-26-um-09.25.32.png)Er beginnt mit der Installation von Amiga OS 3.2 indem er automatisch alle Disk-Images durchgeht und installiert.
Danach wird er neu starten und euch mitteilen, dass er dafür 10 Sekunden wartet, damit auch wirklich alle Schreibvorgänge abgeschlossen sind. Dort drückt ihr ENTER.
![](__GHOST_URL__/content/images/2024/01/Bildschirmfoto-2024-01-26-um-09.25.56.png)
Danach startet die **Package-Installation**, also die grundlegende Software. Hier kann man entscheiden ob man die ClassicWB möchte, EAB WHLoad (Nur die Menüsoftware, nicht WHDLOAD selbst). Ich selbst installiere ClassicWB FULL auf mein Amiga OS 3.2
![](__GHOST_URL__/content/images/2024/01/Bildschirmfoto-2024-01-26-um-09.26.19.png)
Er wird wieder einen Neustart durchführen. Danach startet die **Userpackage Installation**, die zusätzliche Software. Ich wähle folgende Dinge aus (ganz unten  - wenn ihr scrollt - seht ihr gerade nicht WHDLoad, wählt beide Pakete): 
![](__GHOST_URL__/content/images/2024/01/Bildschirmfoto-2024-01-26-um-09.33.40.png)Ganz unten seht ihr noch WHDLoad, wählt beide Pakete.
Er wird während der Installation immer mal wieder nach einer Prozessoroptimierung fragen, denn er kann verschiedene Software abgestimmt für die CPUs installieren. Mein Amiga hat einen 68020 Prozessor, den ich dann auswähle. Nutzt ihr einen Amiga 500, ist es der 68000. ZIP und Packer laufen damit (wohl optimierter und) schneller.
![](__GHOST_URL__/content/images/2024/01/Bildschirmfoto-2024-01-26-um-09.33.51.png)
Irgendwann kommt die **WHDLoad**-Installation. Hier wählt ihr im bekannten Modus die Sprachen und ob OCS oder/und AGA Versionen der Spiele installiert werden sollen. Je nachdem wie viele WHDLoad Spiele ihr habt, kann dieser Schritt sehr lange dauern, denn er entpackt und installiert jedes einzelne Spiel an die richtige Stelle. Ein toller Service. 
![HSTWB installer installiert WHDLoad und die Spiele](__GHOST_URL__/content/images/2024/01/Bildschirmfoto-2024-01-26-um-12.35.19.png)HSTWB installer installiert WHDLoad und die Spiele

💡

Sicher findet ihr auch hier ein ganzes Paket an Spielen für WHDLoad im Netz, bedenkt jedoch, dass ihr im Besitz der originalen Disketten sein müsst, sonst installiert ihr Raubsoftware.

![HstWB: WHDLoad installiert Demos](__GHOST_URL__/content/images/2024/01/Bildschirmfoto-2024-01-26-um-13.30.51.png)

![](__GHOST_URL__/content/images/2024/01/Bildschirmfoto-2024-01-26-um-13.15.19-1.png)

Nach WHDLoad Games und Demos folgen noch ein paar weitere Installationen, je nachdem was ihr in den *Userpackages* gewählt habt. Ist dies abgeschlossen folgt abermals ein Reboot und das System startet mit eurem neuen Amiga OS 3.2 inklusive ClassicWB Full. Jetzt könnt ihr damit rum  spielen und ggf. weitere Software in WinUAE auf das Image installieren. Dann könnt ihr zurück zu [Teil 1 switchen](__GHOST_URL__/installiere-whdload-unter-amiga-os-3-1-4-fur-amiga-1200/), um das Image auf die CF-Karte zu schreiben.
[

HSTWB: Installiere WHDLoad unter AMIGA OS für AMIGA 1200 via WinUAE

Dies wird ein etwas längerer Artikel in welchem ich beschreibe, wie man WHDLoad und AMIGA OS 3.2 auf einer CF-Card installiert. Ich nutze dafür das großartige Toolset HSTWB Installer und erkläre zu Beginn, wie dieser konfiguriert wird.

![](__GHOST_URL__/content/images/size/w256h256/2019/06/logo.png)thahipster.deHerr Montag

![](https://images.unsplash.com/photo-1661793422829-e1f648ab4a15?crop=entropy&amp;cs=tinysrgb&amp;fit=max&amp;fm=jpg&amp;ixid=M3wxMTc3M3wwfDF8c2VhcmNofDR8fGFtaWdhfGVufDB8fHx8MTcwNjE3OTA5MHww&amp;ixlib=rb-4.0.3&amp;q=80&amp;w=2000)
](__GHOST_URL__/installiere-whdload-unter-amiga-os-3-1-4-fur-amiga-1200/)
*Viel Spaß am Gerät*. Bei Fragen schreibt gern in die Kommentare.
