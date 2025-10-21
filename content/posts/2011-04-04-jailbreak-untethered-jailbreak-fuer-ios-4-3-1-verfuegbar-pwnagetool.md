---
title: [Jailbreak] Untethered Jailbreak für iOS 4.3.1 verfügbar (PwnageTool) HOW TO für OS X und Windows
slug: jailbreak-untethered-jailbreak-fuer-ios-4-3-1-verfuegbar-pwnagetool
date_published: 2011-04-04T08:03:30.000Z
date_updated: 2018-08-22T09:38:38.000Z
---

Mit dem soeben veröffentlichten **PwnageTool 4.3** sowie **redsn0w 0.9.6 RC 9** gibt es den ersten **untethered Jailbreak** für **iOS 4.3.1** Dies ist übrigens ein [Jubiläum (archiviert)](http://web.archive.org/web/20110405165947/http://blog.iphone-dev.org:80/post/4332841631/three-years-of-pwnage-tool), denn vor genau drei Jahren auf den Tag genau präsentierte das DevTeam den ersten Jailbreak, damals noch für Firmware 1.1.4 Einen Unlock für iOS 4.3.1 gibt es allerdings noch nicht, weshalb das *DevTeam* von einem Update abrädt, wenn man darauf angewiesen ist.

---

WERBUNG

---
!function(d, s, id) {
    var js, pjs = d.getElementsByTagName(s)[0];
    if (d.getElementById(id)) return;
    js = d.createElement(s);
    js.id = id;
    js.src = "http://player-services.video-loader.com/embed-code/index/find?placementVersionId=283349451331035606369755";
    pjs.parentNode.insertBefore(js, pjs);
}(document, 'script', 'gv_script_283349451331035606369755');
---

**redsn0w 0.9.6 RC 9** und **PwnageTool 4.3** unterstützen:

- **iPhone 3GS**
- **iPhone 4 (GSM/Europa-Version; nicht das Verizon-CDMA-iPhone 4)**
- **iPod touch 3**
- **iPod touch 4**
- **iPad 1**
- **AppleTV 2 (nur PwnageTool)**

Für das iPad 2 gibt es momentan noch keinen funktionierenden Exploit, *limera1n* und *SHAtter* können nicht auf das iPad2 angewendet werden, das DevTeam sucht aber nach einer Möglichkeit.

**Downloads**:

- [**redsn0w 0.9.6rc9 für Mac**](https://sites.google.com/a/iphone-dev.com/files/home/redsn0w_mac_0.9.6rc9.zip?attredirects=0&amp;d=1) (12.1 MiB)
iOS 4.3.1 untethered Jailbreak für Mac
- [**redsn0w 0.9.6rc9 für Windows**](https://sites.google.com/a/iphone-dev.com/files/home/redsn0w_win_0.9.6rc9.zip?attredirects=0&amp;d=1) (29.2 KiB)
Untethered iOS 4.3.1 Jailbreak für Windows
- [**PwnageTool 4.3 für OS X** (archiviert)](http://web.archive.org/web/20110407025154/http://torrents.thepiratebay.org:80/6293151/PwnageTool_4.3.dmg.6293151.TPB.torrent) (*.torrent 28.6 MiB)
Untethered iOS 4.3.1 Jailbreak für OS X. Erstellt gejailbreakte Firmware  welche anschließend mittels iTunes aufs jeweilige Device installiert  wird
- [**sn0wbreeze 2.5 für Windows** (archiviert)](http://web.archive.org/web/20110407143139/http://hotfile.com:80/dl/113251417/0fb726d/sn0wbreeze-v2.5.zip.html) (32.8 MiB)
Untethered iOS 4.3.1 Jailbreak für Windows. Erstellt gejailbreakte  Firmware welche dann mittels iTunes auf das Device installiert wird.

## How To Jailbreak für Windows

Übrigens funktioniert der Jailbreak und diese Anleitung unter *OS X* und *Windows* absolut identisch, weil es die Software **redsn0w** für beide Betriebssysteme gibt. Für Windows benutzt man einfach [diese Version von Redsn0w](https://sites.google.com/a/iphone-dev.com/files/home/redsn0w_win_0.9.6rc9.zip?attredirects=0&amp;d=1), sonst bleibt alles gleich. *Und jetzt geht es endlich los...*
## How To untethered Jailbreak iDevice mit iOS 4.3.1

- **Schritt 1**: Wir sichern das iPhone (in meinem Fall führe ich dieses Tutorial mit einem iPhone 4 durch) mit iTunes, Rechtsklick "Sichern" auswählen.
![0_sicherung_itunes](//picdump.thafaker.de/2011/04/0_sicherung_itunes.png)
- **Schritt 2**: Die richtige Firmware herunter laden die für unser Gerät passt: Wenn man ein [iPhone 4 hat, ist es diese Datei](http://appldnld.apple.com/iPhone4/041-0551.20110325.Aw2Dr/iPhone3,1_4.3.1_8G4_Restore.ipsw), alle anderen können [hier](http://www.felixbruns.de/iPod/firmware/) schauen.
- **Schritt 3**: Jetzt in *redsn0w* die iOS Firmware Datei auswählen:
[![1](//picdump.thafaker.de/2011/04/1-150x150.png)](http://picdump.thafaker.de/2011/04/1.png)[![2](//picdump.thafaker.de/2011/04/2-150x150.png)](http://picdump.thafaker.de/2011/04/2.png)
- **Schritt 4**: Wenn die Datei passt, meldet uns redsn0w dies.
[![3](//picdump.thafaker.de/2011/04/3-150x150.png)](http://picdump.thafaker.de/2011/04/3.png)
- **Schritt 5**: Auf "next" klicken. redsn0w lädt nun die Kernel-Erweiterungen und den untethered-Kram in die Firmware hinein:
![4](//picdump.thafaker.de/2011/04/4.png)
- **Schritt 6**: Jetzt erscheint eine Meldung, dass wir mit dem iPhone 4 keine Custom-Logos (eigene Boot-Logos anstelle des Apple-Zeichens) verwenden können: macht nix. Wir lassen das so und klicken auf "next".
[![5](//picdump.thafaker.de/2011/04/5-150x150.png)](http://picdump.thafaker.de/2011/04/5.png)
- **Schritt 7**: Jetzt weist uns redsn0w darauf hin, dass unser iPhone ausgeschaltet und an den Mac angeschlossen sein sollte: dieser Auffordernugn kommen wir nach.
- **Schritt 8**: Nun müssen wir das Gerät in den DFU-Modus bringen, dies tun wir so [wie in dieser Anleitung](__GHOST_URL__/wie-komme-ich-in-den-dfu-mode-iphone-ipod-touch/) beschrieben!
- **Schritt 9**: Wenn das Gerät im DFU-Modus ist, erkennt diesen Umstand redsn0w sofort und fängt an, sein Voodoo durchzuführen. Es führt den Exploit aus, lädt Dateien in das iPhone, startet das iPhone neu (Bildschirm wird weiß), dann folgt auf dem iPhone Display ein bisschen Linux-Code (hier wird nun der Jailbreak-Code etabliert und injiziert und ausgeführt) und dann (ihr seht vorher noch mal die berühmte Ananas) ist euer Gerät schon jailbroken und sollte sich mit eurem Hintergrundbild melden... thats all.
[![8](//picdump.thafaker.de/2011/04/8-150x150.png)](http://picdump.thafaker.de/2011/04/8.png)[![10](//picdump.thafaker.de/2011/04/10-150x150.png)](http://picdump.thafaker.de/2011/04/10.png)
- **Schritt 10**: Gibt es nicht, ihr habt ein jailbroken iPhone 4 und auf dem zweiten Homebildschirm das Symbol von Cydia
- ***Viel Spaß am Gerät!***

Jetzt könnt ihr zum Beispiel den Hackulo.US Crack aufspielen um [gecrackte IPAs auf dem iPhone laufen zu lassen](__GHOST_URL__/wie-installiere-ich-ipa-dateien-auf-meinem-ipodiphone/), wie das geht steht [hier](__GHOST_URL__/wie-installiere-ich-ipa-dateien-auf-meinem-ipodiphone/).

## **Bekannte Probleme**

- Viele Nutzer klagen über ein Problem mit der Empfangsanzeige, sie hätten nur noch einen Balken. Das iPhone-Dev-Team [bestätigt (Link nicht mehr verfügbar)](http://cl.ly/150l1s1V1o3t111O0H42) diesen Fehler und wird eine aktualisierte Version von redsn0w nach ein paar Tests heraus bringen.
[![Bildschirmfoto 2011-04-06 um 09.29.18](//picdump.thafaker.de/2011/04/Bildschirmfoto-2011-04-06-um-09.29.18-150x150.png)](http://picdump.thafaker.de/2011/04/Bildschirmfoto-2011-04-06-um-09.29.18.png)
- nichts weiter...

Ein kurzes Video zum HowTo gibt es hier:
