---
title: Wordpress 2.8.6 steht zum Download bereit [Update]
slug: wordpress-2-8-6-steht-zum-download-bereit
date_published: 2009-11-12T19:32:15.000Z
date_updated: 2018-08-22T09:38:58.000Z
---

[![wordpressorg](//www.thafaker.de/wp-content/uploads/2008/04/wordpressorg.jpg) (archiviert)](http://web.archive.org/web/20101130212733/http://thafaker.de/wp-content/uploads/2008/04/wordpressorg.jpg)[**Original**] Gerade kam es via **Twitter** zu den Menschen. Wordpress hat ein Sicherheitsupdate seiner gleichnamigen, sehr berühmten Blogging-Software veröffentlicht. Bisher gibt es den Artikel allerdings erst in englischer Spracher: 2.8.6 fixes two security problems that can be exploited by registered, logged in users who have posting privileges.  If you have untrusted authors on your blog, upgrading to 2.8.6 is recommended.

The first problem is an XSS vulnerability in Press This discovered by Benjamin Flesch.  The second problem, discovered by Dawid Golunski, is an issue with sanitizing uploaded file names that can be exploited in certain Apache configurations. Thanks to Benjamin and Dawid for finding and reporting these.

**[Get WordPress 2.8.6](http://wordpress.org/download/)**

Nun gibt es bereits den [**deutschen Artikel** (archiviert)](http://web.archive.org/web/20091115080349/http://blog.wordpress-deutschland.org:80/2009/11/12/wordpress-2-8-6-de-edition-und-upgradepaket.html) zum Update mit allen wichtigen Funktionen und Links.**
**

[**Update**] **Soeben wurde WordPress 2.8.6 veröffentlicht. Diese Version ist ein Sicherheitsrelease und behebt [ein Problem](http://core.trac.wordpress.org/ticket/11122), durch das auf bestimmten Apache-Installationen Dateien wie “foto.php.jpg” als Code ausgeführt werden können.**

Das Problem tritt unter bestimmten Einstellungen des Apache-Webservers auf, wenn in der Konfiguration “AddHandler application/x-httpd-php .php” eingesetzt wird (allerdings ist AddType, dass z.B. bei Strato zum Einsatz kommt, unbetroffen). Des weiteren wurden eine [XSS-Lücke](http://core.trac.wordpress.org/ticket/11119) geschlossen.

- **→**[**Download WordPress 2.8.6 DE-Edition**](http://wordpress-deutschland.org/download/deutsch)

Die offizielle englischsprachige Version 2.8.6 kann im [Downloadbereich](http://wordpress-deutschland.org/download/englisch/) runtergeladen werden. Die offizielle deutschsprachige Version auf [de.wordpress.org](http://de.wordpress.org/) steht ebenfalls zur Verfügung.

Wer die Vorgängerversion 2.8.5 benutzt und nicht die automatische Updatefunktion verwenden möchte, kann mit dem Upgradepaket eine Aktualisierung durchführen. Das Upgradepaket beinhaltet alle geänderten Dateien zu der Vorgängerversion 2.8.5 und kann für ein Upgrade der offiziellen- und der DE-Edition benutzt werden. Es gibt zur Vorgängerversion 2.8.5 keine Änderungen in der Datenbank.

- **→**[**Upgradepaket für 2.8.5 auf 2.8.6**](http://counter.wordpress-deutschland.org/dlcount.php?id=static&amp;url=/upgradepaket/fix-285-to-286.zip)

In der DE-Edition ist die aktuelle Sprachdatei und das übersetzte Standardtheme enthalten. Die Sprachdatei kann auch seperat runtergeladen werden:

- **→****[Sprachdatei für WordPress 2.8.6](http://wordpress-deutschland.org/download/sprachdatei/)**

**Wie vor jeder Aktualisierung solltet ihr immer ein vollständiges Backup aller Dateien und der Datenbank anlegen – auch wenn ihr die automatische Updatefunktion benutzt!**
