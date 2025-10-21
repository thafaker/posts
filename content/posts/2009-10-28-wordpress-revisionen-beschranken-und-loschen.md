---
title: Wordpress Revisionen beschränken und löschen
slug: wordpress-revisionen-beschranken-und-loschen
date_published: 2009-10-27T23:07:36.000Z
date_updated: 2018-08-22T09:38:59.000Z
---

Sie kennen das Problem: Wordpress ist sehr langsam, die Suche nach einem Begriff dauert ewig und überhaupt, am Liebsten würde man auf eine schnellere Blogsoftware umsteigen und Wordpress nur noch aus Gesprächen Anderer kennen. Aber halt, solch drastischer Schritt muss vielleicht gar nicht nötig sein.

Ich habe nämlich mal ein wenig rumgespielt und neulich meine Datenbank angeschaut und festgestellt, dass meine `wp_posts.sql`, jener Teil der Wordpress-Datenbank welcher die Einträge enthält, allein **15,8 MB** groß ist. Krass, wah? Reiner Text, mit Links und so, mehr ist da nicht drin, eigentlich. Na auf jeden Fall kann das elende Wordpress ja verschiedene Revisionen von ein und dem selben Artikel bereit halten.

Und klar, jedes Mal wenn man auf *Speichern* klickt, schreibt er den ganzen Text noch mal in die Datenbank. Das sorgt dafür, dass die Datenbank rapide anwächst weil sich alles doppelt, aber nur einer wirklich angezeigt wird.

Der erste Schritt zur Lösung dieses Problems könnte die Beschränkung der Revisionen sein. Man trägt in der Datei `wp-config.php` folgende Zeile ein `"define ('WP_POST_REVISIONS', 3);"` (ohne Anführungsstriche) um die Anzahl der Artikelüberarbeitungen auf maximal 3 (wobei 3 natürlich jede natürliche Zahl sein kann) zu beschränken, von vorn herein. Die bereits existierenden Revisionen werden dadurch aber nicht gelöscht, das betrifft nur neue Artikel. Um nun die Datenbank aber mal komplett aufzuräumen und eventuelle alte Artikelüberarbeitungen zu löschen, empfiehlt sich laut diesem **[Forenbeitrag (archiviert)](http://web.archive.org/web/20100218153250/http://forum.wordpress-deutschland.org:80/plugins-und-widgets/38865-artikelueberarbeitungen-loeschen.html)** folgender SQL-Befehl:

---
`DELETE
FROM wp_posts
WHERE `wp_posts`.`post_type` = "revision"`
---

Und das hat mir meine `wp_posts.sql` auf unglaubliche 5,9 MB verkleinert. Einfach nur dadurch, weil unnützer, doppelt und dreifach vorhandener Inhalt gelöscht worden ist.

Der Befehl muss übrigens im phpMyAdmin Interface und SQL eingefügt und mit OK bestätigt werden.

Mein Weblog fühlt sich jetzt auch schon viel schneller an und meine Datenbank ist keine 58 MB sondern nur noch 51,4 MB groß :-)

PS: Alle Hinweise und Infos auf eigene Gefahr, wir können hier nicht auch noch für Probleme und Fehler haften!
