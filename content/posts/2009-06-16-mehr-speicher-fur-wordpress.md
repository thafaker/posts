---
title: Mehr Speicher für Wordpress
slug: mehr-speicher-fur-wordpress
date_published: 2009-06-16T14:25:15.000Z
date_updated: 2018-08-22T09:39:02.000Z
---

Weil Wordpress in seiner Standardkonfiguration bereits **32 MB Arbeitsspeicher** verleiert und dieser Wert teilweise sogar schon überschritten wird, ist mehr Speicher grundsätzlich gut. Allerdings bieten nicht viele Hoster Ihren Kunden dieses "Mehr" von Speicher an. Prinzipiell muss man in Wordpress die Datei `wp-config.php` editieren, um einen höheren Wert händisch einstellen zu können

[![](//picdump.thafaker.de/2009/06/wp_memory-thumb1.jpg)](http://picdump.thafaker.de/2009/06/wp_memory.jpg)Nach Lektüre [**dieses**](http://bueltge.de/mehr-speicher-fuer-wordpress/957/) und [**jenes**](http://alexrabe.boelinger.com/2009/06/14/dear-hoster-we-need-more-memory/) Artikels habe ich das bei mir natürlich sofort mit selbigem [**Plugin**](http://wordpress.org/extend/plugins/wp-memory-usage/) überprüft und erkannt, dass meine Installation *serverseitig* mit 32 MB lief und aktuell aber schon bei 31 MB am Ende meiner Leistungsreserve stand.

[![](//picdump.thafaker.de/2009/06/wp_config-thumb.jpg)](http://picdump.thafaker.de/2009/06/wp_config.jpg)Ich habe nun also auch in 3 Schritten mein Limit aufgebohrt und leicht bekleidet abgecheckt. Letztendlich kann ich nun sagen, dass selbst *bei 128 MB Speicher keine Probleme fest gestellt werden konnten*, ich also einen freundlichen **Hoster** habe der mir scheinbar nicht so schnell das Wasser abdrehen würde, wenn es darauf ankommen möge und ich deshalb hoch erfreut bin. Denn in jedem *Computer-Heinz* steckt doch meistens auch ein *Tuning-Fred* oder *Overclocking-Horst*.

Meine Website wird übrigens von [**All-Inkl.com**](http://www.all-inkl.com/index.php?partner=242411) (*Affiliate Link*) gehostet.

Gerade entdeckt, kann wohl auch [**Thomas**](http://www.nicht-spurlos.de/wordpress/wp-motortuning/) meine Einschätzung über **All-Inkl.com** bestätigen, denn auch sein Wordpress läuft mit 128 MB problemlos.
