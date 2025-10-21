---
title: Wie entpacke ich ein iPhone Backup - SMS.db
slug: wie-entpacke-ich-mein-iphone-backup-sms-db
date_published: 2010-07-22T16:18:06.000Z
date_updated: 2018-08-22T09:38:19.000Z
---

Ich habe mich beim Umstieg vom 3Gs auf mein iPhone 4 auch mal mit den Möglichkeiten beschäftigt, wie man zum Beispiel, an die SMS im Backup vom 3Gs kommt, um sie eventuell ins iPhone 4 zu kopieren. Da ich einen Mac besitze, habe ich es auch auf diesem durchgeführt. Ob die Programme auch für Windows existieren, ist mir unbekannt.

---

WERBUNG
!function(d, s, id) {
    var js, pjs = d.getElementsByTagName(s)[0];
    if (d.getElementById(id)) return;
    js = d.createElement(s);
    js.id = id;
    js.src = "http://player-services.goviral-content.com/embed-code/index/find?placementVersionId=169349451334851202369755";
    pjs.parentNode.insertBefore(js, pjs);
}(document, 'script', 'gv_script_169349451334851202369755');
---

Zunächst einmal ist es wichtig, das dass Backup nicht verschlüsselt ist. Klar, die Verschlüsselung ist ja dafür da, unbefugten Zugriff zu verhindern und somit hat man auch keinen Zugriff darauf. 

## Die ist eine Anleitung wie man die Backups welche iTunes vom iPhone erstellt, mit Hilfe vom *iPhone Backup Extractor for Mac* entpackt.

- **1. Schritt**

Ladet den **iPhone Backup Extractor**[**hier** (archiviert)](http://web.archive.org/web/20101130091229/http://supercrazyawesome.com/downloads/iPhone%20Backup%20Extractor.app.zip) herunter und speichert ihn auf dem Mac

- **2. Schritt
**

Klickt doppelt auf das Archiv und entpackt es, dann zieht ihr das Programm in den Programme-Ordner.
[![18697](//picdump.thafaker.de/2010/07/18697.png)](http://picdump.thafaker.de/2010/07/18697.png)
- **3. Schritt
**

Klickt doppelt auf das *iPhone Backup Extractor* Symbol um die App es zu starten
[![18696](//picdump.thafaker.de/2010/07/18696.png)](http://picdump.thafaker.de/2010/07/18696.png)
- **4. Schritt
**

Klickt den *Read Backups* Knopf, das Programm wird dann alle verfügbaren Backups die es findet, anzeigen.
[![18699](//picdump.thafaker.de/2010/07/18699.png)](http://picdump.thafaker.de/2010/07/18699.png)
[![18698](//picdump.thafaker.de/2010/07/18698.png)](http://picdump.thafaker.de/2010/07/18698.png)

- **5. Schritt
**

Es öffnet sich eine Liste mit allen verfügbaren Backups. Jetzt wählt man jenes, welches man entpacken möchte.[![backup_liste](//picdump.thafaker.de/2010/07/backup_liste.png)](http://picdump.thafaker.de/2010/07/backup_liste.png)
- **6. Schritt
**

iPhone  Backup Extractor wird dann eine Liste mit  verschiedenen Programmeinstellungen anzeigen. Jetzt wählt man, was man haben möchte, und klickt den *Extract* button an.
[![18703](//picdump.thafaker.de/2010/07/18703.png)](http://picdump.thafaker.de/2010/07/18703.png)
Hinweis:  Ich habe die *iPhone OS Files* gewählt, weil sie die ganzen Dinge wie SMS, Kontaket und so weiter enthalten.

- **7. Schritt
**

Nun wird man gefragt, wo man die entpackten Dateien speichern will. Einfach neuen Ordner erstellen oder in einen vorhandenen entpacken, *Choose* button klicken, fertig.
[![](//www.iclarified.com/images/tutorials/4974/18704/18704-500.png)](http://www.iclarified.com/images/tutorials/4974/18704/18704.png)
- **8. Schritt
**

Es öffnet sich automatisch der Ordner mit den entpackten Dateien, wenn er fertig ist.
[![18706](//picdump.thafaker.de/2010/07/18706.png)](http://picdump.thafaker.de/2010/07/18706.png)
So, da liegen nur die gesamten Inhalte des iPhones. Man kann nun gern mal damit rum spielen und sich mit den Files beschäftigen, viel Erfolg.

HINWEIS: Viele der Dateien haben eine *.sqlitedb* oder .*db* Erweiterung.Diese Datenbank-Dateien können mit dem Programm **Sqlite Database Browser** geöffnet werden. Man kann es [hier](http://sourceforge.net/projects/sqlitebrowser/) herunter laden.

`Dieser Artikel stammt von [iClarified](http://www.iclarified.com/entry/index.php?enid=4974).`

## Wie komme ich nun aber an die SMS? Eine sehr einfache Sache, eigentlich.

- **1. Schritt
**

Ladet euch das Programm **Sqlite Database Browser**[hier](http://sourceforge.net/projects/sqlitebrowser/) herunter.

- **2. Schritt**

Entpackt es, und verschiebt es in den Programme-Ordner

- **3. Schritt**

Startet die Applikation durch einen Doppelklick.
[![Bildschirmfoto 2010-07-22 um 17.54.14](//picdump.thafaker.de/2010/07/Bildschirmfoto-2010-07-22-um-17.54.14.png)](http://picdump.thafaker.de/2010/07/Bildschirmfoto-2010-07-22-um-17.54.14.png)
- **4. Schritt**

Klickt auf *Öffnen* und wählt aus dem (wie oben beschrieben) Backup die Datei **sms.db** aus.
[![Bildschirmfoto 2010-07-22 um 18.03.14](//picdump.thafaker.de/2010/07/Bildschirmfoto-2010-07-22-um-18.03.14.png)](http://picdump.thafaker.de/2010/07/Bildschirmfoto-2010-07-22-um-18.03.14.png)
Nun sollte sich folgendes Bild zeigen:
[![Bildschirmfoto 2010-07-22 um 18.06.02](//picdump.thafaker.de/2010/07/Bildschirmfoto-2010-07-22-um-18.06.02-580x485.png)](http://picdump.thafaker.de/2010/07/Bildschirmfoto-2010-07-22-um-18.06.02.png)
- **5. Schritt**

Wählt jetzt oben File --> Export --> Table as CSV File
[![export_sms](//picdump.thafaker.de/2010/07/export_sms.png)](http://picdump.thafaker.de/2010/07/export_sms.png)
Dann wählt ihr aus, welche Tabelle ihr aus der Datei exportieren wollt. In diesem Fall die Nachrichten.
[![table_sms](//picdump.thafaker.de/2010/07/table_sms.png)](http://picdump.thafaker.de/2010/07/table_sms.png)
Nun noch den Dateinamen eingeben, zum Beispiel sms.csv und dann könnt ihr die Datei mit einem Programm was CSV Dateien lesen kann, Excel kann es, öffnen und die SMS Nachrichten zumindest lesen. *Das wars auch schon*.

Wie man allerdings nun mit diesem Wissen die sms.db in ein neues, anderes Backup integrieren (verschmelzen) kann, ist mir leider nicht bekannt. Sinnvoll könnte diese Szenarion sein, wenn man wie ich nicht das alte Backup vom iPhone 3Gs auf dem neuen iPhone 4 wiederherstellen möchte, doch aber auf die vielen SMS-Konversationen nicht verzichten will.

---

*WERBUNG*

---
