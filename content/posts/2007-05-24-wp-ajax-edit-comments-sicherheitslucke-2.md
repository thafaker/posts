---
title: Wp-Ajax-Edit-Comments // Sicherheitslücke
slug: wp-ajax-edit-comments-sicherheitslucke-2
date_published: 2007-05-24T17:34:00.000Z
date_updated: 2018-08-22T09:37:58.000Z
---

Soeben erreichte mich folgende Mail des deutschen [WP-Ajax-Plugin-Weblog-Menschen](__GHOST_URL__/18/wp-ajax-edit-comments-kommentare-noch-mal-bearbeiten/).

**Kurz und knapp**: Wp-Ajax-Edit-Comments weist eine Sicherheitslücke auf.

[wp-ajax-edit-comments wichtiges update](http://dmay.net/blog/?p=331)

`Die Mail gibt es nach dem Klick!`

Der Autor des Wordpress Plugins Wp-Ajax-Edit-Comments, Ronald Huereca, hat mich gerade angeschrieben und mir mitgeteilt, dass es eine Sicherheitslücke in seinem Plugin gebe. Mich hat er angeschrieben, weil ich das Plugin übersetzt habe und für ihn auch Supportanfragen aus dem deutschsprachigen Raum übernehme.

Wie ich dazu komme, euch anzuschreiben? Entweder habt ihr eure Mailadresse in den Kommentaren zu meinem Blogartikel zu der deutschen Version des Plugins hinterlassen, was mich dazu veranlasst hat zu glauben, ihr würdet das Plugin bei euch nutzen, oder ihr wart beim Suchbegriff "wp ajax edit comments" bei technorati unter den ersten Ergebnissen.

Zur Sicherheitslücke: (Ronald möchte nicht, das Details zu der Lücke in Blogs veröffentlicht werden; würde die genaue Art der Lücke bekannt werden, steigt die Möglichkeit, dass es von jemandem ausgenutzt wird) Das Plugin arbeitet mit Cookies. Diese lassen sich manipulieren, so dass jeder User einen beliebigen Kommentar, auf unbegrenzte Zeit, bearbeiten könnte. Er muss nur die CommentID wissen. In der neuen Version wird die IP des Kommentators (Hash-Wert) und das sekundengenaue Datum zusätzlich zu der CommentID im Cooki gepeichert. Um ein Cookie zu manipulieren müssten eben diese beiden Werte bekannt sein, was nahezu unmöglich ist.

Wenn ihr noch andere Leute kennt, die das Plugin nutzen, weist sie bitte auch auf die aktualisierte Version hin.

David May
