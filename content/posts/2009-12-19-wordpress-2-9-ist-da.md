---
title: Wordpress 2.9 ist da [Update]
slug: wordpress-2-9-ist-da
date_published: 2009-12-19T10:16:28.000Z
date_updated: 2018-08-22T09:38:59.000Z
---

[**Update**] Wordpress Deutschland hat die Lokalisation bereits erfolgreich durchgeführt und online gestellt. Mehr gibt es im offiziellen **[Weblog (archiviert)](http://web.archive.org/web/20091221204639/http://blog.wordpress-deutschland.org:80/2009/12/19/wordpress-2-9-carmen.html)** des Projektes.

- [**Download der deutschen Version** (Link nicht mehr verfügbar)](http://counter.wordpress-deutschland.org/dlcount.php?id=static&amp;url=/de-edition/latest.zip) (*.Zip, 2,6 MB)

[**Original**]
**[![wordpressorg](//picdump.thafaker.de/2008/04/wordpressorg.jpg)](http://picdump.thafaker.de/2008/04/wordpressorg.jpg)****[WordPress 2.9](http://wordpress.org/development/2009/12/wordpress-2-9/) steht seit [heute (archiviert)](http://web.archive.org/web/20091221022730/http://blog.wordpress-deutschland.org:80/2009/12/19/wordpress-2-9-veroeffentlicht.html) zum Download, vorerst allerdings nur in der englischen Version, bereit. Wie Wordpress-Deutschland schreibt, soll auch die lokalisierte Version im Laufe des Tages auf deren Website zur Verfügung stehen.**

- **[Download der englischen Version](http://wordpress.org/latest.zip)** (*.Zip, 2.2 MB)

Eine automatische Aktualisierung sollte ebenfalls über das Backend möglich sein und steht bei mir ebenfalls zur Verfügung.
![wordpress_2.9](//picdump.thafaker.de/2009/12/wordpress_2.9.jpg)
Es folgt eine Zusammenfassung zu **Wordpress 2.9** vom [**blog.wordpress-deutschland.org** (archiviert)](http://web.archive.org/web/20091221004911/http://blog.wordpress-deutschland.org:80/2009/12/18/wordpress-2-9-eine-uebersicht-der-neuen-funktionen.html) über die neuen Funktion.

- 
### Neue Voraussetzung

Wer auf WordPress 2.9 aktualisieren möchte oder eine Neuinstallation aufsetzen möchte benötigt mindestens die MySQL-Version **4.1.2**. Wer also noch MySQL 4.0.0 verwendet kann kein Update auf die neue Version durchführen. Nutzer der automatischen Aktualisierung erhalten eine Warnung.

- 
### Highlights

**Mülleimer**

Mit WordPress 2.9 werden Artikel, Seiten, Kommentare und Anhänge nicht sofort gelöscht, sondern wandern erstmal in den Mülleimer, wo sie wiederhergestellt oder endgültig gelöscht werden können.

**Artikelbilder (”post thumbnails”)**

Jede gute Nachrichtenseite fügt zur Veranschaulichung ein Bild zu jedem Artikel hinzu. In WordPress war dies bisher nur mit einer Pluginlösung oder den benutzerdefinierten Feldern möglich. Version 2.9 baut dies nun fest ein. Damit es funktioniert, muss [das Theme diese Funktion auch unterstützen (archiviert)](http://web.archive.org/web/20100114022153/http://dynamicinternet.eu:80/blog/2009-12-17/the-ultimative-guide-for-the_post_thumbnail-in-wordpress-2-9/)

**“oEmbed”**

Auch war es bisher eine Qual, Flash-Videos, wie die von YouTube z.B., in Artikel einzufügen. WordPress 2.9 unterstützt nun den Standard “[oEmbed](http://oembed.com/)“, der das Einfügen von externen Medien jeglicher Art ermöglicht. Mehr zu diesem Thema findet sich [in diesem Beitrag (archiviert)](http://web.archive.org/web/20091016194119/http://blog.wordpress-deutschland.org:80/2009/10/15/noch-einfacher-videos-bilder-einbinden-mit-oembed-in-wordpress-2-9.html).

**Bildbearbeitung**

WordPress 2.9 ermöglicht es nun Bilder zu bearbeiten. Somit sind für Standardaufgaben wie Schneiden, Drehen und Spiegeln, nicht mehr externe Programme notwendig.

**Plugin-Massenaktualisierung**

Für Menschen die Bequemlichkeit zu ihren Eigenschaften zählen, macht WordPress 2.9 das Leben noch einfacher. Über “Werkzeuge -> Autoupdate” kann man nun alle Plugins auf einen Schlag aktualisieren.

**“Custom Post Types”-API**

Für die Entwickler gibt es nun eine neue API, die es erlaubt verschiedene Artikeltypen anzulegen. Bisher erlaubt diese Änderung nur die Berücksichtigung in den verschiedenen API-Funktionen, wie z.B. query_posts oder WP_Query, jedoch automatisch passende Felder im Backend werden erst mit WordPress 3.0 angelegt.

- 
### Weitere Neuerungen

- Im HTML-Headbereich wird nun [rel=”canonical”](http://googlewebmastercentral.blogspot.com/2009/02/specify-your-canonical.html) gesetzt um doppelten Content zu vermeiden.
- Das Backend erhält eine Geschwindigkeitsoptimierung mit Zusammenfassen der Stylesheet-Dateien und Verbesserung der jQuery-Skripte.
- Um für Kategorie- und Tag-Seiten eigene Template-Dateien zu nutzen, müsste man bisher immer z.B. categorie-ID.php nutzen. WordPress 2.9 erlaubt nun die Nutzung des Slugs, also category-SLUG.php. Das selbe wurde auch für Seiten eingeführt (page-ID.php & page-SLUG.php).
- Das Export- und Importformat “WXR” unterstützt nun auch Sticky Posts und Custom Taxonomies.
- Datenbank-Tabellen können direkt aus WordPress heraus repariert und optimiert werden.
- In WordPress wird man aus Sicherheitsgründen nach einer bestimmten Zeit automatisch abgemeldet. WordPress 2.9 zeigt nun, falls dies eintritt und man einen Artikel bearbeitet, ein Popup, um sich neu einzuloggen.
- Im Default-Theme “Kubrick” können Seiten nun auch Kommentare haben (z.B. um es als Gästebuch einzusetzen).
- Die Funktion “get_excerpt()”, die es erlaubt einen Artikelauszug anzuzeigen, kann nun [via Plugin-API in der Funktionalität beeinflusst werden (archiviert)](http://web.archive.org/web/20100211113642/http://blog.wordpress-deutschland.org:80/2009/09/10/excerpt-ab-wordpress-2-9.html).
- JSON-Funktionen, die in PHP erst mit Version 5.2 und höher zur Verfügung stehen, werden für ältere PHP-Versionen zurück portiert, um den Einsatz von AJAX zu erleichtern.
- Durch Austausch der Sprachdatei-Lesefunktion in der Komponente “POMO” wurde Speichernutzung und Geschwindigkeit verbessert.
- Mit der neuen Funktion “get_delete_post_link()” kann man, ähnlich der Funktion “get_edit_post_link()”, ein Link zum direkten Löschens eines Artikels erzeugen.
- Ähnlich den benutzerdefinierten Feldern, im englischen Custom Fields genannt, erhalten Kommentare, vorerst nur via API, das selbe mit der “Comment Meta API”.
- Plugins können in WordPress 2.9 Verzeichnisse anmelden, in denen WordPress nach Themes sucht. [Haupteinsatzzweck für diese Neuerung ist BuddyPress (archiviert)](http://web.archive.org/web/20091224012315/http://buddypress.de:80/blog/2009/10/buddypress-neuerung-mit-wordpress-mu-2-9.html).
- Mit add_theme_support(”feature”) and current_theme_supports(”feature”) können Plugin- und Theme-Autoren bestimmte Funktionen, wie z.B. Unterstützung für Artikelbilder, anmelden und danach prüfen.

Eine ausführliche [Übersicht aller Änderungen](http://codex.wordpress.org/Version_2.9) findet sich in der englischsprachigen Dokumentation.
