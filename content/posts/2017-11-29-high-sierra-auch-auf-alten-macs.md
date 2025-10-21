---
title: High Sierra auch auf alten Macs
slug: high-sierra-auch-auf-alten-macs
date_published: 2017-11-29T13:45:04.000Z
date_updated: 2018-08-22T09:37:42.000Z
tags: how to, high sierra, anleitung, apple, osx, mac os, alte macs, howto
---

Viele ältere Macs sind durchaus in der Lage, das aktuelle macOS 10.13 High Sierra gut laufen zu lassen. Jedoch ist Apple auch dafür bekannt, alter Hardware gern von sich aus den Saft abzudrehen. So ist es auch bei High Sierra wieder geschehen. Einer Menge alter Hardware wurde dieses Update verwehrt. 

Jedoch wäre das Netz nicht das Netz, wenn sich genau dieser Problematik nicht ein findiger Hacker annehmen würde, um diesen Misstand zu beseitigen. Und mal ehrlich, wer sieht schon ein auf einem Mac Pro 3.1 mit 20 Gb Ram und SSDs sowie 8 Kernen kein High Sierra laufen lassen zu dürfen?

Und so gibt es mit dem **macOS High Sierra Patch Tool** eine einfache Lösung. Eigentlich ist es nämlich nur eine Prüfroutine des Installationsprogramms, die eine Installation des neuen Systems verhindert – und diese kann man relativ einfach deaktivieren.

![](https://images.unsplash.com/photo-1510843572979-e4b9e790fdd7?ixlib=rb-0.3.5&amp;q=80&amp;fm=jpg&amp;crop=entropy&amp;cs=tinysrgb&amp;w=1080&amp;fit=max&amp;s=d86ae4ef47fb4c1ebabd18feba9666d9)
Photo by [Federica Galli](https://unsplash.com/@fedechanw?utm_source=ghost&amp;utm_medium=referral&amp;utm_campaign=api-credit) / [Unsplash](https://unsplash.com/?utm_source=ghost&amp;utm_medium=referral&amp;utm_campaign=api-credit)

Versucht man, macOS High Sierra auf einem alten Mac zu installieren, verweigert das Installationsprogramm die Durchführung. Mit dem Tool macOS High Sierra Patcher von dosdude1 kann man ein Installationsmedium erstellen, das diese Installationssperre überwindet.

### Anleitung High Sierra Patch Tool

- [Download High Sierra Patch Tool](http://dosdude1.com/highsierra/)

#### Welche Macs kommen in Frage

- Mac Pro ab 2008 (Modell 3.1, 4.1)
- iMacs 8.1 und 9.1
- Macbooks Pro 4.1, 5.1, 5.2, 5.3, 5.4, 5.5.
- Macbook Air ab Ende 2008, das Macbook Air 2.1
- Macbook 5.1
- Mac Mini von Anfang 2009.

1. Zuerst wird der High Sierra Installer aus dem Mac App Store herunter geladen.
2. Dann startet man das Tool. Über ein Auswahlfeld wählt man zunächst den aus dem Store geladenen High-Sierra-Installer sowie einen formatierten USB-Stick (8 GB) oder eine Festplatte aus.
3. Das Tool erstellt ein spezielles Startmedium, das neben dem neuen System auch ein Patch-Tool enthält. Über dieses Spezialmedium kann man nun das heruntergeladene System installieren.
4. Hierzu geht man wie immer vor, man hat den Stick angesteckt, hält beim Boot nach dem Gong die Auswahltaste gedrückt und wählt das USB Medium zur Installation aus.
5. Meines Wissens ist so aber nur ein Clean-Install möglich, die vorhandenen Daten werden gelöscht.
6. Nach der Installation muss man ein zweites Mal über dieses Medium booten und das frisch installierte System „patchen“. Der Hintergrund: Das Tool kann Prüfungen beim Booten deaktivieren und für Unterstützung von HDMI-Audio-Support und USB-Geräten sorgen.
7. Diese Funktion ist in die Oberfläche des Systems integriert und wählt die passenden Voreinstellungen automatisch aus..

#### Bekannte Probleme

> Vor allem ältere Macbooks sind hier betroffen:

- Probleme mit der Helligkeitseinstellung
- Touchpad des Macbook 5.2. wird als Maus erkannt und kann nicht konfiguriert werden.
- WLAN ohne Funktion bei vielen alten Macbooks — hier fehlen High Sierra die Treiber (kein Problem bei Ethernet); eventuell Abhilfe mit kext Files, also Treibern alter OSX Installationen, die man in High Sierra überträgt (ungetestet)

---

Eventuell auch nützlich: [Bootbaren USB Stick für macOS High Sierra erstellen](__GHOST_URL__/macos-high-sierra-bootbaren-usb-stick-erstellen/).
