---
title: Windows Phone 8 - Firmware für Nokia Lumia neu aufspielen [UPDATE #2]
slug: windows-phone-8-firmware-neu-aufspielen
date_published: 2013-07-14T18:26:47.000Z
date_updated: 2018-08-22T09:38:46.000Z
---

![windows-phone-8-logo-new.png](//thafaker.de/assets_c/2013/07/windows-phone-8-logo-new-thumb-100xauto-293.png)Ich habe nun den halben Tag damit zugebracht herauszufinden, wie man auf ein Nokia Lumia 820 die Firmware, also das Betriebssystem, neu aufsetzen kann. Unter iOS ist das relativ einfach. Da lädt man die passende Firmware für sein Gerät, bringt es in den DFU Modus und spielt sie via iTunes auf - fertig, heraus kommt ein völlig neu "formatiertes" Telefon. 

[red_box]**ACHTUNG**: Alle Tipps zum Flashen auf eigene Gefahr, das Gerät kann dadurch Schaden nehmen. thafaker.de übernimmt keine Haftung. Wenn ihr damit nicht einverstanden seid, geht weg.[/red_box]

Ja und diese Möglichkeit suchte ich quasi vergeblich. Nicht nur, dass unter Windows alles anders ist, nein, unter Nokia ist das Andere gar noch viel mehr anders und weitaus schlimmer. Erstens gibt es für jedes Gerät von jedem Provider in jeder Farbe eine eigene Firmware, noch dazu sind diese natürlich auch nach Ländern und Kontinenten unterteilt und tragen kryptische Bezeichnungen, die man sich auf den ersten Blick nicht merken kann. Allerdings habe ich nun bereits folgende Infos heraus gefunden:

Ich habe ein *simlockfreies*Nokia Lumia 820 der Telekom aus Deutschland, es hört auf den Namen RM-825 (824 und 826 sind Asien bzw. USA *afaik*).

- Gerät: Nokia Lumia 820 (RM-825)
- Firmware: 1232.5957.1308.0005 (0005 = TD1)

Für den Download der Firmware über die Nokia Software NCS, um sie später händisch aufs Lumia flashen zu können, benötigt man den zugehörigen Code welcher das Gerät identifiziert, der sich bei mir durch Telekom und Deutschland und schwarz ergibt: 059Q9G6

- Liste mit allen Nokia Codes [hier](http://www.uo5oq.com/forum/showthread.php?t=2236)
- Download der NCS (Nokia Care Suite) [hier (archiviert)](http://web.archive.org/web/20250905094406/https://mega.co.nz/). (Mega Link)
- Wird euer Windows Phone 8 nicht unter Windows 7 erkannt? Fragezeichen im Gerätemanager? [Hier gibts die Lösung](__GHOST_URL__/nokia-luma-mit-windows-phone-8-wird-unter-windows-7-nicht-erkannt).

### How To Flash Firmware WP8 on Nokia Lumia (820, 920; RM-825)

1. Das Nokia Telefon ist nicht mit dem Computer verbunden!
2. Um nun tatsächlich flashen zu können, braucht man die *Nokia Care Suite* in einer ganz speziellen Version, also *nicht* die Aktuellste, die man [hier (archiviert)](http://web.archive.org/web/20250905094406/https://mega.co.nz/) downloaden kann. Die ältere Version ist wichtig, weil in neueren Versionen der Download der Firmware gesperrt ist.
3. Dann wird die NCS installiert, aber noch nicht gestartet.
4. Dann muss man die Datei "usergroupsconfiguration.cfg" laden (sollte auch in der ZIP-Datei der NCS enthalten sein), [hier (archiviert)](http://web.archive.org/web/20250905203445/https://mega.co.nz/).
5. Diese geladene Datei "usergroupsconfiguration.cfg" wird nun in das Verzeichnis "C:Program Files (x86)NokiaNokia Care SuiteProduct Support Tool For Store 5.0" kopiert. Wenn ihr ein x64 Windows habt, dann in "Program Files" ohne (x86), also der andere Ordner.
6. Dann als Administrator die Nokia Care Suite starten und im Auswahlmenü "Product Support Tool For Store" doppelklicken.
[![Bildschirmfoto 2013-07-14 um 20.40.44.png](//thafaker.de/assets_c/2013/07/Bildschirmfoto%202013-07-14%20um%2020.40.44-thumb-250xauto-284.png) (archiviert)](http://web.archive.org/web/20221003090914/http://apfelhammer.de/assets_c/2013/07/Bildschirmfoto%202013-07-14%20um%2020.40.44-284.html)
7. Dann oben auf "Tools" --> "Firmware Downloads".
8. Dort den zuvor schon mal besprochenen Code eingeben, eine Liste mit allen Codes findet ihr [hier](http://www.uo5oq.com/forum/showthread.php?t=2236), meiner (Lumia 820, schwarz, Telekom) war ja: 059Q9G6
9. Dann auf "Check Online" und er zeigt euch passend für euer Telefon die aktuellste verfügbare Firmware an, die man direkt von Nokia downloaden kann.
10. Dazu muss man einfach nur auf Download klicken, und er lädt es herunter.
[![Bildschirmfoto 2013-07-14 um 20.43.38.png](//thafaker.de/assets_c/2013/07/Bildschirmfoto%202013-07-14%20um%2020.43.38-thumb-250xauto-287.png) (archiviert)](http://web.archive.org/web/20221003083100/http://apfelhammer.de/assets_c/2013/07/Bildschirmfoto%202013-07-14%20um%2020.43.38-287.html)
11. Dies sieht dann folgendermaßen aus.
[![Bildschirmfoto 2013-07-16 um 19.19.32.png](//thafaker.de/assets_c/2013/07/Bildschirmfoto%202013-07-16%20um%2019.19.32-thumb-250xauto-328.png) (archiviert)](http://web.archive.org/web/20221003082716/http://apfelhammer.de/assets_c/2013/07/Bildschirmfoto%202013-07-16%20um%2019.19.32-328.html)
12. Die Datei wird übrigens in den folgenden Ordner geladen: 

"C:ProgramDataNokiaPackagesProductsrm-825" 

Wobei die hintere Bezeichnung (rm-825) jene eures Telefons ist.
13. Jetzt habt ihr die Firmware herunter geladen und auf der Festplatte gespeichert, im nächsten Schritt werden wir die Firmware auf das Nokia installieren, ähnlich dem Recovery DFU Mode beim iPhone.
14. Dazu klickt ihr im Product Tool auf "File" --> "Open Product", damit wir unser Telefon auswählen können.
[![1.png](//thafaker.de/assets_c/2013/07/1-thumb-250xauto-331.png) (archiviert) (Link nicht mehr verfügbar)](http://web.archive.org/web/20221003071945/http://apfelhammer.de/assets_c/2013/07/1-331.html)
15. Meins heißt RM-825 (Lumia 820).
[![2.png](//thafaker.de/assets_c/2013/07/2-thumb-250xauto-334.png) (archiviert)](http://web.archive.org/web/20221003085623/http://apfelhammer.de/assets_c/2013/07/2-334.html)
16. Nun klicken wir unten auf "Programming --> Recovery" und befinden uns in einem Bildschirm wo wir sehen, welche Firmware wir vorhin bereits geladen haben. JETZT SCHLIEßEN WIR DAS NOKIA AN. Eigentlich brauchen wir dann nur noch auf START zu klicken und Volume UP + POWER am Telefon zu halten (DFU Mode).
[![4.png](//thafaker.de/assets_c/2013/07/4-thumb-250xauto-337.png) (archiviert)](http://web.archive.org/web/20221003085212/http://apfelhammer.de/assets_c/2013/07/4-337.html)
17. Start, VOLUME UP + POWER und warten, bis es vibriert. Dann kann es passieren, dass euch folgende Anleitung von der NCS ausgegeben wird. Dieses durchführen und RETRY klicken. 
[![Bildschirmfoto 2013-07-18 um 17.34.45.png](//thafaker.de/assets_c/2013/07/Bildschirmfoto%202013-07-18%20um%2017.34.45-thumb-250xauto-341.png) (archiviert)](http://web.archive.org/web/20221003091537/http://apfelhammer.de/assets_c/2013/07/Bildschirmfoto%202013-07-18%20um%2017.34.45-341.html)
18. Ich musste das mehrmals durchführen, bei mir rebootete immer nur mein Telefon, aber der Firmware-Flash-Recovery-Prozess kam nicht in Gang. Und dann ging es plötzlich. Also nicht verzagen. Wenn alles läuft, seht ihr auf dem Telefon folgendes Bild.
[![IMG_4159.jpg](//thafaker.de/assets_c/2013/07/IMG_4159-thumb-autox334-344.jpg) (archiviert)](http://web.archive.org/web/20221003072215/http://apfelhammer.de/assets_c/2013/07/IMG_4159-344.html)
19. Und die NCS zeigt euch dieses Bild, was signalisiert, dass die Firmware aufgespielt wird. Circa 1,25 GB mobiles Betriebssystem.
[![Bildschirmfoto 2013-07-18 um 17.40.12.png](//thafaker.de/assets_c/2013/07/Bildschirmfoto%202013-07-18%20um%2017.40.12-thumb-250xauto-347.png) (archiviert)](http://web.archive.org/web/20221003075237/http://apfelhammer.de/assets_c/2013/07/Bildschirmfoto%202013-07-18%20um%2017.40.12-347.html)
20. Das wars auch schon wieder. Danach rebootet das Telefon mit dem üblichen Windows Phone 8 und Nokia Logo. Nun könnt ihr fröhlich euer [Backup wiederherstellen (archiviert)](http://web.archive.org/web/20170224093601/http://apfelhammer.de/2013/07/windows-phone-8---backup-wiederherstellen.html) indem ihr euch mit eurem Windows Live Konto einloggt. BTW: warum man hier kein WLan auswählen kann, ist mir schier ein Rätsel, die Wiederherstellung wird übers Mobilfunknetz geladen.
21. An dieser Stelle sei vermerkt, dass ich durch das Flashen mein Branding als angenehme Nebenerscheinung entfernt habe. Mein Telefon stammte eigentlich von einem großen deutschen Anbieter (ohne Simlock) und deshalb waren diverse Apps vorinstalliert und es erschien auch beim Boot ein Bildschirm, den ich nicht wollte und mochte.
22. Durch die Installation der europaweiten freien Firmware wurde mein Lumia 820 vom Anbieter befreit :-) 
23. Eigentliche Firmware laut Code: 059Q9G6
24. Firmware die ich stattdessen genutzt habe: 059Q9L8
25. Das sollte auch bei euch klappen, wenn ihr ein Gerät von Vaderfone habt oder so.

Viel Spaß mit dem befreiten Gerät

#### Warum sollte ich mein Gerät "befreien"?

Das hat gleich mehrere Vorteile, die beiden Wichtigsten will ich aufzählen:

- man bekommt Updates schneller direkt von Nokia, als wenn sie erst noch durch den Provider "bearbeitet" und dann ausgerollt werden müssen.
- Die ganzen vorinstallierten providerabhängigen Apps sind meist nur Werbung und nützen niemandem etwas - so sind sie gar nicht mehr vorhanden.

Für ein baldiges Update von Windows Phone 8 wünsche ich mir [ordentliches WLan (archiviert)](http://web.archive.org/web/20170224070625/http://apfelhammer.de/2013/07/windows-phone-8-eduroam.html).

---
Hat ihnen dieser Artikel gefallen? Dann [liken Sie uns doch bitte auf Facebook](http://www.facebook.com/thafakerde) oder [folgen Sie uns auf Twitter (archiviert)](http://web.archive.org/web/20111020235347/http://twitter.com/thafakerde), wenn sie mögen. Auch können sie gern den [RSS-Feed abonnieren (archiviert)](http://web.archive.org/web/20130330030028/http://feeds.feedburner.com:80/apfelhammer.de). Vielen Dank für ihren Besuch.

Die Download-Links sind Affiliate Links.
