---
title: Asus Router Firmware Recovery Apple Mac OSX
slug: asus-router-firmware-recovery-apple-mac-osx
date_published: 2015-01-24T20:46:53.000Z
date_updated: 2018-08-22T09:38:58.000Z
---

**Auf eigene Gefahr**!
![asus rt-n56u](//picdump.thafaker.de/2015/01/asus-rt-n56u-100x100.png)Wenn ihr diesen Artikel lest, dann habt ihr eventuell auch einen schicken Asus Router, so wie ich bswp. einen *Asus RT-N56U* - und damit ein Problem. Mir ist beim Versuch des Flashens der Firmware der Browser abgestürzt und seitdem tut sich nichts mehr mit dem Router, kein Netzwerk, kein Internet, kein Wlan. 

Indikator für ein größeres Problem ist, dass weder Power On / Off noch ein Reset etwas brachten. Vielmehr blinkt unten nur noch eine einzelne LED langsam vor sich hin, sonst geschieht nichts. Dieses Verhalten beschreibt den Safe-Mode, Notfallmodus des Routers.

Asus sieht für diesen Fall ein Recovery-Tool vor (hier gehts zur [Anleitung für Windows](http://www.manualslib.com/manual/415038/Asus-Rt-N56u.html?page=47)), mit dem man ausschließlich unter Windows eine Firmware in das Gerät laden kann, sodass dieser diese Firmware dann "installiert". WINDOWS. Ausschließlich. Und das ist das Problem für mich, denn ich habe kein Windows. Also folgt nun eine Anleitung, wie man das mit Windows machen kann. Übrigens: Unten gibt es für die erfahrenen User einen Kurzanleitung.

### How To Asus Router Recovery OS X Terminal ausführlich.

1. Ihr braucht auf jeden Fall eine funktionierende Firmware. Ladet euch diese von dieser [Asus-Website](http://www.asus.com/microsite/2014/networks/routerfirmware_update/) für euren Router herunter.
2. Zieht alle Kabel vom Router ab.
3. verbindet den Mac mit dem Asus über Cat5-Netzwerkkabel und steckt es im Router an Port 1 ((nicht in den WAN / Internetport, sondern den normalen Switch Port 1))
4. Geht auf dem Mac über "Systemeinstellung" --> "Netzwerk" in eure Netzwerkeinstellungen und stellt folgendes ein: IP Adresse: 192.168.1.20 Netzmaske: 255.255.255.0 Rest: leer.
[![osx_10.9_netzwerk_einstellungen](//picdump.thafaker.de/2015/01/osx_10.9_netzwerk_einstellungen-100x100.png)](http://picdump.thafaker.de/2015/01/osx_10.9_netzwerk_einstellungen.png)
5. Öffnet die Terminal.app und geht in den Ordner, wo ihr die Firmware gespeichert habt. Zum Beispiel im Ordner Downloads.
`cd ~/Downloads`
6. gebt folgenden Befehl ein: `ping 192.168.1.1`
7. Hier sollte es eine Antwort geben.
`jans-air:~ thafaker$ ping 192.168.1.1
PING 192.168.1.1 (192.168.1.1): 56 data bytes
64 bytes from 192.168.1.1: icmp_seq=0 ttl=64 time=47.801 ms`
8. gebt nun folgende Befehle ein: `tftp`
dann nachfolgend gebt ihr ebenfalls folgende befehle ein, allerdings immer nur den Part, den ich in die beiden * * geschrieben habe, ohne das "tftp>": 
`tftp> **timeout 6000**` ENTER drücken
`tftp> **connect**` ENTER drücken
`(to) **192.168.1.1**` ENTER drücken
`tftp> **binary**` ENTER drücken
`tftp> **put RT-N56U_3.4.3.9-091_base.trx**` (hier den Namen der Firmware die ihr geladen habt).
Das wars, dann sollte folgende Meldung kommen.
`Sent 7161955 bytes in 3.7 seconds` (erfolgreich übertragen)
`tftp> **quit**`
9. Jetzt ist die Firmware auf den Asus übertragen. Wartet etwas, circa 5 Minuten, damit sie installiert werden kann. 
10. Mein Router startete dann automatisch neu und stand nun wieder normal mit Web-Interface zur Verfügung, die anderen LEDs leuchteten auch wieder wie vorher. Jetzt konnte ich mich wieder einloggen, die Einstellungen vornehmen und alles war super.

#### bekannte Probleme.

F: Ping af 192.168.1.1 funktioniert nicht.

A: Es kann sein, dass der Router noch die IP von vorher hat, die ihr mal eingestellt habt. Versucht es damit.

F: Ping funktioniert immer noch nicht.

A: Über Paket Spoofing habe ich gemerkt, dass mein Router in den ARPs immer was von 192.168.1.11 wollte. Also habe ich meine IP auf diese eingestellt, dann ging es.

F: Ping funktioniert immer immer noch nicht.

A: Versucht es trotzdem mit den lftp-Befehlen! Bei mir gab es auch keine Rückmeldung bei PING, aber ich konnte die Datei trotzdem in den Asus laden, versucht es einfach.

F: Egal was ich tue, es geht einfach nicht.

A: Eventuell ein Garantiefall, da kann man nichts machen.

([via](http://www.chrishardie.com/2013/02/asus-router-firmware-windows-mac-linux/))
