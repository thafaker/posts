---
title: Fritzbox und Dynamic DNS mit FreeDNS
slug: fritzbox-und-dynamic-dns-mit-freedns
date_published: 2014-03-29T11:15:11.000Z
date_updated: 2018-08-22T09:38:56.000Z
---

[![FritzBox](//picdump.thafaker.de/2014/03/FritzBox-100x100.jpg)](http://picdump.thafaker.de/2014/03/FritzBox.jpg)Ich besitze nun eine Fritzbox, jenes legendäre Stück Technik aus Deutschland, was die dereinst zahlreichen Fahnen guter Elektronik weiter hoch hält, auch wenn es scheinbar die letzten ihrer Zunft sind - die noch hier produzieren. Doch genug des Geredes, eigentlich ist der Hintergrund sehr traurig, denn die Fritzbox habe ich nur, weil ich nach Umzug keinen Kabelanbieter mehr finden konnte und deshalb auf DSL zurück rüsten musste. 

Und DSL und FritzBox passen eben gut zusammen. Hinter der Fritzbox werkelt weiterhin mein Asus RT-N56U und served das WLan, welches in der Box deaktiviert ist.

Eigentlich ist das Menü der FB sehr nett, irgendwie so ganz anders als sonstige Webinterfaces die ich so kennen, strukturiert und… ich finde nichts mehr wieder. Immer mal kommt es also vor, dass ich eine eigentlich bereits bekannte Funktion von Früher wieder haben möchte und dann erst mal vor einer fast unlösbaren Aufgabe stehe - wie auch diesmal.

**Warum FreeDNS?**

All free accounts come with:

- Unlimited DNS query traffic
- 5 free subdomains from domains in the shared system
- 20 free subdomains per domain of your own

BÄM! Deshalb.

### DynDNS mit freedns.afraid.org soll es werden!

1. Erst mal [registrieren](http://freedns.afraid.org/signup/).
2. Email erhalten und Account bestätigen.
3. und eine Domain auswählen.
[![Bildschirmfoto 2014-03-29 um 11.06.44](//picdump.thafaker.de/2014/03/Bildschirmfoto-2014-03-29-um-11.06.44.png)](http://picdump.thafaker.de/2014/03/Bildschirmfoto-2014-03-29-um-11.06.44.png)
4. Auf der Seite klickt ihr auf "Menü" --> "Dynamic DNS".
5. Dort findet ihr den Link "Direct URL" unten bei eurer DynDNS-Domain.
6. Rechtsklick Link kopieren.
7. In der Fritzbox auf "Internet" --> Freigaben --> Dynamic DNS.
[![fritzbox_dyndns](//picdump.thafaker.de/2014/03/fritzbox_dyndns-144x144.png)](http://picdump.thafaker.de/2014/03/fritzbox_dyndns.png)
8. Legt in der Firtzbox einen benutzerdefinierten Anbieter an und tragt diese URL erst einmal bei UpdateURL ein. Den php Parameter löscht Ihr weg und ersetzt in mit Eurem Benutzernamen (rechts von php? ):
`freedns.afraid.org/dynamic/update.php?**meinusername**`
9. Dann tragt Ihr Eure ausgesuchte Domain, den Benutzernamen ein zweites Mal in das entsprechende Feld und zum Schluss Euer Kennwort in die Maske ein.

Und schon sollte es gehen.
