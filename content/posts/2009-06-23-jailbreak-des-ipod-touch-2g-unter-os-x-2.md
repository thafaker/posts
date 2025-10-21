---
title: Jailbreak des iPod Touch 2G mit Firmware 3.0 unter OS X
slug: jailbreak-des-ipod-touch-2g-unter-os-x-2
date_published: 2009-06-23T11:45:36.000Z
date_updated: 2018-08-22T09:39:21.000Z
---

---
**ACHTUNG** liebe(r) LeserInnen: Hier gibt es [eine Seite (archiviert)](http://web.archive.org/web/20091107130920/http://thafaker.de:80/iphone-ipod) mit allen Artikeln die zum Thema iPhone, iPod, Jailbreak, IPA und so weiter existieren.

---

---

.
.
**Weiter mit dem Artikel:**[![ipt2g](//picdump.thafaker.de/2009/06/ipt2g1.jpg)](http://picdump.thafaker.de/2009/06/ipt2g1.jpg)Nachdem ja nun diese lang ersehnte und auch weit besprochene [**Firmware 3.0**](http://www.apple.com/de/iphone/softwareupdate/) für **Iphone** und **iPod Touch** in aller Munde (oder auf Jedermanns Device) ist, kam natürlich auch in mir der Wunsch auf, diese Version zu testen.

Aber weit gefehlt, diese *UnJungs®* von Apple verlangen doch tatsächlich 7,99 Euro damit man die neue Software installieren kann. *Krass*! Sicher kann man argumentieren, dass ein Update von Windows Vista auf (7) Seven auch Geld kosten würde und so, aber hier geht es um einen MP3-Player der an sich schon mit einem extrem hohen Preis zu Buche schlägt und über kostenpflichtige Software-Zusätze ständig neues Geld in die Kassen spült. Also *Pustekuchen*? **Na klar**!

Jetzt erinnerte ich mich nämlich an meine alten Jailbreaking-Versuche mit dem damals noch sehr wackeligen **rednsn0w** welches bei jedem Neustart des iPod erneut durchgeführt werden mussten, mit Terminal und auch nur möglich bei speziell installierten USB-Kernel-Erweiterungen. Aber selbst das klappte damals.

Und diesmal? Schnell fand ich heraus, dass man folgende (fett) Dateien *für OS X* brauchen würde.

**Voraussetzungen:**

- **[iTunes 8.2](http://www.apple.com/de/itunes/download/)** (*77,3* MiB)
- [redsn0w 0.7.1 Windows (archiviert)](http://web.archive.org/web/20090625025048/http://uploaded.to:80/file/czintn) (*11,9* MiB)
- [r (archiviert)](http://web.archive.org/web/20090626115059/http://uploaded.to:80/file/yf29gt)**[edsn0w 0.7.2 Mac OS X (archiviert)](http://web.archive.org/web/20090626115059/http://uploaded.to:80/file/yf29gt)** (*15,8* MiB)
- [iPhone 3G Firmware 3.0](http://www.felixbruns.de/iPod/firmware/) (*230,1* MiB)
- [iPhone 2G Firmware 3.0](http://www.felixbruns.de/iPod/firmware/) (*229,3* MiB)
- [iPod Touch 1G Firmware 3.0](http://www.felixbruns.de/iPod/firmware/) (*231,2* MiB)
- **[iPod Touch 2G](http://www.felixbruns.de/iPod/firmware/)**[http://www.felixbruns.de/iPod/firmware/](http://www.felixbruns.de/iPod/firmware/)**[Firmwar](http://www.felixbruns.de/iPod/firmware/)**[e ](http://www.felixbruns.de/iPod/firmware/)**[3.0](http://www.felixbruns.de/iPod/firmware/)** (*257,8* MiB)

Also iTunes aktualisieren, redsn0w laden, IPT2G Firmware 3.0 laden und weiter gehts... Bevor man so wie auf den folgenden Bildern vorgehen kann, muss man den iPod allerdings *händisch* über die Wiederherstellungsfunktion von iTunes auf die Firmware 3.0 aktualisieren. Man schließt dazu den iPod via USB an und klickt im iTunes mit gedrückter ALT-Taste (für Menschen wie **[Soulexx](__GHOST_URL__/23/jailbreak-des-ipod-touch-2g-unter-os-x/comment-page-1#comment-35334)**: unter Windows ist es die **SHIFT**-Taste) auf "Wiederherstellen" und wählt jetzt im Finder die Datei `iPod2,1_3.0_7A341_Restore.ipsw`. Dies muss man tun, weil redsn0w nur die bereits aufgespielte FW aktualisiert, also sollte bereits ein 3.0 auf dem iPod laufen bevor man *jailbreaken* möchte. Dauert übrigens ne ganze Weile, danach kann man noch seine Daten wiederherstellen, sprich, das letzte Backup (legt iTunes automatisch an) einspielen und dann: weiter wie auf den Bildern.

[![ipt2g_fw3.0#1](//picdump.thafaker.de/2009/06/ipt2g_fw3.01.jpg)](http://picdump.thafaker.de/2009/06/ipt2g_fw3.01.jpg)

[![ipt2g_fw3.0#2](//picdump.thafaker.de/2009/06/ipt2g_fw3.02.jpg)](http://picdump.thafaker.de/2009/06/ipt2g_fw3.02.jpg)

[![ipt2g_fw3.0#3](//picdump.thafaker.de/2009/06/ipt2g_fw3.03.jpg)](http://picdump.thafaker.de/2009/06/ipt2g_fw3.03.jpg)

[![ipt2g_fw3.0#4](//picdump.thafaker.de/2009/06/ipt2g_fw3.04.jpg)](http://picdump.thafaker.de/2009/06/ipt2g_fw3.04.jpg)

[![ipt2g_fw3.0#5](//picdump.thafaker.de/2009/06/ipt2g_fw3.05.jpg)](http://picdump.thafaker.de/2009/06/ipt2g_fw3.05.jpg)

[![ipt2g_fw3.0#6](//picdump.thafaker.de/2009/06/ipt2g_fw3.06.jpg)](http://picdump.thafaker.de/2009/06/ipt2g_fw3.06.jpg)

Nach einigen Meldungen im Redsn0w-Fenster sollte der iPod neu starten und wahrscheinlich dieses Bild angezeigt werden.
![IMG_1615](//picdump.thafaker.de/2009/06/IMG_1615-300x150.jpg)
Nach einem erneuten Reboot folgt die berühmte **Redsn0w-Ananas** und der iPod lädt erneut Daten.
![22062009(001)](//picdump.thafaker.de/2009/06/22062009001-1024x768.jpg)
Und ich glaube, das sollte es bereits gewesen sein. Wenn euer iPod jetzt noch mal neu startet, müsste eigentlich ganz normal **Firmware 3.0** booten, leicht zu erkennen an der Batterie-Prozent-Anzeige neben dem Batterie-Symbol und der Suchfunktion. (Bluetooth lässt sich nun auch An/Abschalten, hat aber noch keine richtige Funktion irgendwie)

[![Batteriesymbol_Prozent](//picdump.thafaker.de/2009/06/Batteriesymbol_Prozent.PNG)](http://picdump.thafaker.de/2009/06/Batteriesymbol_Prozent.PNG)

Und jetzt ein paar schnell entdeckte Features der FW 3.0:

[![Querformat](//picdump.thafaker.de/2009/06/Querformat.PNG)](http://picdump.thafaker.de/2009/06/Querformat.PNG)

[![Copy&amp;Paste](//picdump.thafaker.de/2009/06/CopyPaste.PNG)](http://picdump.thafaker.de/2009/06/CopyPaste.PNG)

[![Suchfunktion](//picdump.thafaker.de/2009/06/Suchfunktion.PNG)](http://picdump.thafaker.de/2009/06/Suchfunktion.PNG)

*ENDE*. (Das ging ja einfach, was)

[**Hier** (archiviert)](http://web.archive.org/web/20090622022658/http://touch-mania.com:80/2009/06/20/tutorial-jailbreak-unlock-firmware-30-ipod-touch-iphone/) findet ihr diese Jailbreak-Anleitung für Windows.

**Ressourcen**:

- **[benm.at](http://www.benm.at)**
- **[Alle Firmwares zum Download](http://www.felixbruns.de/iPod/firmware/)**
- **[touch-mania.com (archiviert)](http://web.archive.org/web/20090622022658/http://touch-mania.com:80/2009/06/20/tutorial-jailbreak-unlock-firmware-30-ipod-touch-iphone/)**

PS: Hier folgt nun noch ein englisches Video mit einer ausführlichen Schritt-für-Schritt-Anleitung, allerdings nicht auf die Firmware 3.0 bezogen, aber dafür auf den **iPod Touch 2G**.
`How to Jailbreak iPod Touch 2G full Tutorial`
