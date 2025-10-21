---
title: Staatstrojaner [Update]
slug: staatstrojaner
date_published: 2011-10-08T20:49:51.000Z
date_updated: 2018-08-22T09:38:28.000Z
---

*Fefe*: [...] Achtung, aufgepasst, heute gibt es ein besonderes Leckerli. Der CCC kämpft ja schon seit Jahren gegen den Bundestrojaner und die Trojaner der einzelnen Bundesländer und hat bei diversen Gelegenheiten angesagt, dass wenn jemand bei sich einen Bundestrojaner findet, er den doch bitte bei uns abgeben möge, damit wir den sezieren können.

Es ist mir eine besondere Freude, heute [auf diese Presseerklärung des CCC](http://www.ccc.de/de/updates/2011/staatstrojaner) zu verlinken. Denn dem CCC sind tatsächlich Trojaner zugespielt worden, von denen wir nach eingehender Analyse glauben, dass es sich um "Quellen-TKÜ" handelt. Und die Ergebnisse der Analyse sind ernüchternd.

[![0zapftis](//picdump.thafaker.de/2011/10/0zapftis.png)](http://picdump.thafaker.de/2011/10/0zapftis.png)Von den ganzen Zusagen nach dem Bundestrojaner-Urteil des Verfassungsgericht ist nichts übrig geblieben. Es hieß, der Quellen-TKÜ-Trojaner sei was gaaaaanz anderes als der Bundestrojaner für die "Online-Durchsuchung" und könne gar keine fiesen Dinge tun, nur Skype abhören und so. Tatsächlich aber hat der Trojaner eine Nachladefunktion für beliebige zusätzlich Malware. Es hieß, alle Versionen werden für den speziellen Fall manuell entwickelt, aber in der Realität sind die Trojaner nicht nur sehr ähnlich, sie verwenden auch denselben hartkodierten AES-Schlüssel für die Absicherung der C&C-Verbindung. Und wenn ich AES sage, meine ich AES im ECB-Modus, und es wird nur in eine Richtung verschlüsselt. Und der Schlüssel ist wie gesagt hartkodiert. Die Richtung mit Verschlüsselung ist der Antwortkanal des Trojaners. Der Kanal, über den man zusätzliche Malware nachladen kann, ist gänzlich ungesichert. Integritätsprüfung (digitale Signatur, HMAC o.ä.) oder gar kryptographische Authentisierung gibt es gar nicht.

Oh und Teil des Trojaners ist ein Kernelmodul, allerdings ohne Tarnfunktion (das war wohl zu kompliziert) sondern nur mit Keylogger. Das Kernelmodul stellt Operationen wie "leg mal ne Datei unter diesem Pfad an" oder "schreibe das hier in die Registry" zur Verfügung, und die Keylogger-Funktionalität ist deaktiviert — der Code ist aber noch erreichbar, und dank dilettantischer Anfängerfehler im Rest des Kernelmoduls kann man ihn trotzdem aktivieren und benutzen.

Wenn dieser Trojaner auf einem Rechner installiert ist, steht der danach für jeden offen wie ein Scheunentor, ganz ohne dass man einen Exploit bräuchte. Man muss nur anklopfen und den Trojaner freundlich bitten. Und das Kernelmodul räumt allen lokalen Benutzern Adminrechte an. "Scheunentor" ist zu kurz gegriffen, um das katastrophale Sicherheitsniveau dieser Software zu beschreiben. Die CCC-Reverser dachten erst an einen besonders gewieften Tarnungs-Trick, als sie für AES nur den Verschlüsselungscode fanden und nicht den Entschlüsselungscode.

Der CCC hat für die Scheunentor-API des Trojaners [ein GUI geschrieben](http://www.ccc.de/system/uploads/78/original/0zapftis.png), das wir mal in einem kurzen Video vorstellen werden. Die Antivirenhersteller haben inzwischen Kopien des Trojaners erhalten und sollten ihn ab morgen früh erkennen und entfernen können, zumal keine Rootkit-übliche Tarnfunktionalität in dem Kernelmodul implementiert war. Aber macht euch keine Sorgen, wir haben den Behörden rechtzeitig Bescheid gegeben, dass sie noch schnell den Selbstzerstörungsknopf drücken können.

Oh, und, ganz wichtig noch, falls ihr ein Andenken haben wollt: die FAZ [hat dazu eine Meldung gemacht](http://www.faz.net/aktuell/chaos-computer-club-der-staatstrojaner-wurde-geknackt-11486538.html) und wird dem Thema in der FAS-Ausgabe morgen mehrere Seiten widmen. Und zwar, wie ich hörte, inklusive Auszügen aus dem Disassemblat. Wer also die erste Print-Tageszeitung haben will, in der Quellcode von Malware abgedruckt ist, sollte sich morgen eine FAS sichern. Oder halt [online lesen](http://www.faz.net/aktuell/chaos-computer-club-der-staatstrojaner-wurde-geknackt-11486538.html), aber das ist ja nicht das gleiche in dem Fall :) Ein [Listing-Service in der FAZ](http://www.faz.net/aktuell/feuilleton/ein-amtlicher-trojaner-anatomie-eines-digitalen-ungeziefers-11486473.html), wie damals bei der "DOS International"!

[**Update**] [Die Zeit ist auch im Boot](http://www.zeit.de/digital/datenschutz/2011-10/ccc-bundestrojaner-onlinedurchsuchung/komplettansicht).

[**Update**] Erstaunlicherweise ist der C&C-Server immer noch online, und mir erzählt gerade jemand, dass da ein Plesk von 2009 drauf läuft. Die BESTEN der BESTEN der BESTEN, SIR!

Falls sich jetzt jemand wundert, wieso ich die FAZ so plugge: [Schirrmacher (Herausgeber) hat einen Leitartikel zum Thema geschrieben](http://www.faz.net/aktuell/politik/staatstrojaner-code-ist-gesetz-11486546.html), und da hält er das Flammenschwert der Gerechtigkeit in den Händen und kloppt auf genau die richtigen Stellen. Er schreibt nicht nur, dass so ein Trojaner ja grundsätzlich immer alles kann, sondern zeigt auch auf die Nonnenmacher-Geschichte mit den zu Diskreditierungszwecken hinterlegten Kinderpornobildern hin und spricht in der Kontext von "der neuen Vernichtungsstrategie in der digitalen Welt". Und dann spricht er das Offensichtliche gelassen aus:

> In Zeiten einer „Piratenpartei“ kann der Fund des Chaos Computer Clubs die politische Geographie nachhaltig ändern.

So sieht das aus. Ich bin mir sicher, dass da dem politischen Establishment gerade mit Nachdruck der Arsch auf Grundeis geht. Es freut mich sehr, solche Gedankengänge in den etablierten Leitmedien zu lesen. Nicht mehr nur in Verschwörungsblogs wie dem meinen.

[**Update**] Wenn ich schon am erzählen bin, kann ich ja auch noch ein bisschen mehr plaudern. Der eine oder andere wird sich vielleicht gedacht haben, hey, so ein Trojaner, das ist ein komplexes Stück Software, das schaffen die doch bestimmt nicht ohne Plagiieren von Open Source, da ist doch bestimmt noch ne GPL-Verletzung zu haben. Nicht GPL, aber Speex haben wir gefunden, und die Lizenz wurde verletzt. Ich hörte, ein Anwalt sei schon unterwegs.

[**Update**] Das ehemalige Nachrichtenmagazin hat immer noch keine Meldung. Vor zwei drei Stunden ging die dpa-Meldung raus. Nichts. Wow. Da scheint mir die personelle Nähe zu den Geheimdiensten noch ausgeprägter zu sein als bisher angenommen. "Sturmgeschütz der Demokratie", dass ich nicht lache.

[**Update**] [Heise](http://www.heise.de/newsticker/meldung/CCC-knackt-Bundestrojaner-1357670.html), [ZDF Heute](http://www.heute.de/ZDFheute/inhalt/16/0,3672,8356656,00.html), [Tagesschau (archiviert)](http://web.archive.org/web/20111009165022/http://www.tagesschau.de:80/inland/trojaner100.html), [Golem](http://www.golem.de/1110/86917.html), [Gulli](http://www.gulli.com/news/17285-chaos-computer-club-staatstrojaner-rechtlich-und-technisch-fragwuerdig-2011-10-08) aber immer noch nichts bei Spon. Und auf Twitter musste sich ZDF Heute schon anpupen lassen, wieso sie in ihrer Nachtsendung nichts gebracht haben :-)

[**Update**] [Jetzt hat auch Spon was](http://www.spiegel.de/netzwelt/netzpolitik/0,1518,790756,00.html), und sie greifen bei den Zitaten in die Vollen, erwähnen sogar explizit den Wirtschaftsspionageaspekt bei der Durchleitung durch die USA. Inzwischen ist die Geschichte [auch in Österreich angekommen](http://orf.at/stories/2083344/) und sogar [sogar in den USA (archiviert)](http://web.archive.org/web/20111010063430/http://redtape.msnbc.msn.com:80/_news/2011/10/08/8228095-chaos-computer-club-german-govt-software-can-spy-on-citizens)[berichten erste Blogs](http://www.zdnet.com/blog/bott/german-government-accused-of-spying-on-citizens-with-state-sponsored-trojan/4044). Oh und [sogar die "Bild" war schneller als Spon](http://www.bild.de/digital/internet/bundestrojaner/chaos-computer-club-knackt-staatliche-spionage-software-20370024.bild.html). Oh und fürs Archiv [solltet ihr euch zum Vergleich auch nochmal die BMI-FAQ zum Bundestrojaner durchlesen (archiviert)](http://web.archive.org/web/20111011074005/http://www.bmi.bund.de:80/SharedDocs/FAQs/DE/Themen/Sicherheit/Datenschutz/Online_Durchsuchungen.html), mit Statements wie

> Die Datenübertragung wird derart verschlüsselt erfolgen, dass der Zugriff Dritter hierauf ausgeschlossen ist und die übermittelten Daten durch hohe Datenschutzstandards geschützt sind.

[**Update**] [Jetzt hat das ehemalige Nachrichtenmagazin noch einen richtigen Artikel nachgelegt](http://www.spiegel.de/netzwelt/netzpolitik/0,1518,790768,00.html) und damit sogar den Vetter von der Pole Position verdrängt. [blog.fefe.de]

([via](http://blog.fefe.de/?ts=b06e60e0))
