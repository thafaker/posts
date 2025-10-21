---
title: Gib mir Speed - ZFS unter OS X?
slug: gib-mir-speed-zfs-unter-os-x
date_published: 2012-05-19T14:24:36.000Z
date_updated: 2018-08-22T09:38:08.000Z
---

[![zfs_feature_2](//picdump.thafaker.de/2012/05/zfs_feature_2.jpg)](http://picdump.thafaker.de/2012/05/zfs_feature_2.jpg)Ich nenne ja so einen ultra fetten 2010er **27" iMac Core i7 12GB-Ram** ((iMac11,3 - [Hier](http://www.everymac.com/systems/apple/imac/specs/imac-core-i7-2.93-27-inch-aluminum-mid-2010-specs.html) kann man sich genauere Specs ansehen.)) mein Eigen... und könnte mal wieder verzweifeln. Ich setze das Ding seit OSX 10.5 nun das erste mal richtig neu auf, weil ich die Installationen über meine verschiedenen Macs und via TimeMachine immer mal wieder mit umgezogen habe und mein System ziemlich zugemüllt war. Na auf jeden Fall hat die Bude echt viel Bums (ca. 12000 Geekbench Punkte) und reicht für alles rechnerische ziemlich gut aus - wenn da nicht die beknackte scheiß interne 1TB-Festplatte wäre. Diese ist echt ein Krampf. Sie ist so langsam, dass ich schon das eine oder andere mal einen Ausflug durchführen konnte, ob der Länge der Bootzeit. 

Mit alternativen Möglichkeiten wie dem zusätzlichen Einbau einer SSD habe ich mich bereits beschäftigt, aufgrund der hohen Preise bei einem professionellen Umbau aber eher wieder Abstand genommen. Sicher würde ich mir den Umbau mit ner zweiten Person auch selbst zutrauen, aber ich habe ob des Risikos und vor allem des Schmutzes beim Display einfach gar keine Lust - noch dazu wo das SSD-Einbaukit mit den original Apple-Teilen gleich mal mit 80 Euro zu Buche schlägt - und da habe ich noch keine SSD.

An solchen Tagen also, Tagen wie heute, da frage ich mich, was aus der glorreichen Ankündigung von ZFS unter OS X geworden ist? HFS+, das aktuelle Dateisystem von OS X, ist nämlich schon sehr in die Jahre gekommen und ähnlich wie ein NTFS, nämlich auswechslungswürdig. ZFS sollte bereits in LION implementiert werden, 2006 gabs bereits Developer-Screenshots mit ZFS unter LION. Selbst eine Website hatte Apple bereits eingerichtet, nur, um selbige dann sang und klanglos wieder zu entfernen. Sogar der Chefentwickler ging und somit ist klar, dass ZFS nicht so bald in OS X Einzug halten wird.

ZFS wurde ursprünglich unter dem Namen *Zettabyte Filesystem* von der Firma SUN entwickelt. Es geht einen radikal neuen Ansatz wie man mit Dateien umgeht. Es hat ausschließlich Features im Gegensatz zu anderen Dateisystemen und unter Betriebssystemen wie FreeBSD lässt es sich bereits problemlos nutzen.

Der ehemalige Entwickler der bei Apple das ZFS implementieren sollte, hat nach seinem Weggang eine eigene Firma gegründet und arbeitet an einer Lösung, ZFS zumindest im Userspace als Dateisystem in OSX zu integrieren - Zevo. Dies ist nun gelungen und die Software in stabiler Version zum Kauf bereit. 19 Euro kostet die sogenannte Einstiegs-Silver-Edition, weitere Editionen mit weiteren Features werden im Laufe des Jahres folgen. Leider kann man OSX damit nicht von ZFS booten und anderen Features wie Deduplication fehlen.

Zur theoretischen Kapazität von ZFS kursiert folgendes Zitat:

> “Populating 128-bit file systems would exceed the quantum limits of earth-based storage. You couldn't fill a 128-bit storage pool without boiling the oceans.”
> 
> „Ein 128-Bit-Dateisystem zu füllen, würde die quantenmechanische Grenze irdischer Datenspeicherung übersteigen. Man könnte einen 128-Bit-Speicher-Pool nicht füllen, ohne die Ozeane zu verdampfen.“
> 
> – Jeff Bonwick, Chefentwickler von ZFS

Letztendlich bleibt also festzustellen, dass nativer ZFS-Support in OS X wahrscheinlich auch nicht mit dem bald erwarteten 10.8 Berglöwe Einzug halten wird. Ich hoffe, Apple besinnt sich bald wieder und kümmert sich um wichtige Dinge unter der Haube, so wie mit 10.6 als Feature von 10.5...

`**Artikelfoto**: Quelle [http://opensolaris.org/os/features/ (archiviert)](http://web.archive.org/web/20091026013207/http://www.opensolaris.org:80/os/features/)`
