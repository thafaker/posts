---
title: Wordpress Datenbank aufräumen [Update]
slug: wordpress-datenbank-aufraumen
date_published: 2010-03-04T10:46:22.000Z
date_updated: 2018-08-22T09:38:25.000Z
---

Weil ich gerade wieder akute Probleme mit der SQL-Datenbank habe (Artikel aufrufen und so Zeugs) und mir eine Lösung überlegen musste, habe ich mal ein wenig das Netz durchforstet, was man gegen eine zu fette Wordpress Datenbank tun kann.

Meine `wp-posts` Tabelle ist war unglaubliche `72 Megabyte` groß. Eigentlich schon viel zu fett, um sie überhaupt noch sichern zu können. Warum die so riesig ist, liegt nicht zuletzt an den vielen Artikel die es hier gibt (3257 an der Zahl), sondern vielmehr auch an den Revisionen die bei jedem Speichern angelegt werden. Eine Revision ist dafür da, verschiedene Versionen eines Artikels zu haben und dort wieder hin wechseln zu können, sie werden automatisch angelegt und es gibt keine Begrenzung. Wenn einem mal der Browser abstürzt, ist das natürlich recht sinnvoll weil man den Artikel durch die Revision wieder holen kann oder ganz simpel, um Änderungen an dem Artikel nachvollziehen zu können. Aber was ist mit Artikeln von vor nem Jahr, die quasi 20 mal in der Datenbank liegen. Die Datenbank hat sich dadurch bei mir sozusagen verachtfacht.

**Lösungswege**:

1. Die Wordpress-Datenbank sichern ist der wichtigste Schritt, denn man weiß ja nie, was passieren kann wenn man "am Herzen operiert".
2. Man kann in der `wp-config.php` eine Beschränkung einstellen, wie viele Revisionen zukünftig pro Artikel gespeichert werden. Diese habe ich auf 1 eingestellt. Fügt einfach folgende Zeile zu eurer wp-config.php hinzu:

    define('WP_POST_REVISIONS', 1);

3. Nun wird zukünftig nur noch eine Revision pro Artikel gespeichert. Was aber tut man mit all den alten Revisionen? Man löscht sie einfach per SQL-Befehl. Dazu loggt man sich in seinem phpMyAdmin ein, welches bei vielen Hostern zur Verwaltung der Datenbank dient und gibt dort unter dem Punkt "SQL" folgenden Befehl ein:

    DELETE FROM  wp_posts WHERE  post_type = "revision";

Dies sorgt nun dafür, das die `wp-posts` nach Revisionen durchsucht wird und diese gelöscht werden. Auswirkungen auf die Artikel selbst hat es natürlich nicht. Nur auf lästigen Ballast.
4. Am Schluss führen wir noch einen SQL-Befehl aus, welcher die geleerte `wp-posts` aufräumt und optimiert.

    OPTIMIZE TABLE  wp_posts;

Das wars auch schon. Die Datenbank sollte erheblich entschlackt worden sein und eventuell merkt man das auch in der Geschwindigkeit, wie das Weblog oder Wordpress nun agiert.

Meine `wp-posts` Tabelle ist von 72 MB auf unglaubliche 15 MB geschrumpft. Hammer, oder?

[**Update**] Mario hat mich darauf hingewiesen, dass es mit diesem Weg zu einer inkonsistenten Datenbank kommen kann

> Leider hast Du danach aber eine leidlich inkonsistente Datenbank, da der ganze Schutt in wp_postmeta, der über die post_id mit der ursprünglichen, nun gelöschten, Revision verknüpft war, noch da ist…
> 
> Und auch wp_term_relationships, verknüpft über object_id, sollte berücksichtigt werden.

Aber klug wie er ist, hat er auch gleich eine Möglichkeit genannt, wie man das Problem beheben kann. Natürlich ausschließlich auf eigene Gefahr. Ich habe das soeben selbst verifiziert und es hat problemlos funktioniert.

    delete meta
    from wp_postmeta as meta
    left join wp_posts as post
    on (post.id = meta.post_id)
    where post.id is null

Und dann noch folgenden Befehl einfach kopieren und wie oben schon beschrieben, ausführen.

    delete termrel
    from wp_term_relationships as termrel
    left join wp_posts as post
    on (post.id = termrel.object_id)
    where post.id is null

So sah das dann bei mir aus:
[![wp_postmeta](//picdump.thafaker.de/2010/03/wp_postmeta-580x387.png)](http://picdump.thafaker.de/2010/03/wp_postmeta.png)
[![wp_term_rela](//picdump.thafaker.de/2010/03/wp_term_rela-580x369.png)](http://picdump.thafaker.de/2010/03/wp_term_rela.png)

Das wars nun aber wirklich :-)

**HINWEIS**: Bitte beachten Sie den folgenden [Kommentar](__GHOST_URL__/wordpress-datenbank-aufraumen/#comment-38239), inwiefern er generell gilt und maßgeblich ist, kann ich allerdings nicht verifizieren.

---

[**Update**] Der Mainboarder hat auf [seiner Website ein Script erstellt (archiviert)](http://web.archive.org/web/20150517000256/http://mainboarder.de:80/artikel/2273/aktualisiert-datenbankoptimierungs-snippet.html), welches man monatlich per Cronjob laufen lassen kann. Man muss hier lediglich eine php Datei auf seinem Webserver anlegen, das Script hinein kopieren, oben die Daten seiner eigenen Email, Datenbank sowie Passwort ändern und das wars auch schon. Bei mir funktioniert das noch immer absolut problemlos, Dank an Mainboarder.

---

**Quelle**: [yourinspirationweb.com](http://www.yourinspirationweb.com/en/how-to-clean-up-your-wordpress-database/?utm_source=feedburner&amp;utm_medium=feed&amp;utm_campaign=Feed%3A+yourinspirationweb%2FHuJt+%28Your+Inspiration+Web%29)
