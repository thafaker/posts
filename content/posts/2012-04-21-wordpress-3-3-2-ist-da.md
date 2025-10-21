---
title: Wordpress 3.3.2 ist da
slug: wordpress-3-3-2-ist-da
date_published: 2012-04-20T22:02:41.000Z
date_updated: 2018-08-22T09:38:10.000Z
---

![wordpress-logo_grey-xl](//picdump.thafaker.de/2010/09/wordpress-logo_grey-xl.png)Pünktlich zum Start der Diablo 3 Beta gibt es plötzlich auch eine neue Version Wordpress. Diesmal hört sie auf **Version 3.3.2** und stellt ein Sicherheitsrelease dar, behebt also verschiedene Sicherheitslücken und einige kleinere Fehler. Eine Aktualisierung auf die neue Version 3.3.2 wird dringend empfohlen.

Die offizielle deutschsprachige Version auf [de.wordpress.org](http://de.wordpress.org/) steht zur Verfügung und wird im Administrationsbereich zur automatischen Aktualisierung angeboten. Die Version von Wordpress-Deutschland.org gibt es [hier](http://wpde.org/download/deutsch/).

**Vor jeder Aktualisierung unbedingt ein vollständiges Backup aller Dateien und der Datenbank anlegen – auch wenn die automatische Updatefunktion verwendet wird!**

[![Download Wordpress de 3.3.2](//picdump.thafaker.de/2012/04/Bildschirmfoto-2012-04-20-um-23.59.15.png)](http://de.wordpress.org/wordpress-3.3.2-de_DE.zip)

## Summary

Three external libraries included in WordPress received security updates:

- Plupload (version 1.5.4), which WordPress uses for uploading media.
- SWFUpload, which WordPress previously used for uploading media, and may still be in use by plugins.
- SWFObject, which WordPress previously used to embed Flash content, and may still be in use by plugins and themes.

WordPress 3.3.2 also addresses:

- Limited privilege escalation where a site administrator could deactivate network-wide plugins when running a WordPress network under particular circumstances.
- Cross-site scripting vulnerability when making URLs clickable.
- Cross-site scripting vulnerabilities in redirects after posting comments in older browsers, and when filtering URLs.

A full log of the changes made for 3.3.2 can be found at [http://core.trac.wordpress.org/changeset?new=20554%40branches%2F3.3&old=20087%40branches%2F3.3](http://core.trac.wordpress.org/changeset?new=20554%40branches%2F3.3&amp;old=20087%40branches%2F3.3)
