---
title: WP-Supercache
slug: wp-supercache
date_published: 2010-09-24T13:05:00.000Z
date_updated: 2018-08-22T09:38:17.000Z
---

AHA. Schon mal über das Plugin **WP-Supercache** ([Link](http://wordpress.org/extend/plugins/wp-super-cache/)) gestolpert oder vielleicht sogar selbst in Betrieb gehabt? Es verbessert die Geschwindigkeit eines Wordpress-Weblogs, indem es häufig abgerufene Inhalte cached. Ich schon. Und ich bin fast geplatzt vor lauter Unbehagen. Feste Seiten beispielsweise hat es nie ordentlich aktualisiert, also, die Seite ist im Web nicht korrekt angezeigt worden und es gab nur Probleme damit, teilweise war der Inhalt dann richtig durcheinander. Sogar Änderungen auf Pages die in der Sidebar durchgeführt worden sind, wollte es partout nicht aktualisieren. Manchmal bringt deaktivieren etwas. Aber das Plugin verstrickt sich tief ins System und ändert beispielsweise die `.htaccess` Datei. Deinstallieren kann man das Plugin aber auch nicht, weil es den Vorgang mit einer kruden Fehlermeldung quittiert.

**Meine Vorgehensweise**:

1. Plugin deaktivieren. Dann per FTP auf den Webspace verbinden und den Ordner wp-supercache im Verzeichnis /dein weblog/wp-content/wp-plugins/ löschen.
2. Nun per FTP in den Ordner /dein weblog/ navigieren und dort die Ordner, die wie deine Seiten heißen, löschen. Hier lag der Hase im Pfeffer, diese sorgten dafür, dass die alten Inhalte nicht aktualisiert worden sind.
3. Jetzt mit einem Editor die Datei `.htaccess`, ebenfalls im untersten Verzeichnis deines Weblogs, öffnen und den von Supercache hinzugefügten Code wieder löschen.

Die Datei sollte danach so wie hier (Standard-Wordpress-Installation) aussehen:

    # BEGIN WordPress
    
    RewriteEngine On
    RewriteBase /
    RewriteCond %{REQUEST_FILENAME} !-f
    RewriteCond %{REQUEST_FILENAME} !-d
    RewriteRule . /index.php [L]
    
    # END WordPress
    

Speichern... und das wars. Nun sollte euer Weblog wieder wie erwartet und ohne **WP-Supercache** funktionieren.

PS: Alles auf eigene Gefahr, thafaker kann keine Haftung übernehmen. Bei mir hat der oben beschriebene Weg funktioniert, aber, garantieren kann ich sowas nie.
