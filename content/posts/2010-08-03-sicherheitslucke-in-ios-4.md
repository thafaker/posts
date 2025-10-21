---
title: Sicherheitslücke in iOS 4 [Update]
slug: sicherheitslucke-in-ios-4
date_published: 2010-08-03T07:18:38.000Z
date_updated: 2018-08-22T09:38:19.000Z
---

Der am Sonntag veröffentliche [Jailbreak für alle Geräte](__GHOST_URL__/01/das-warten-hat-ein-ende-jailbreak-fur-alle-gerate-ist-da) (iPhone 4, iPhone 3Gs / 3G, Ipod Touch usw.) nutzt ja eine bis dato unbekannte Sicherheitslücke beim Betrachten von PDF-Dateien aus, um über eine speziell konstruierte PDF Datei das jeweilige Gerät zu öffnen. Nur deshalb funktioniert der Jailbreak -wie [hier](__GHOST_URL__/02/vorgehensweise-zum-neuen-jailbreak-jailbreakme-2-0) beschrieben- auch so spielend einfach. Apple wird diese Lücke mit Sicherheit so bald wie möglich schließen, da dies, jetzt wo der Exploit bekannt ist, ein enormes Sicherheitsrisiko für alle iPhone Benutzer darstellt, denn die Lücke ist natürlich auch ohne das man sein Gerät jailbreakt, vorhanden (sonst wäre der Jailbreak ja auch gar nicht möglich).

[**Update**] Comex, der Entwickler des Jailbreaks und Betreiber der Website jailbreakme.com hat den Patch in die neueste Version bereits integriert, sollte man jetzt jailbreaken, ist die Sicherheitslücke bereits durch unten beschriebene Variante gesichert.

[**Update**] Die Jungs von [BenM.at](http://www.benm.at/2010/08/02/wichtig-gefahrliche-sicherheitslucke-im-ios-4/?utm_source=feedburner&utm_medium=feed&utm_campaign=Feed%3A+benm+%28BENM.AT%29) haben den (weiter unten im Artikel) komplizierten Vorgang in ihre eigene Repo integriert, sodass man nur noch die Quelle adden und das Paket installieren muss, um geschützter zu sein.

**Installationsanleitung:**

- Füge in Cydia die Source “http://repo.benm.at” hinzu
- Installiere das Paket “PDF Exploit Warner”
- Starte das Gerät neu
- Das wars schon, von nun an wird das Öffnen einer PDF immer angezeigt und gemeldet.

[**Update**] Comex hat dieses Sicherheitspaket bereits in seinen Jailbreak auf jailbreakme.com integriert.

[**Original**] Es gibt bereits eine relativ komplizierte [Anleitung](http://ispazio.wordpress.com/2010/08/02/importante-come-risolvere-una-grave-falla-di-sicurezza-dellios-dopo-aver-eseguito-il-jailbreak-con-jailbreakme/) um die Sicherheitslücke zu schließen:

**Voraussetzungen**:

- gejailbreaktes iPhone
- installiertes OpenSSH
- Cyberduck bzw. WinSCP
- Putty (nur für Windows-User)

**Vorgehensweise**:

- Ladet euch von [hier](http://go2.wordpress.com/?id=725X1342&amp;site=ispazio.wordpress.com&amp;url=http%3A%2F%2Fcl.ly%2F8ad8cadc8ae3ff8729eb&amp;sref=http%3A%2F%2Fispazio.wordpress.com%2F2010%2F08%2F02%2Fimportante-come-risolvere-una-grave-falla-di-sicurezza-dellios-dopo-aver-eseguito-il-jailbreak-con-jailbreakme%2F) die *.deb-Datei herunter
- verbindet euch via WinSCP oder Cyberduck mit eurem iPhone
- kopiert die *.deb-Datei nach: private/var/root
- verbindet euch mit Putty (Win) oder Terminal (Mac) als User "root"  (Standard-Passwort ist: alpine) mit der SSH-Konsole eures iPhones
- gebt folgenden Befehl (ohne ") ein:
`"dpkg -i com.willstrafach.pdfexploitwarner_1.0.0-4_iphoneos-arm.deb"`

Nun solltet ihr beim Öffnen von PDF-Dateien aus Safari immer folgenden Warnhinweis bekommen:
[![ispazio](//picdump.thafaker.de/2010/08/ispazio-150x150.jpg)](http://picdump.thafaker.de/2010/08/ispazio.jpg)
