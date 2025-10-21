---
title: Kömmentäre
slug: kommentare
date_published: 2009-09-23T13:52:23.000Z
date_updated: 2018-08-22T09:38:59.000Z
---

Nach 3 Jahren des Defekts habe ich es heute endlich mal geschafft, meine Umlaute in den Kommentaren alter Artikel (bis Mitte 2007) zu repaieren. Es trug sich nämlich zu, so **[Anfang 2005](__GHOST_URL__/11/ich-habe-nun-ein-weblog)**, als ich von einem kostenlosen Webspace auf Lycos-Tripod zu Puretec (heute 1und1) wechselte, das der Export... nee, ganz anders.

Zuerst hatte ich ja auf Lycos ein [**B2Evolution**](http://b2evolution.net/) genanntes Weblog-System laufen. Dieses wollte ich aber aus verschiedenen Gründen irgendwann nicht mehr und versuchte nun, b2evo auf Wordpress zu migrieren. Wir reden hier von 2005. Allerdings gab es damals noch keine echten Möglichkeiten daür, sodass ich mir mit einem PHP-Script zu helfen versuchte, welches dann direkt aufgerufen alle Informationen aus Wordpress ausliest und in eine Textdatei speicherte. Diese wiederum konnte ich in mein [**Wordpress importieren**](__GHOST_URL__/09/von-b2evolution-zu-wordpress). Und dabei starben das erste mal Umlaute.

Allerdings nicht nur in den **[Kommentaren](__GHOST_URL__/24/wie-schnell-die-zeit-vergeht)** sondern auch in den Beiträgen selbst.

Durch viel umherprobiere und so, unter anderem mit verschiedenen Zeichencodierungen dirket in der `wp-config`, konnte ich aber dem Problem Herr werden. Damals. Und dann zog ich nach Puretec um. Und hatte wieder Probleme. Und letztendlich landete ich ja bei meinem aktuellen Horster, [**all-inkl.com**](http://www.all-inkl.com/index.php?partner=242411) mit dem ich sehr zufrieden bin. Der wiederum hatte zu alte oder neuere MySQL Versionen laufen sodas ein Ex/Import nicht richtig klappte, aber im großen und ganzen waren meine alten Beiträge importiert, sodas ich mich später nicht mehr darum kümmerte, aber meine Umlaute weiterhin defekt waren.

Wie dem auch sei, heute habe ich dann endlich mal die `wp-comments` herunter geladen (6 MB Kommentare), in einem Texteditor geöffnet und einfach durch *Suchen & Ersetzen* alle kaputten Umlaute durch ö ä oder ü ersetzt. Und wieder hoch geladen. Und siehe da, es klappt. Alles heile, scheinbar, nix verschwunden, nix gelöscht. Respekt.

*Amen*
