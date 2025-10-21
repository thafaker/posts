---
title: iTunes Restore 4.3.4 / 4.3.5 iPhone 1013 Error TinyUmbrella
slug: itunes-restore-4-3-4-iphone-1013-error-tinyumbrella
date_published: 2011-07-29T21:36:27.000Z
date_updated: 2018-08-22T09:38:34.000Z
---

[**Update**] Was braucht man, um sein iPhone 4 von iOS 4.3.5 auf OS 4.3.3 zurück zu bringen? Warum will man eigentlich auf 4.3.3 zurück gehen? Weil ein untethered Jailbreak nur bis zur 4.3.3 möglich ist.

**Voraussetzung**: Ihr habt eurer SHSH Blobs gesichert. Wie ihr euer Gerät zurück auf eine alte iOS Version bringt, lest ihr [hier](__GHOST_URL__/tiny-umbrella-shsh-sichern-und-wiederherstellen/). Wenn ihr jetzt das iOS korrekt wiederhergestellt habt aber nach dem Neustart des iPhones das iTunes Kabel Symbol seht und iTunes den Fehler 1013 meldet, gehts hier weiter.

Ladet den Recoveryfix [hier](http://thefirmwareumbrella.blogspot.com/) (oder Direktlink [Mac (archiviert)](http://web.archive.org/web/20110610144247/http://cache.firmwareumbrella.com/downloads/fixrecovery-osx.zip) /[Win (archiviert)](http://web.archive.org/web/20150216011714/http://cache.firmwareumbrella.com/downloads/fixrecovery-win.zip)) herunter und entpackt ihn auf dem Desktop.

Nun öffnet ihr das Terminal von OSX und gebt `sudo su` ein. Dann drückt ihr ENTER. Nun müsst ihr das Kennwort von eurem Benutzeraccount eingeben.

Nun nehmt ihr einfach die vorhin herunter geladene und entpackte Datei Names `fixrecovery43` (da sind noch andere Dateien im Ordner, egal) und zieht diese in euer Terminal Fenster. Dort steht nun in etwa folgendes:
[![Bildschirmfoto 2011-09-01 um 19.18.18](//picdump.thafaker.de/2011/07/Bildschirmfoto-2011-09-01-um-19.18.18.png)](http://picdump.thafaker.de/2011/07/Bildschirmfoto-2011-09-01-um-19.18.18.png)

Jetzt müsst ihr euer iPhone in den DFU-Modus bringen. Wie das geht, könnt ihr [hier](__GHOST_URL__/wie-komme-ich-in-den-dfu-mode-iphone-ipod-touch/) nachlesen. Nun drückt ihr im Terminal wieder ENTER und die Software startet. Das Terminal müsste zuerst `Device must be in DFU mode to continue` kurz anzeigen und wenn das Gerät im Recovery ist sofort anfangen, den Fix zu injizieren. Es erscheinen einige Befehle im Terminal und der Rest sollte automatisch ablaufen.

Nach einer kurzen Zeit steht ähnlich kryptisches auf dem iPhone-Display. Dies läuft auch automatisch durch. Nach einer gewissen Zeit sollte dann endlich das wiederhergestellte iPhone booten und euch den Bildschirm zeigen, dass die Sim-Karte gesperrt ist und das Gerät aktiviert werden will. Das könnt ihr tun und nun befindet ihr euch auf dem Homescreen.

Das wars auch schon wieder: euer Gerät ist nun korrekt auf iOS 4.3.3 zurück gesetzt.

Jetzt kann man entweder sein Backup wieder einspielen oder vorher direkt folgenden Artikel lesen, um das Gerät zu Jailbreaken. [Jailbreak iOS 4.3.3](__GHOST_URL__/der-jailbreak-fuer-das-ipad-2-ist-da-jailbreakme-3-0-how-to/)

Wenn nun euer Gerät jailbroken ist und Cydia auf dem Bildschirm steht, könnt ihr folgenden Artikel lesen um [gecrackte IPAs installieren](__GHOST_URL__/wie-installiere-ich-ipa-dateien-auf-meinem-ipodiphone/) zu können.

Danach könnt ihr euer Backup wieder einspielen. Der Vorteil: wenn ihr gecrackte IPAs im Backup habt, werden diese natürlich sogleich korrekt aufgespielt, weil das iPhone neu aufgesetzt, aber bereits mit Cydia und dem Crack versehen ist.

Viel Spaß am Gerät!

---

HINWEIS: Der untere Artikel ist hinfällig und fachlich nicht korrekt.

[**Original**] Für alle, die ein iPhone (oder anderes iDevice besitzen) mit iOS 4.3.4 besitzen und versuchen, mit [TinyUmbrella](__GHOST_URL__/tiny-umbrella-shsh-sichern-und-wiederherstellen/) auf eine frühere iOS Version wie 4.3.3 (wegen des Jailbreaks o.ä.) zurück zu kehren... diesen Personenkreis muss ich leider knallhart enttäuschen. Apple signiert die iOS Version 4.3.4 nicht, das heißt, TinyUmbrella kann kein DFU Image von Apple laden und somit nicht korrekt wieder her stellen, Problem: iTunes meldet nach einem erfolgreichen Restore immer Fehler 1013 den man nicht los wird. Irgendwie braucht TinyUmbrella wohl Firmwares mit gleichem Baseband, dann ist es kein Problem. Weil aber Apple die 4.3.4 nicht signed, ist das quasi was anderes als die 4.3.3 und somit kann nicht zurück gegangen werden. Mit der 4.3.5 ist es genau das gleiche. Shit. Man muss also einfach warten, bis TinyUmbrella aktualisiert wird.
[![Bildschirmfoto 2011-07-29 um 23.31.34](//picdump.thafaker.de/2011/07/Bildschirmfoto-2011-07-29-um-23.31.34-565x580.png)](http://picdump.thafaker.de/2011/07/Bildschirmfoto-2011-07-29-um-23.31.34.png)

Dann klappt es hoffentlich wieder, auch mit 4.3.4 auf 4.3.3 und dann mit nem Jailbreak. *ARGHHH*!

TinyUmbrella 5.00.07 hat ein paar neue Funktionen eingebaut, unter anderem die Möglichkeit, das Baseband nicht zu aktualisieren (um einen eventuellen Unlock per Jailbreak behalten zu können). Wie jedoch bereits erwähnt, kommt dieses neue Baseband Update Feature mit ein paar Haken, welche wir für euch hier nochmals auflisten:

- Erstens, die iOS Version, zu welcher ihr wiederherstellen wollt, wie auch die von Apple zur Zeit aktuelle & noch signierte iOS Firmware, müssen beide das *GLEICHE* Baseband haben. Dies ist sehr wichtig, da sonst das Baseband Update nicht funktioniert und ihr am Ende einer Wiederherstellung den Fehler 10xx erhaltet und somit Fixrecovery benutzen müsst, damit ihr das Gerät aus dem Recovery Loop heraus holen könnt. (Funktioniert beim iPhone 4 - jedoch nicht beim iPad 2)

[**Update**] Ich habe jetzt einfach mal versucht, auf iOS 4.3 zurück zu aktualisieren (Paradoxon). Vorher habe ich diesen Haken "Update Baseband" in TinyUmbrella gesetzt, weil ich ein Werks-Unlocked iPhone 4 habe. Natürlich erschien wieder der 1013 Error, aber diesmal habe ich im Terminal mit Root-Rechten (sudo su) den Recovery-Fix (Download: [Win (archiviert)](http://web.archive.org/web/20150216011714/http://cache.firmwareumbrella.com/downloads/fixrecovery-win.zip) / [OSX (archiviert)](http://web.archive.org/web/20110610144247/http://cache.firmwareumbrella.com/downloads/fixrecovery-osx.zip)) laufen lassen und siehe da, mein iPhone hat sich problemlos auf iOS 4.3 restoren lassen. Dann sofort jailbreakme.com besucht und Cydia installiert, jetzt spielt er gerade das Backup wieder ein. Danach werde ich einfach Schritt-für-Schritt (oder wie NKOTB sangen: Step-by-Step) auf meine gewünschte iOS 4.3.3 Firmware aktualisieren - *Bingo*.

[**Update** #2] Verdammt, man kann nicht Schrittweise aktualisieren. Die einzige Möglichkeit die jetzt besteht, ist, in einem Schritt auf die aktuellste Version, namentlich iOS 4.3.5, zu aktualisieren. Dann würde ich aber wieder den Jailbreak verlieren. *ARGHHHHHH*!
