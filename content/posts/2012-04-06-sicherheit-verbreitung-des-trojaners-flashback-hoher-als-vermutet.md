---
title: [SICHERHEIT] Verbreitung des Trojaners 'Flashback' höher als vermutet [UPDATE]
slug: sicherheit-verbreitung-des-trojaners-flashback-hoher-als-vermutet
date_published: 2012-04-06T09:00:18.000Z
date_updated: 2018-08-22T09:38:11.000Z
---

![cccebit_bundestrojaner](//picdump.thafaker.de/2008/11/cccebit_bundestrojaner-150x150.png)Mehr als eine halbe Million Mac-OS-X-Maschinen könnten nach Einschätzung des russischen Antiviren-Spezialisten Doctor Web mit Varianten der Malware "Flashback" infiziert sein. Der Trojaner verbreitet sich seit kurzem über eine Java-Lücke, die Apple erst in [dieser Woche gepatcht](__GHOST_URL__/update-apple-aktualisiert-java-unterstutzung-fur-mac-os-x/) hat. Dabei reicht es zur Infektion aus, mit eingeschaltetem Java eine präparierte Website zu besuchen. Doctor Web schätzt, dass mittlerweile 550.000 Maschinen zu einem Botnetz zusammengefasst sind, das Kriminelle fernsteuern können. [...] Das sind natürlich wesentlich weniger Botnetz-Mitglieder als man dies von unter Windows gehijackten Computern gewohnt ist, aber dennoch scheint es der lang erwartete Beginn dessen zu sein, was oft schon vermutet wurde. OS X scheint nicht sicherer zu sein, es benutzen einfach nur weniger Menschen. Es gab schon immer vieler Vertreter der These, dass mit zunehmender Nutzung von Macs und OS X auch dessen Attraktivität für Viren-Programmierer steigt. Flashback kann nun als *Proof-Of-Concenpt in the Wild* interpretiert werden. 550.000 Macs sind keine Armee, aber 550.000 Macs zeigen, wie leicht es auch hier scheint, sich derer zu bedienen und sie zu zweckentfremden.

[...] Die Infektion mit dem Trojaner soll sich laut Doctor Web innerhalb weniger Tage massenhaft ausgebreitet haben. Vor allem seien Rechner in den USA, Kanada und Großbritannien betroffen. In Deutschland liege der Anteil der Infektionen dagegen bei nur 0,4 Prozent. Doctor Web ermittelte die Zahl mit der sogenannten Sinkhole-Methode, bei der Botnet-Daten auf eigene Server umgeleitet wurden, über die sich die Identifikationsnummer eines infizierten Rechners auslesen ließ. Daraus wurde der Wert dann hochgerechnet.

Der "Flashback"-Trojaner ist schon länger bekannt. Die Schadsoftware versucht Nutzer zum Herunterladen einer Software zu bewegen, indem sie sich als Flash-Player im Internet ausgibt. Laut einem Advisory des Sicherheitsunternehmens F-Secure verlangt die Malware an einem bestimmten Punkt des Installationsprozesses die Eingabe eines Administrator-Passworts, versucht sich aber auf anderem Weg auch zu installieren, wenn der Nutzer dies verweigert. Zuvor waren in früheren "Flashback"-Varianten andere Lücken ausgenutzt worden, allerdings waren diese bislang nie ungepatcht

F-Secure nennt in seinem [Advisory](https://www.f-secure.com/v-descs/trojan-downloader_osx_flashback_k.shtml) Schritte, mit denen sich eine potenzielle Infektion im Mac-OSX-Terminal feststellen lässt. Wenn die Befehle

    defaults read /Applications/Safari.app/Contents/Info LSEnvironment

und

    defaults read ~/.MacOSX/environment DYLD_INSERT_LIBRARIES

jeweils die Fehlermeldung "The domain/default pair of (...) does not exist" ausgeben, soll man sich die Malware nicht eingefangen haben. (Für Betroffene bietet F-Secure im gleichen Advisory außerdem eine Entfernungsanleitung.) Nutzer sollten darüber hinaus baldmöglichst [Apples Java-Update](__GHOST_URL__/update-apple-aktualisiert-java-unterstutzung-fur-mac-os-x/) einspielen, das für Lion und Snow Leopard angeboten wird. Zusätzlich lässt sich Java auch über das Hilfsprogramm "Java-Einstellungen" vollständig abdrehen.

[![Bildschirmfoto 2012-04-06 um 10.54.33](//picdump.thafaker.de/2012/04/Bildschirmfoto-2012-04-06-um-10.54.33-580x244.png)](http://picdump.thafaker.de/2012/04/Bildschirmfoto-2012-04-06-um-10.54.33.png)

([via](http://www.heise.de/mac-and-i/meldung/AV-Firma-vermutet-groessere-Verbreitung-des-Mac-Trojaners-Flashback-1516895.html))

[**Update**] Kaspersky bietet an [dieser Stelle (archiviert)](http://web.archive.org/web/20120412181859/http://www.securelist.com:80/en/blog/208193454/Flashfake_Removal_Tool_and_online_checking_site) ein "Removal Tool" an, welches den Mac scannt und den Trojaner entfernen kann.
[![Bildschirmfoto 2012-04-10 um 14.23.02](//picdump.thafaker.de/2012/04/Bildschirmfoto-2012-04-10-um-14.23.02-580x396.png)](http://picdump.thafaker.de/2012/04/Bildschirmfoto-2012-04-10-um-14.23.02.png)[![Bildschirmfoto 2012-04-10 um 14.23.10](//picdump.thafaker.de/2012/04/Bildschirmfoto-2012-04-10-um-14.23.10-580x396.png)](http://picdump.thafaker.de/2012/04/Bildschirmfoto-2012-04-10-um-14.23.10.png)

EOF
