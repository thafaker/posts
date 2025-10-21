---
title: Schutzfunktion in Mac OSX wird durch Trojaner deaktiviert
slug: schutzfunktion-in-mac-osx-wird-durch-trojaner-deaktiviert
date_published: 2011-10-20T10:44:59.000Z
date_updated: 2018-08-22T09:38:28.000Z
---

Es  gibt mal wieder einen Schädling für Mac OSX. Wie [F-Secure](http://www.f-secure.com/weblog/archives/00002256.html) berichtet, ist die Schadsoftware Trojan-Downloader:OSX/Flashback.C in der Lage, die File Quarantine von Mac OSX zu deaktivieren. Hierbei handelt es sich um die von Apple implementierte Schadsoftwareerkennung.

[![](//picdump.thafaker.de/2011/10/flashback_c_installer.jpg)](__GHOST_URL__/schutzfunktion-in-mac-osx-wird-durch-trojaner-deaktiviert/flashback_c_installer/)

Flashback will scheinbar verhindern, dass über ein Sicherheitsupdate die Funktionen des Programms unschädlich gemacht werden. Dazu löscht der Trojaner einige Dateien im System, die für File Quarantine zwingend notwendig sind. Anschließend sind Updates der Liste von Schadsoftware nicht mehr möglich. Die Softwareaktualisierung selbst wird offenbar nicht angegriffen, so dass Apple mit einem regulären Sicherheitsupdate eine Reparatur starten könnte. Ein normales Löschen der Systemdateien ist jedoch mit einem Standardnutzer nicht möglich, dies kann nur ein Administrator und auch der nur, nachdem er nochmals sein Passwort zur Bestätigung eingegeben hat. Ganz ungefährlich ist das ganze leider trotzdem nicht, denn der Trojaner versucht es mit Social Engineering, er tarnt sich als [Flashplayer](http://www.f-secure.com/v-descs/trojan-downloader_osx_flashback_c.shtml) und versucht den Nutzer davon zu überzeugen, das Programm mit Adminrechten zu installieren, geschickt, da auch der echte Flashplayer Administratorrechte benötigt. Da ja nun auf neueren Macs standardmässig kein Flash mehr vorinstalliert ist, sind natürlich viele Nutzer daran interessiert, diesen zu installieren. Auf Schadsoftwareseiten wird das Opfer dann nicht zu Adobe geleitet, sondern eben auf eine präparierte mit dem Flashback Schädling.

In letzter Zeit erscheint gehäuft Schadsoftware für den Mac, vermutlich aufgrund des steigenden Marktanteils der Mac-Plattform. Erst im Mai / Juni 2011 war der [Mac-Defender in den Schlagzeilen](__GHOST_URL__/apple-entfernt-im-kommenden-update-die-scareware-mac-defender/).

[[golem.de](http://www.golem.de/1110/87176.html)]

Bild: F-Secure
