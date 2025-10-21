---
title: iMac8,1 Grafikfehler [Update]
slug: imac81-grafikfehler
date_published: 2011-10-05T07:12:14.000Z
date_updated: 2018-08-22T09:38:28.000Z
---

[**Update #2**] Ich habe den iMac zerlegt und verkaufe ihn gerade per eBay in Einzelteilen, die [CPU](http://rover.ebay.com/rover/0/e12000.m43.l1123/7?euid=5d40b8877a7f41f9ab52aa3fd10ac8ad&loc=http%3A%2F%2Fcgi.ebay.de%2Fws%2FeBayISAPI.dll%3FViewItem%26item%3D170708840490%26ssPageName%3DADME%3AL%3ALCA%3ADE%3A1123), den Bildschirm und das [Logicboard](http://rover.ebay.com/rover/0/e12000.m43.l1123/7?euid=3302eeaff52040f2b0fa127155671d19&loc=http%3A%2F%2Fcgi.ebay.de%2Fws%2FeBayISAPI.dll%3FViewItem%26item%3D170708875090%26ssPageName%3DADME%3AL%3ALCA%3ADE%3A1123).

[**Update #1**] Lustigerweise sorgt die defekte VGA nicht dafür, dass der iMac nichts mehr tut. Er läuft, und zwar vollständig. Ich kann auf die Freigaben zugreifen und auch eine VNC-Verbindung aufbauen. Im Systemprotokoll ist kein Bildschirm mehr vorhanden. Verdammt. Das bringt mir leider gar nichts, die VGA ist einfach tot. Kann man so eine VGA austauschen? Sicher nicht, oder? Die ist sehr wahrscheinlich auf dem Logicboard verlötet, denke ich.

[**Original**]Scheinbar hat es die Grafikkarte (nVidia 8800) in meinem iMac durchgehauen. Zuerst gab es nur Grafikfehler unter Lion und dann einen Freeze. Das war aber schon sehr seltsam weil ich noch nie einen Freeze hatte. Nun denn, nach einem Neustart war alles okay. Kurze Zeit später gab es nach dem Loginfenster bereits wilde blaue Vierecke und andere Artefakte:
[![broken_vga1](//picdump.thafaker.de/2011/10/broken_vga1-580x567.png)](http://picdump.thafaker.de/2011/10/broken_vga1.png)

Dann konnte man noch neu starten, aber sobald die GUI erschien, gab es einen Freeze. Also PRam oder NVRam Reset. Danach lief alles prima. Doch nach circa 2h Laufzeit wieder ein Freeze und wieder wilde Artefakte:
[![Foto 2](//picdump.thafaker.de/2011/10/Foto-2-580x433.jpg)](http://picdump.thafaker.de/2011/10/Foto-2.jpg)

Und jetzt geht gar nichts mehr. Bereits beim Einschalten, wenn also das Apple-Logo erscheint, gibt es Grafikfehler und er bootet gar nicht mehr.
[![Foto 3](//picdump.thafaker.de/2011/10/Foto-3-580x433.jpg)](http://picdump.thafaker.de/2011/10/Foto-3.jpg)

Das war es dann wohl... ich kotze!

#### Resetting PRAM and NVRAM

1. Shut down the computer.
2. Locate the following keys on the keyboard: Command, Option, P, and R. You will need to hold these keys down simultaneously in step 4.
3. Turn on the computer.
4. Press and hold the Command-Option-P-R keys. You must press this key combination before the gray screen appears.
5. Hold the keys down until the computer restarts and you hear the startup sound for the second time.
6. Release the keys.

So sah mein Bildschirm nach diesem Reset aus - das brachte also leider auch keinerlei Abhilfe.
[![Foto](//picdump.thafaker.de/2011/10/Foto-580x433.jpg)](http://picdump.thafaker.de/2011/10/Foto.jpg)
