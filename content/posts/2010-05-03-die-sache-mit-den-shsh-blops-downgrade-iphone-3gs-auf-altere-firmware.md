---
title: Die Sache mit den SHSH Blobs (Sichern selbiger und Downgrade iPhone 3GS auf ältere Firmware)
slug: die-sache-mit-den-shsh-blops-downgrade-iphone-3gs-auf-altere-firmware
date_published: 2010-05-03T19:13:52.000Z
date_updated: 2018-08-22T09:38:22.000Z
---

`Dieser Artikel ist nur für das iPhone 3GS wichtig, nicht aber 3G oder Classic. Ich glaube, iPhone 3G sind nun mittlerweile auch betroffen.`

Wenn man sein **SHSH** Zertifikat nicht sichert, hat man keinerlei Möglichkeit mehr auf eine frühere Firmware zurück zu kehren, sie mit iTunes wiederherzustellen. Dies ist gerade jetzt, wo der Jailbreak [Spirit](__GHOST_URL__/03/spirit-jailbreak-ist-da) veröffentlicht worden ist, ausgesprochen wichtig.

Hat man beispielsweise ein iPhone 3GS (oder einen iPod touch "late 2009" oder ein iPad) mit Firmware 3.1.2 und einen tethered Jailbreak wie blackra1n am Laufen und aktualisiert dann auf die FW 3.1.3 oder lässt Spirit jailbreaken, bleibt das iPhone immer mit dem iTunes Stecker Symbol hängen und man hat keinen Zugriff mehr, Wartungszustand. Ein erneuter Jailbreak mit blackra1n (oder auch red2n0w 9.4) ist nun nicht mehr möglich. Will man jetzt auf die Firmware 3.1.2 wiederherstellen, so schlägt auch dieses fehl, weil Apple alle alten Firmware Versionen ausperrt und nur noch die Firmware 3.1.3 akzeptiert. Für die Firmware 3.1.3 gibt es aber wiederum keinen Unlock Bzw. Aktivierung, das kann Spirit nämlich nicht.

Hat man aber die SHSH Blobs gesichert, so kann man im Falle eines Falles versuchen, iTunes zu verarschen um wieder auf die Firmware 3.1.2 wiederherzustellen/downzugraden. Um die Zertifikate zu sichern, geht bitte bei Cydia auf “**Make my life easier**”. Nach kurzer Zeit erscheint dann “**This device has a 3.x ECID SHSH on file**” und ihr seid auf der sicheren Seite. Alternativ kann auch die Software “**Firmware Umbrella**” helfen, wobei es [hier](http://www.early-adopter.info/2010/05/shsh-hashes-sichern-beim-iphone-vorbereitung-auf-den-os-3-1-3-unlock/) eine Anleitung dazu gibt.

**Wie verarschen?** Saurik hat sich den Signierungsprozess genauer angesehen und so den Apple Zertifizierungserver “nachgebaut”. Dies ermöglicht es, alle Firmware-Signierungsanfragen an die Apple Server per Hostfile (die Datei /etc/hosts) umzuleiten und so den Signierungsprozess nicht durch Apple, sondern durch den Cydiaserver durchführen lassen, der dann wiederum erlaubt, auf die alte Firmware downzugraden. Unten steht zu diesem Verfahren mehr.

**ACHTUNG**: Hat man den Schritt **Make my life easier** in Cydia nicht durchgeführt und hat man auch keinen Zugriff mehr auf Cydia (weil das Teil schon nicht mehr bootet oder ähnliches), dann ist es bereits zu spät, dann kommt man nicht mehr an die SHSH Zertifikate und braucht den Text hier auch nicht mehr weiter zu lesen. Dann muss man auf einen Jailbreak warten, der die Firmware 3.1.3 unlocken, aktivieren und jailbreaken kann, *der vielleicht niemals kommen wird.*

[![iTunes_ERROR_SHSH](//picdump.thafaker.de/2010/05/iTunes_ERROR_SHSH.png)](http://picdump.thafaker.de/2010/05/iTunes_ERROR_SHSH.png)

So, jetzt aber mal los. Zuerst brauchen wir die eindeutige **ECID** des iPhones. Denn die SHSH Zertifikate sind eine Mischung aus der ECID und anderen Daten des iPhones, die für jedes Gerät einmalig sind, sodass man auch keine SHSH von einem anderen User nutzen kann. Man braucht sein eigenes SHSH Zertifikat! 

**Das iPhone muss in den DFU Modus gebracht werden**.

1. iPhone ausschalten, es darf dabei nicht mit dem Mac verbunden sein
2. Home-Taste drücken und dabei das iPhone an den Mac anschließen
3. Home-Taste solange gedrückt halten, bis auf dem iPhone das iTunes  Logo und das USB-Kabel-Symbol erscheinen
4. Hat man ein 3GS mit einem tethered Jailbreak, so muss man es nur ausschalten, beim wieder Einschalten geht es automatisch in den DFU Modus (weil es ja wieder auf einen Jailbreak wartet).
5. Fertsch

Jetzt endlich zur ECID.

- **Apple-Nutzer** können die ECID ihres Gerätes folgendermaßen  herausfinden: Klickt im OS X-Menü auf “Über diesen Mac” und danach auf  “Weitere Informationen”. Im neuen Fenster wählt ihr nun “USB” und “Apple  Mobile Device (Recovery Mode)” aus der daraufhin erscheinenden Liste  aus. Jetzt seht auch ihr die **ECID eures iPhone** gepaart mit ein paar weiteren Informationen, welche  ihr ebenfalls kopiert. *Fertsch*.

- **Windows-Nutzer benötigen** das Programm USBView,  einen USB Connection Viewer von Microsoft, welcher [hier (archiviert)](http://web.archive.org/web/20100113171227/http://ftdichip.com/Resources/Utilities/usbview.zip) heruntergeladen werden  kann. Nach dem Start von USBView klickt man im Menü des Programms auf  “Options” und danach auf “Config Descriptors”. Nach dem Druck auf die  F5-Taste sollte sich die Ansicht im Programm entsprechend aktualisieren.
Wählt nun in der Baumansicht links den Eintrag “Apple Mobile Device  (Recovery Mode)” bzw. “Apple Recovery (iBoot) USB Driver”.  Rechts sollte man nun u.a. eine lange Zeile mit verschiedenen Zahlen  und Codes vorfinden. In mitten dieser Zeile ist der Eintrag “ECID” zu  finden. Diese ECID kopiert ihr. *Fertsch*.

**SHSH Hashes sichern**
Nun zum abschließenden Schritt:
Ladet euch von [dieser Seite](http://thefirmwareumbrella.blogspot.com/) das  Programm **Firmware Umbrella** herunter. Nach dem Ausführen der *Umbrella.exe* (Windows) bzw. *Umbrella.dmg* (OS X) **tragt ihr die zuvor kopierte ECID ein**, wählt euer iPhone Modell inkl. der  aktuell installierten Firmware-Version und zusätzlich noch je nach Bedarf die SHSH Speichermethode aus:

- **Saurik** speichert die SHSH Hashes auf Sauriks Server (wie oben erläutert) – würde ich aber nicht empfehlen, da dieser oft überlastet ist und im Fall  der Fälle, also bei einer nötigen Wiederherstellung oder einem  Downgrade, nicht erreichbar sein könnte oder irgendwann ganz abgeschaltet wird und die Zertigikate auf ewig verloren sind.
- **Local Host** speichert die SHSH Hashes eures iPhone  direkt im Firmware Umbrella Ordner auf eurem Rechner. Dies ist die  sicherste Variante, da ihr immer wieder auf die Datei zugreifen könnt. Ich empfehle, beide Varianten durchzuführen, doppelt hält besser.

Bei Auswahl von “Apple” wird euch angezeigt, welche SHSH ihr von Apple  erhalten würdet.

Sollte es beim Ausführen von Firmware Umbrella zu Problemen oder  Fehlermeldungen kommen, werft bitte zuerst einen Blick auf die  entsprechenden [FAQ des Programms](http://thefirmwareumbrella.blogspot.com/2010/03/faq-firmware-umbrella.html).

Nach dem Sichern der SHSH Hashes könnt ihr nun **beruhigt dem  nächsten iPhone OS Update entgegensehen**, da ihr euch die  Möglichkeit zu einem Downgrade offen gehalten habt. Sollte mit dem neuen  **OS 3.1.3, OS 3.2 oder OS 4.0** also zu Beginn kein  Unlock möglich sein, wie sich ja bereits heraus gestellt hat, könnt ihr immer wieder auf eine ältere  Firmware-Version zurück (downgrade) wechseln. Und wie das geht, zeigt der nächste Schritt, den ich allerdings später nachreichen werde.

**Firmware downgraden bzw. wiederherstellen einer älteren Version**[

Hier](http://www.cultofmac.com/how-to-downgrade-iphone-with-shshs-stored-on-file-with-cydia-using-mac/29359) gibt es eine großartige, bebilderte Beschreibung, allerdings in englischer Sprache.
