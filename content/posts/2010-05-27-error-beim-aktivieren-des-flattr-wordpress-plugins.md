---
title: Error beim Aktivieren des Flattr Wordpress Plugins
slug: error-beim-aktivieren-des-flattr-wordpress-plugins
date_published: 2010-05-27T10:08:57.000Z
date_updated: 2018-08-22T09:38:22.000Z
---

Wenn ihr, so wie ich, folgenden Fehler bei der Aktivierung des Flattr-Plugins erhaltet, fehlt eurem Weblog die Unterstützung für **PHP 5**.

Folgender Fehler erschien bei mir:

    Parse error: syntax error, unexpected T_CONST, expecting T_OLD_FUNCTION or T_FUNCTION or T_VAR or '}' in /yourdomain.com/wp-content/plugins/flattr/flattr.php  on line 13

Laut meinem Webhoster ([all-inkl.com](http://www.all-inkl.com/index.php?partner=242411)) muss ich in der Datei `.htaccess` im Wurzelverzeichnis meines Webservers folgende Zeile eintragen, um PHP 5 zu aktivieren:

    #Für PHP5-CGI:
    AddHandler php5-cgi .php

Kurz speichern, das wars auch schon. Jetzt einfach noch mal versuchen, das Plugin zu aktivieren und nun sollte alles funktionieren und ihr könnt Flattr benutzen.

Übrigens kann der Fehler in ähnlicher Art und Weise natürlich auch mit jedem anderen Plugin, was PHP 5 benötigt, auftreten. Der Workaround ist der gleiche. Allerdings müsst ihr das nur ein mal in die `.htaccess` eintragen, um es dauerhaft zu aktivieren.

PS: Frank hat in einem [Kommentar](__GHOST_URL__/27/error-beim-aktivieren-des-flattr-wordpress-plugins/comment-page-1#comment-37077) eine weitere, technisch saubere Lösung des Problems beschrieben.
