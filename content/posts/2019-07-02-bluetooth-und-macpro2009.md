---
title: Bluetooth Upgrade am MacPro 4,1 und 5,1 ab 2009
slug: bluetooth-und-macpro2009
date_published: 2019-07-02T16:11:07.000Z
date_updated: 2024-03-30T15:58:32.000Z
tags: cMP, bigmac, bluetooth 4.0, bluetooth, howto, anleitung
---

Liebe Kolleginnen und Kollegen, wie Sie alle wissen besitze ich einen MacPro5,1, der mir auch nach der Vorstellung vom [MacPro 2019](__GHOST_URL__/macpro7-1-die-neue-kasereibe/) immer noch sehr sehr gut gefällt. So gut, als dass ich auch immer noch mal etwas Geld in die Hand nehme, um ihn aufzurüsten. Das habe ich neulich zum Beispiel mit der CPU ([Link](__GHOST_URL__/how-to-delid-and-upgrade-your-macpro-4-1-cpus/)), dem Arbeitsspeicher ([Link](__GHOST_URL__/als-ich-neulich-den-arbeitsspeicher-erweiterte/)) oder einer NVMe-SSD ([Link](__GHOST_URL__/nvme-ssd-in-macpro4-1/)) getan. Alle Artikel zu meinem classicMacPro (cMP) finden Sie übrigens unter dem Tag: [BigMac](__GHOST_URL__/tag/bigmac/) :-)

![thahipster.de MacPro](__GHOST_URL__/assets/2019/02/cinema2.jpg)

Und heute ist es mal wieder so weit. Allerdings ist das Upgrade furchtbar klein. Die Rede ist von meinem Bluetooth-Adapter. Ich habe in meinem MacPro selbstverständlich ein original Apple-Bluetooth-Modul eingebaut. Dieses funktioniert auch ganz gut. Jedoch ist es mittlerweile recht betagt. Es unterstützt zum Beispiel nur Bluetooth 2.0, die Reichweite, gerade für meine Mighty Mouse, lässt sehr zu wünschen übrig und natürlich unterstützt es auch keine besseren Audio-Codecs, wie sie heute in Bluetooth-Headsets Standard sind -und erst recht kein *Bluetooth Low Energy*, wie es viele neuere Geräte nutzen. Kurzum, ich möchte Abhilfe.

Nach kurzer Recherche im Netz gibt es durchaus kommerzielle Anbieter, die ein Nachrüstkit für den MacPro anbieten, welches das Originale so originalgetreu wie möglich mit einem aktuellen Modul ersetzt. Allerdings kostet dies ca. $ 175, was ich nun doch nicht bereit bin zu investieren, plus den Versandkosten aus den USA. Nun denn, in diversen Foren wird ein günstiger kleiner USB 2.0 Bluetooth Dongle erwähnt, den ich mir näher ansah. Gemeint ist hier der **ASUS USB-BT400** (Bluetooth 4.0 USB) Adapter (dies ist kein Affiliate-Hinweis, wir verdienen kein Geld damit), den man für circa 10 € überall bekommt. Er funktioniert am Mac Pro Out-Of-The-Box und wird sofort erkannt. Allerdings haben wir den alten Adapter nicht ausgebaut, sodass macOS weiterhin den alten Bluetooth-Adapter verwendet und den neuen USB-Dongle zwar brav installiert, aber nicht als Default einbindet.

Hier schafft nun ein Befehl im Terminal Abhilfe, der macOS sagt, dass es fortan den USB-Dongle als Hauptbluetoothgerät nutzen soll und den anderen ignoriert, solange der Stick angesteckt ist.

Öffnet dazu die Terminal.app und gebt folgende Befehl, nach dem § ein.

`Jans-Big-Mac:~ $ sudo nvram bluetoothHostControllerSwitchBehavior=always`

Nach dem Befehl müsst ihr euer Passwort eingeben, neustarten und fortan nutzt macOS den USB-Stick. Bei mir funktioniert das ziemlich gut.

Im folgenden Screenshot seht ihr, wie es aussehen sollte. HCI-Version und LMP-Version sind die beiden richtigen Indikatoren: HCI-Version 4.0 sagt, dass er Bluetooth 4.0 nutzt (0x6), das alte Modul würde hier nur 2.0 (0x4) anzeigen. Mein neuer Stick ist also korrekt eingebunden.
![](__GHOST_URL__/content/images/2019/07/bluetooth.png)HCI-Version 4.0 sagt, dass er Bluetooth 4.0 nutzt (0x6)
Da der MacPro nun zwei Bluetooth-Geräte hat, müssen auch alle Geräte neu gepaired werden. Das heißt, der USB-Dongle kennt erst mal keine Geräte und ihr müsst Tastatur, Maus und Headset erneut verbinden. 

Ich nutze übrigens die Apple Alu Kabel-Tastatur ([Link](https://www.google.com/search?q=apple+a1243+deutsch&amp;client=safari&amp;rls=en&amp;source=lnms&amp;tbm=isch&amp;sa=X&amp;ved=0ahUKEwiot8qd0ZbjAhXP6aQKHSK3DjAQ_AUIESgC&amp;biw=1222&amp;bih=1010)), welche an der Seite zwei USB-Anschlüsse hat. In einem der beiden Anschlüsse steckt nun unsichtbar der USB-Bluetooth-Dongle. Das funktioniert problemlos und ist nur zu empfehlen. Ansonsten kann der Dongle aber auch am Mac selber angesteckt werden. Wenn man einen Bildschirm mit USB-Hub nutzt, kann man den Stick auch hier "verstecken". 

![](__GHOST_URL__/content/images/2019/07/IMG_5491-1.JPG)

![](__GHOST_URL__/content/images/2019/07/IMG_5494.JPG)

Apple Alu Keyboard mit USB-Anschluss - ASUS BT Dongle

Nachteile sind mir durch meine USB-Lösung bisher nicht entstanden. Wie es sich allerdings mit Features wie Hand-Off ([Link](https://support.apple.com/de-de/guide/mac-help/mchl732d3c0a/mac)) verhält, kann ich nicht genau sagen. Die Telefonfunktion funktioniert bei mir problemlos, also wenn mein iPhone ein Gespräch bekommt, kann ich es am Mac Pro annehmen. Aber für Apps die auf einem anderen Gerät laufen und am Mac Pro weiter geführt werden sollen, ist auch noch eine moderne Wifi-Karte notwendig, die mein Mac nicht besitzt. Ich betreibe ihn mit LAN-Kabel. Hier gibt es eine [Diskussion mit Lösungsvorschlägen](https://www.macuser.de/threads/bluetooth-4-0-und-wlan-ac-auf-mac-pro-5-1-2010.746021/) diesbezüglich.

### Bekannte Probleme

Mein MacPro vergisst nach längerer stromloser Zeit manchmal, dass er den USB-Dongle nutzen soll. Das merke ich immer dann, wenn meine Maus mal wieder ruckelt.  Dann hat er nämlich auf die interne Bluetooth-Karte umgeschaltet. Eine Eingabe des obigen Befehls zum SwitchBehavior löst das pRoblem jedoch sofort.
