---
title: Wordpress 3.0 Multiblog
slug: wordpress-3-0-multiblog
date_published: 2010-06-20T10:54:35.000Z
date_updated: 2018-08-22T09:38:21.000Z
---

Diese neue Funktion ist vielen vielleicht noch gar nicht bekannt, aber mit der Veröffentlichung von **Wordpress 3.0** haben die Entwickler die beiden Versionen Wordpress und Wordpress MU (MU meint Multi User) zusammen gelegt, so das man nun aus einer einzigen Wordpress-Installation mehrere Weblogs mit unterschiedlichen Domains und Subdomains betreiben kann.

Die Funktion ist per Default allerdings deaktiviert und muss zuerst über einen Eintrag in der Datei `wp-config.php` aktiviert werden.

    define('WP_ALLOW_MULTISITE', true);

Nach einem erneuten Login hat man nun unter *Werkzeuge* im Wordpress Backend einen neuen Menüpunkt mit der Bezeichnung *Blog-Netzwerk* in der deutschen Version, in der englischen Version heißt er *Networks*.

[![wordpress_3.0_MU_true](//picdump.thafaker.de/2010/06/wordpress_3.0_MU_true-580x336.png)](http://picdump.thafaker.de/2010/06/wordpress_3.0_MU_true.png)

Nach einem Klick auf *Installieren* erscheint eine Seite mit diversen Anweisungen, die auf den ersten Blick etwas verwirrend aussehen mögen. Aber sie sind überhaupt kein Problem, wenn man den Anweisungen Schritt für Schritt Folge leistet.

1. 
Erstellt ein neues Verzeichnis Namens `blogs.dir` im Pfad
`/Pfad/zum/Wordpress/wp-content`.

In diesem Verzeichnis werden die hochgeladene Dateien von den Blogs deines Blog-Netzwerks gespeichert. Dieses Verzeichnis muss durch den Webserver beschreibbar sein.

2. 
Man fügt folgenden Code in die Datei `wp-config.php` im Wordpress-Verzeichnis (wie oben schon beschrieben) über der Zeile
`/* That’s all, stop editing! Happy blogging. */` ein:

    define( 'MULTISITE', true );
    define( 'SUBDOMAIN_INSTALL', false );
    $base = '/wordpress/';
    define( 'DOMAIN_CURRENT_SITE', 'test.thafaker.de' );
    define( 'PATH_CURRENT_SITE', '/wordpress/' );
    define( 'SITE_ID_CURRENT_SITE', 1 );
    define( 'BLOG_ID_CURRENT_SITE', 1 );

Achtung: es fehlen noch folgende Sicherheitsschlüssel in der `wp-config.php` um die Wordpress-Installation sicherer zu machen. Folgendes hinzufügen:

    define( 'AUTH_SALT', 'Q|pT1@l.-+%cZ YXa1/A<1u~M|Y]-~[`Cdwub)a-peY4Zt=+|w2rcyQ-<>{tp~~!' );
    define( 'SECURE_AUTH_SALT', ')` WYKCd4Rk&#P!b*+rJU}tRj-|(}vJ.2Eh:5U1%fitN+Psc ? Ni <2@o|!F4;|' );
    define( 'LOGGED_IN_SALT', 'C![Nm M.B5W0ekX!>FM]F%-$Xt{+rVFUf[Z`0GG#!gyv~OA3Uc#87SyDgV84#*5P' );
    define( 'NONCE_SALT', 'rD+M|Rv-q`b<.Pz~}-pF1Es+pnk|K2?S7qbMCfL%s3acy+sj-Uh^m&/ [*$aa
    1. Jetzt wird die versteckte Datei .htaccess im Verzeichnis von Wordpress (wo auch die wp-config.php liegt) editiert, diesmal überschreibt man mit folgendem Code eventuell bereits vorhandene WordPress Rewrite-Regeln.
    
    
        RewriteEngine On
        RewriteBase /wordpress/
        RewriteRule ^index\.php$ - [L]
        
        # uploaded files
        RewriteRule ^([_0-9a-zA-Z-]+/)?files/(.+) wp-includes/ms-files.php?file=$2 [L]
        
        # add a trailing slash to /wp-admin
        RewriteRule ^([_0-9a-zA-Z-]+/)?wp-admin$ $1wp-admin/ [R=301,L]
        
        RewriteCond %{REQUEST_FILENAME} -f [OR]
        RewriteCond %{REQUEST_FILENAME} -d
        RewriteRule ^ - [L]
        RewriteRule  ^([_0-9a-zA-Z-]+/)?(wp-(content|admin|includes).*) $2 [L]
        RewriteRule  ^([_0-9a-zA-Z-]+/)?(.*\.php)$ $2 [L]
        RewriteRule . index.php [L]
    
    
    1. Das wars auch schon, wenn man diese Schritte durchgegangen ist, sollte Wordpress als Multiblog Variante laufen. Nach einem erneuten Login sollte alles funktionieren.
    
    
    Wie das mit der Konfiguration geht, beschreibt auch ein Artikel auf [Wordpress-Deutschland (archiviert)](http://web.archive.org/web/20100526014923/http://blog.wordpress-deutschland.org:80/2010/05/23/multi-blog-funktion-in-wordpress-3-0-aktivieren.html).
    
