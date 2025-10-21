---
title: Wordpress 3.0.2 steht zum Download bereit
slug: wordpress-3-0-2-steht-zum-download-bereit
date_published: 2010-12-01T15:54:13.000Z
date_updated: 2018-08-22T09:38:16.000Z
---

![wordpress-logo_grey-xl](//picdump.thafaker.de/2010/09/wordpress-logo_grey-xl-150x150.png)Wie immer, wenn ich mich in mein Backend einlogge, gibt es ein [Update von Wordpress](http://codex.wordpress.org/Version_3.0.2) :-) Das ist natürlich nur Spaß, ich logge mich weit öfter als ein Mal pro Monat ein. Aber dennoch finde ich es immer eine Erwähnung wert. Wie Wordpress-Deutschland in seinem Blog [schreibt (archiviert)](http://web.archive.org/web/20101204044218/http://blog.wordpress-deutschland.org:80/2010/12/01/wordpress-3-0-2-de-edition-veroeffentlicht.html), steht bereits die aktualisierte deutsche Version bereit und kann automatisch über die Update-Funktion installiert werden.

**Download**:

Die offizielle englischsprachige Version 3.0.2 kann im [Downloadbereich](http://wordpress-deutschland.org/download/englisch/) von Wordpress-Deutschland herunter geladen werden. Die offizielle deutschsprachige Version auf [de.wordpress.org](http://de.wordpress.org/) steht ebenfalls zur Verfügung.

Wer die Vorgängerversion 3.0.1 benutzt und nicht die automatische  Updatefunktion verwenden möchte, kann mit dem Upgradepaket eine  Aktualisierung durchführen. Das Upgradepaket beinhaltet alle geänderten  Dateien zu der Vorgängerversion 3.0.1 und kann für ein Upgrade der  offiziellen- und der DE-Edition benutzt werden. Es gibt zur  Vorgängerversion 3.0.1 keine Änderungen in der Datenbank.

**Änderungen**:

-  Fix moderate security issue where a malicious Author-level user could gain further access to the site. ([r16625](http://core.trac.wordpress.org/changeset/16625))

Other bugs and security hardening:

-  Remove pingback/trackback blogroll whitelisting feature as it can easily be abused. ([#13887](http://core.trac.wordpress.org/ticket/13887))
-  Fix canonical redirection for permalinks containing %category% with nested categories and paging. ([#13471](http://core.trac.wordpress.org/ticket/13471))
-  Fix occasional irrelevant error messages on plugin activation. ([#15062](http://core.trac.wordpress.org/ticket/15062))
-  Minor XSS fixes in request_filesystem_credentials() and when deleting a plugin. ([r16367](http://core.trac.wordpress.org/changeset/16367), [r16373](http://core.trac.wordpress.org/changeset/16373))
-  Clarify the license in the readme ([r15534](http://core.trac.wordpress.org/changeset/15534))
-  Multisite: Fix the delete_user meta capability ([r15562](http://core.trac.wordpress.org/changeset/15562))
-  Multisite: Force current_user_can_for_blog() to run map_meta_cap() even for super admins ([#15122](http://core.trac.wordpress.org/ticket/15122))
-  Multisite: Fix ms-files.php content type headers when requesting a URL with a query string ([#14450](http://core.trac.wordpress.org/ticket/14450))
-  Multisite: Fix the usage of the SUBDOMAIN_INSTALL constant for upgraded WordPress MU installs ([#14536](http://core.trac.wordpress.org/ticket/14536))
