---
title: Ein echtes Linux auf einem Mac Mini M1 starten
slug: ein-echtes-linux-auf-einem-mac-mini-m1
date_published: 2021-10-08T21:18:00.000Z
date_updated: 2021-10-09T20:54:13.000Z
tags: apple m1, M1, mac mini m1, apple silicon, anleitung, how to, howto, wie geht, linux, linux m1, lubuntu, arm
---

Es ist mal wieder Zeit für ein kleines Tutorial. Und was liegt näher als auszuprobieren, wie Linux auf einem Mac Mini M1 laufen kann? Genau! Nichts, denn dass Windows for Arm in einer virtuellen Maschine nativ läuft, dass habe ich schon vor längerer Zeit [beschrieben](__GHOST_URL__/starting-windows-10-on-macmini-m1/).

Der M1 hat eine unglaubliche Leistung bei sehr guter Energieeffizienz und Linux für Arm gibt es schon ewig. Wir bedienen uns eines Ubuntu Linux in der aktuellen Version, es ist die Raspberry Pi Version und laden uns einen speziellen Kernel, der die Hardware des M1 nutzen kann. Wir bearbeiten die Sicherheitsfunktion des Macs sodass etwas anderes als macOS gebootet werden kann und los. Allerdings gibt es auch noch ein paar Hindernisse, das ganze sollte also nur aus Lust und Spaß an der Sache verstanden werden. Ein Proof Of Concept. Ich nutze hierfür einen Mac Mini M1.

=Disclaimer: Diese Anleitung führen Sie auf eigenes Risiko durch. Es kann alles kaputt gehen. Niemand außer sie selbst sind dafür verantwortlich.=

### Was wird benötigt

- Mac Mini M1
- USB Stick mit mindestens 16 GB Speicher. Es funktioniert nur mit einem USB-C Stick, die USB-A Anschlüsse am Mac Mini werden noch nicht unterstützt! Ihr braucht also einen Adapter

![Ich nutze einen Sandisk 32 GB Stick und diesen USB-C auf USB-A Adapter](__GHOST_URL__/content/images/2021/10/tempImagevgOB0i.gif)Ich nutze einen Sandisk 32 GB Stick und diesen USB-C auf USB-A Adapter
### Was funktioniert noch nicht?

- Es gibt keine Grafikbeschleunigung
- Das eingebaute WLan wird noch nicht unterstützt

## How To Linux Mac M1

1. Sichert eure Daten, macht das mit TimeMachine oder händisch, aber sichert eure Daten.
2. Ladet euch das Ubuntu Image (3,07 GB) [hier](https://assets.checkra.in/downloads/corellium/e4beb88251d7adf927e1a0db33677bf3b4b8ec6bfff4f971e38fb9d2767cbd69/ubuntu-20.10-preinstalled-desktop-arm64+raspi.img.bz2) herunter
3. Entpackt es durch einen Doppelklick oder im Terminal mit folgendem Befehl:
*`tar -xjvf ubuntu-20.10-preinstalled-desktop-arm64+raspi.img.bz2`*
Ihr erhaltet eine *.img Datei, das Linux Image. Dieses wird gleich auf den USB Stick übertragen.
4. Schließt den USB Stick an euren Mac Mini an und startet das Festplattendienstprogramm. Dort schaut ihr nach, wie euer Stick heißt. Meiner heißt `disk4s1`. Bedenke: Der USB Stick wird durch die folgenden Aktionen vollständig gelöscht!

![](__GHOST_URL__/content/images/2021/10/Bildschirmfoto-2021-10-09-um-09.02.33.png)Festplattendienstprogramm USB Stick lokalisieren
1. Jetzt übertragen wir das Image mit dem Befehl dd auf den USB-Stick. Folgender Befehl führt das aus.

*`sudo dd if=ubuntu-20.10-preinstalled-desktop-arm64+raspi.img of=/dev/r**YOURUSBDISK** bs=1m`*

**YOURUSBDISK** wird durch eure ersetzt, bei mir ist es `disk4s1`. Das r in der Befehlszeile bleibt stehen. Bei mir lautet der Befehl also folgendermaßen, ich befinde mich in dem Ordner, in welchem ich das Image entpackt habe:

*`sudo dd if=ubuntu-20.10-preinstalled-desktop-arm64+raspi.img of=/dev/r**disk4s1** bs=1m`*

2. Das ganze dauert ein Weilchen bis er das Linux Dateisystem, die entpackten 9 GB, auf den Stick geschrieben hat. Er wird für den Befehl nach eurem Passwort fragen, gebt es ein. Bei mir sah der erfolgreich beschriebene USB Stick so aus. Fertig.

`8345+1 records in
8345+1 records out
8750736384 bytes transferred in 329.352946 secs (26569480 bytes/sec)`

3. Jetzt kopieren wir die WLan Firmware auf die exFat Partition des MacMini mit folgendem Befehl, dadurch können wir später WLan einbinden:

`sudo *cp -RLav /usr/share/firmware/wifi /Volumes/system-boot*`
4. Wenn er den Stick erstellt hat, booten wir in das 1TR (the one true recovery OS) unseres Mac Minis. Der Stick muss am USB-C des Macs angeschlossen sein! 
Fahrt den Mac herunter. Dann haltet den Einschaltknopf beim Einschalten so lange gedrückt, bis ihr `Optionen` seht, die ihr auswählt.

![](__GHOST_URL__/content/images/2021/10/boot_recovery_macminim1.jpg)
1. Wenn er gebootet hat wählt ihr euren Benutzer aus und gebt euer Kennwort ein. Dann klickt ihr links oben auf  Dienstprogramme und wählt `Terminal`.
2. Im Terminal gebt ihr folgenden Befehl ein:
*`bash -c "$(curl -fsSL [https://downloads.corellium.info/linuxusbboot.sh (archiviert)](http://web.archive.org/web/20220306052554/https://downloads.corellium.info/linuxsetup.sh))"`*
Das Script führt alle nötigen Schritte durch. ACHTUNG: Es funktioniert nur, wenn eure Festplatte `Macintosh HD` heißt, ansonsten findet das Script sie nicht. Hardcoded.
3. Das Script läuft durch und meldet euch bei Erfolg "installing Kernel. Safe to reboot". Tippt einfach `reboot` ins Terminal, der Mac startet neu und sollte nun Ubuntu booten :) Es bleibt spannend.
4. Ich musste diesen Schritt zwei mal tun, warum auch immer. 
5. Ihr landet nun beim Login Screen von Ubuntu. Da es ein Raspberry Pi Ubuntu ist, könnt ihr euch folgendermaßen einloggen:
* Username: pi
* Passwort: raspberry
6. Viel Spaß am Gerät.

### zurück zu macOS

Das Schöne an dieser Anleitung ist, dass die interne Festplatte nicht gelöscht wird. Sie wird vorbereitet um einen Custom Kernel zu booten, das kann man rückgängig machen wenn man mächte. 

1. Folgt dazu dem Schritt wo wir in das 1TR (the one true recovery OS) durch langes Gedrückthalten des Einschalters gebootet haben. 
2. Gebt euer Passwort ein
3. Startet das Terminal
4. Gebt folgenden Befehl ein: 
*`bputil -n`*
5. und drückt ENTER. Ihr benötigt wieder euer Kennwort.
6. Das Script läuft durch und setzt die getätigten Änderungen zurück.
7. Gebt `reboot` ein: et voila, macOS bootet wieder, alles ist wie vorher.

([via](https://www.corellium.com/blog/linux-m1))
