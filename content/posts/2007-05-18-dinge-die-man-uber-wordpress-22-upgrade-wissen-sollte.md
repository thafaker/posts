---
title: Dinge die ich über Wordpress 2.2 wissen sollte
slug: dinge-die-man-uber-wordpress-22-upgrade-wissen-sollte
date_published: 2007-05-18T09:18:32.000Z
date_updated: 2018-08-22T09:37:58.000Z
---

Wordpress 2.2 ist toll :-(

1. Widgets sind nun direkt in den Wordpress-Kern integriert, man benötigt das [Automattic-Widget-Plugin](http://automattic.com/) nicht mehr. Da beginnt auch bereits das erste Problem: Internet Explorer kann nicht richtig damit umgehen. Er verkackt die Widget-Leiste im Admin-Menü, man kann sie also nicht umher schieben oder wieder entfernen. Workaround ist, den Firefox zu benutzen. PS: Fehler tritt nur mit integriertem Widgets im WP 2.2 auf.
2. Ausführende PHP-Widgets, allen voran das berühmte [King-Text-Widget (archiviert)](http://web.archive.org/web/20060515142126/http://www.blog.mediaprojekte.de:80/cms-systeme/wordpress-plugins/wordpress-widget-king-text/), funktionieren nicht mehr. Sie erwarten das Sidebar-Widget-Plugin von Automattic welches es ja nun nicht mehr gibt. Es existiert bis dato noch kein Workaround für King-Text. Nach langem suchen habe ich dann endlich das [ExecPHP-Widget](http://ottodestruct.com/blog/2006/04/09/fun-with-widgets/) gefunden. Jenes funktioniert bei mir problemlos mit PHP-Code in der Sidebar, meine doofe Tagwolke ist direkt ausgeführter PHP-Code. ZUSATZ: Es ist nun auch ein Fehler in Verbindung mit dem ExecPHP-Widget aufgetaucht: >>Folks using multiple ExecPHP widgets may run into difficulty with only the first widget contents being echoed on the blog.<< Das Inhalt des ersten Widgets wird zerhackt, allerdings nur wenn man mehr als 1 ExecPHP Widget in der Sidebar stehen hat. Dies ist ein Bug im Widget selbst. Es existiert aber bereits ein [Workaround](http://trac.wordpress.org/ticket/4275#comment:5) von *Ryan Boren*.
3. Mal sehen wann mein Weblog wieder hergestellt ist
4. [...](http://technosailor.com/10-things-you-should-know-about-wordpress-22/)

[tags]Wordpress, widgets, Weblog, 2.2, Blog, Fehler, firefox, Internet Explorer, PHP, Plugin, fix.it[/tags]
