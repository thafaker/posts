---
title: Glacier und ARQ = best longtime Backup-Solution fürn Mac
slug: glacier-und-arq-best-longtime-backup-solution-furn-mac
date_published: 2012-11-29T16:14:28.000Z
date_updated: 2018-08-22T09:39:16.000Z
---

![ARQ icon](//picdump.thafaker.de/2012/11/arqIcon230-100x100.png)Ich bin ja so ein Typ, der immer gern backuped, aber eigentlich noch nie darauf angewiesen war. Dennoch fühle ich mich gut, wenn beispielsweise meine ganzen Hausarbeiten, die *BA Thesis* oder aktuell eben die *Master Thesis* nicht nur auf meinem Macbook Air liegen, sondern auch auf meinem USB Stick und eventuell noch in der Dropbox, sodass ich diese wirklich lebenswichtigen Daten mehrfach vorgehalten habe, redundant eben. 

Das ist für so kleine Daten wie eben Textdateien und Kram relativ easy, 10 GB Dropbox nimmt man bequem noch locker auf nem USB-Stick mit, die passen auf einen aktuellen 7 euro 16GB Stick locker drauf etc., was aber passiert, wenn ich auch gern meine MP3-Sammlung und meine Bilder sichern möchte? Beides jeweils über 100 GB groß? Da wird es dann bereits schwierig, da kann ich dann eigentlich nur noch auf externe Datenträger wie USB-Laufwerke zurück greifen, die auch erst mal eine gewisse Sicherheit bieten. Aber was, gesetzt den Fall, meine Wohnung wird ausgebraubt und die nehmen einfach alles mit was rumliegt oder… sie brennt ab? Dann wären alle meine Fotos der letzten 15 Jahren auf immer verloren, ganze Menschen würden dann nicht mehr exisiteren und so. Eine krasse Vorstellung. Also will ich neben der USB-Platte noch ein weiteres Backup-Medium, was groß genug ist damit all das Platz hat und was nicht unendlich viel kostet.

Hier kommt [Amazons Glacier](http://aws.amazon.com/de/glacier/) zum Einsatz, ein Langzeit-Online-Backup der nur 1 Cent pro Gigabyte pro Monat kostet. Um Glacier auf einem Mac sinnvoll einsetzten zu können, sollte man das Programm [**ARQ** (archiviert)](http://web.archive.org/web/20121203074456/http://www.haystacksoftware.com:80/arq/) nutzen, welches in Version 3 auch den neuen Amazon-Speicherdienst Glacier nutzt und sonst auch Amazons bisher schon bekannten S3 Speicher für Datenübertragungen und Backups nutzen kann.

Was genau ist **Glacier**?: Der Amazon-Dienst speichert Daten langfristig und eben sehr günstig für 1 Cent pro Gigabyte. Das Rückspielen dagegen ist aber eher umständlich (Nach Anforderung der Daten verstreichen 3-5 Stunden) und wird von Amazon in Rechnung gestellt, wenn ein bestimmte Freivolumen (aktuell 5 Prozent der gesamt gespeicherten Daten) überschritten ist. Glacier ist nicht der tägliche Backup Speicher auf den man ständig zugreift, sondern sowas wie die letzte Sicherung für den absoluten Ernstfall. Wie früher Magnetbänder, die man auch nur im Notfall aus dem Archiv geholt und zurück gespielt hat. Aber auch für Glacier ist das Tool Arq durchdacht: Das Programm berechnet vor dem Rückspielen die Download-Geschwindigkeit und gibt an, wie viel das Rückspielen dauern wird. Und, mal Hand aufs Herz: Wer würde nicht 30 Tacken zahlen, wenn die lokalen Daten von 2 Terabyte kaputt sind?

Die Nutzung ist simpel und effektiv: Lokales Verzeichnis und Speicherort (Amazon S3 oder Glacier) auswählen, schon werden die Daten stündlich (bei S3) oder täglich (bei Glacier) in die Amazon-Wolke gesichert. Ein GByte kostet bei S3 12 US-Cent pro Monat und bei Glacier gar nur 1 Cent. Wer also 100 GByte sichern möchte, zahlt dafür zwischen 12 und 1 US-Dollar im Monat. Das ist zwar aufs Jahr gerechnet teuer als eine externe USB-Festplatte  - aber eben auch sicherer, denn Amazon garantiert eine 99,999999999 Prozent Zuverlässigkeit der Daten. Die Daten werden von Arq übrigens VOR der Übertragung zu Amazon mit einem frei wählbaren 256-bit-Schlüssel verschlüsselt.

Und die Nachteile? Die Sicherung/Übertragung von 100 GByte dauert über eine DSL-Leitung ewig (mehrere Tage), das betrifft aber eigentlich nur die erste Grund-Sicherung. Die  tägliche Sicherung der seither aktualisierten Daten geht viel schneller, weil sie inkrementell erfolgt und wirklich nur die Daten übertragen werden, die sich geändert haben, ähnlich TimeMachine. Und wer wie ich einen [100MBit](__GHOST_URL__/schwanzvergleich-2/)-Anschluss nutzt, sichert seine 100 GByte innerhalb eines Tages.

[![g1](//picdump.thafaker.de/2012/11/g1-580x220.png)](http://picdump.thafaker.de/2012/11/g1.png)

[![g2](//picdump.thafaker.de/2012/11/g2-580x270.png)](http://picdump.thafaker.de/2012/11/g2.png)

[![g3](//picdump.thafaker.de/2012/11/g3-580x527.png)](http://picdump.thafaker.de/2012/11/g3.png)

Sexy, diese Vorstellung eines dauerhaften Online-Speichers, oder nicht? Leider dauert die Übertragung von 100 GB bei heutigen Leutungen durchaus ne Woche und das ist schon ne ziemlich große Barriere.
