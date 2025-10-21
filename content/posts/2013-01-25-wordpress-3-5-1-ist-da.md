---
title: Wordpress 3.5.1 ist da
slug: wordpress-3-5-1-ist-da
date_published: 2013-01-25T12:54:23.000Z
date_updated: 2018-08-22T09:38:51.000Z
---

![wordpress-logo_grey-xl](//picdump.thafaker.de/2010/09/wordpress-logo_grey-xl-150x150.png)Update Update Update. Heute mal wieder eine aktuelle Version von Wordpress, Version 3.5.1 ist da. Das erste Update zum großen 3.5 ist ein Sicherheits- und Wartungsupdate und wird allen Betreibern von Wordpress angeraten. 

Vorher aber gilt wie immer: Datenbank sichern, Verzeichnis sichern --> Updaten

Das Update wird euch im Backend angezeigt, oder ihr könnt es [hier](http://de.wordpress.org/wordpress-3.5.1-de_DE.tar.gz) (de, tar.gz, 5,8 MB) und [hier](http://wpde.org/download) (wpde) downloaden.

#### Siehe auch

→ [offizielles Entwicklerstatement](http://wordpress.org/news/2013/01/wordpress-3-5-1/)

→ [Übersicht der in 3.5.1 behobenen Fehler](http://core.trac.wordpress.org/query?milestone=3.5.1)

→ [WordPress in 5 Minuten installieren](http://wpde.org/installation)

→ [Wie führe ich ein Upgrade durch?](http://faq.wpde.org/wie-fuhre-ich-ein-upgrade-durch/)

→ [Informationen zu den Upgradepaketen](http://faq.wpde.org/upgradepakete/)

→ [Die WordPress-Versionsnummern](http://blog.wpde.org/2008/12/05/die-wordpress-versionsnummern.html)

#### Summary

From the [announcement post](http://wordpress.org/news/2013/01/wordpress-3-5-1/), this maintenance release addresses 37 bugs with version 3.5, including:

- Editor: Prevent certain HTML elements from being unexpectedly removed or modified in rare cases.
- Media: Fix a collection of minor workflow and compatibility issues in the new media manager.
- Networks: Suggest proper rewrite rules when creating a new network.
- Prevent scheduled posts from being stripped of certain HTML, such as video embeds, when they are published.
- Work around some misconfigurations that may have caused some JavaScript in the WordPress admin area to fail.
- Suppress some warnings that could occur when a plugin misused the database or user APIs.

Additionally: Version 3.5.1 fixes a few security issues:

- Server-side request forgery (SSRF) and remote port scanning via pingbacks. Fixed by the WordPress security team.
- Cross-site scripting (XSS) via shortcodes and post content. Discovered by Jon Cave of the WordPress security team.
- Cross-site scripting (XSS) in the external library Plupload. Plupload 1.5.5 was released to address this issue.

Eine vollständige Zusammenfassung aller Änderungen gibt es [hier](http://core.trac.wordpress.org/log/branches/3.5?rev=23341&amp;stop_rev=23167).
