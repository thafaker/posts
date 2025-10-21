---
title: Wordpress 3.4.2 Update steht zum Download bereit [UPDATE]
slug: wordpress-3-4-2-update-steht-zum-download-bereit
date_published: 2012-09-07T07:04:25.000Z
date_updated: 2018-08-22T09:39:13.000Z
---

Und wieder ein mal überrascht mich kalt und an einem Freitag das aktuellste Wordpress Update, auf Version [3.4.2](http://wordpress.org/news/2012/09/wordpress-3-4-2/): Mit dem Release werden [20 Fehler](http://core.trac.wordpress.org/query?status=closed&amp;resolution=fixed&amp;milestone=3.4.2&amp;group=resolution&amp;order=severity&amp;desc=1) behoben. Die Änderungen betreffen den Theme Customizer, die Browserkompatibilität, die PHP Abwärtskompatibilität oder die Theme Schnittstellen. Gleichzeitig werden mit dem Update mögliche **Sicherheitslücken geschlossen**, die unter anderem Multisite-Installationen betreffen. Da es sich um Ein Sicherheitsupdate handelt, wird die Installation jedem Blogger empfohlen.

**Download****Vollversio**n

- Deutsch [ZIP](http://de.wordpress.org/wordpress-3.4.2-de_DE.zip) / [TAR.GZ](http://de.wordpress.org/wordpress-3.4.2-de_DE.tar.gz)(noch nicht fertig)
- Englisch [ZIP](http://wordpress.org/latest.zip) / [TAR.GZ](http://wordpress.org/latest.tar.gz)

Ansonsten steht das Update wie immer im Backend von Wordpress selbst als automatische Variante zur Verfügung. Zuvor sollte allerdings immer ein Update durchgeführt werden, niemand haftet für eventuelle Schäden die durch ein Update entstehen könnten.

## Summary

From the [announcement post](http://wordpress.org/news/2012/09/wordpress-3-4-2/), this maintenance release addresses 18 bugs with version 3.4 and 3.4.1, including:

- Fixes some issues in the admin area where some older browsers (IE7, in particular) may slow down, lag, or freeze.
- Fixes an issue where a theme may not preview correctly, or its screenshot may not be displayed.
- Fixes the use of multiple trackback URLs in a post.
- Prevents improperly sized images from being uploaded as headers from the customizer.
- Ensures proper error messages can be shown to PHP4 installs. (WordPress requires PHP 5.2.4 or later.)
- Fixes handling of oEmbed providers that only return XML responses.
- Addresses pagination problems with some category permalink structures.
- Adds more fields to be returned from the XML-RPC wp.getPost method.
- Avoids errors when updating automatically from very old versions of WordPress (pre-3.0).
- Fixes problems with the visual editor when working with captions.

Additionally: Version 3.4.2 fixes a few security issues and contains some security hardening. These issues were discovered and addressed by the WordPress security team:

- Fix unfiltered HTML capabilities in multisite.
- Fix possible privilege escalation in the Atom Publishing Protocol endpoint.
- Allow operations on network plugins only through the network admin.
- Hardening: Simplify error messages when uploads fail.
- Hardening: Validate a parameter passed to wp_get_object_terms().

A full log of the changes made for 3.4.2 can be found at [http://core.trac.wordpress.org/changeset?old_path=%2Ftags%2F3.4.1&old=21780&new_path=%2Ftags%2F3.4.2&new=21780](http://core.trac.wordpress.org/changeset?old_path=%2Ftags%2F3.4.1&amp;old=21780&amp;new_path=%2Ftags%2F3.4.2&amp;new=21780)
