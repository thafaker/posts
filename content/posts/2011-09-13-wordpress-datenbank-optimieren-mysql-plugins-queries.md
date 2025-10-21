---
title: Wordpress Datenbank optimieren. MySQL, Plugins, Queries... [UPDATE]
slug: wordpress-datenbank-optimieren-mysql-plugins-queries
date_published: 2011-09-13T20:43:19.000Z
date_updated: 2018-08-22T09:38:31.000Z
---

Meine Wordpress-Datenbank ist unkomprimiert 55,7 MB groß. Das finde ich unglaublich. Die `wp-posts` allein hat 37 MB. Klar habe ich im Leben dieser Website bereits recht viel geschrieben, so 6000 Artikel wahrscheinlich, aber... muss die wirklich so fett sein? Momentan beschäftigt mich die Größe der SQL-Datenbank mal wieder erheblich, weil ich -wie so oft- mit Geschwindigkeitsproblemen auf meiner Website zu kämpfen habe. Es zur Zeit meine Lieblingsbeschäftigung heraus zu finden, woran es liegt und wie ich es beheben kann. Leider bin ich noch nicht sehr weit gekommen.

Um heraus zu finden, wie lange eine Website lädt und welche Dateien, Bilder Bzw. Scripts so lange nerven, sei folgender Link empfohlen: [www.gajin.at (archiviert)](http://web.archive.org/web/20110923163938/http://www.gaijin.at:80/olsloadtime.php)

---

Generell, also als kleiner Tipp, sei folgendes Plugin angemerkt. `[WP-ImageHost](http://www.milchrausch.de/wordpress-plugin-wp-imagehost/)`. Dieses Plugin biegt die Links zu den Bildern auf eurer Website auf eine Subdomain (bei mir picdump.thafaker.de) um, diese zeigt in den wp-contents/upload Ordner. Es wird also nix verschoben. Aufgrund der Subdomain aber baut der Webbrowser mehr Verbindungen auf -weil er ja denkt es sei eine andere Website- und so lädt die Seite schneller. Bei mir funktioniert das erstaunlich gut.

---

[Hier](__GHOST_URL__/wordpress-datenbank-aufraumen/) habe ich mich vor einiger Zeit bereits mit dem Thema beschäftigt, der Inhalt funktioniert auch heute noch gut. Es folgt ein essentieller Auszug:

Ein Problem sind die Revisionen, welche Wordpress anlegt. Man beginnt einen neuen Artikel zu schreiben, und alle 2 Minuten legt WP eine automatische Sicherung (Revision) an. Eine nette Sache, was einem einen Neuanfang beim klicken eines falschen Link o.ä. sehr behilflich sein kann - oder wenn der Strom ausfällt und man den Artikel seines Lebens schreibt... (doch das geschieht nicht so oft). Das selbe geschieht auch mit Artikeln die bereits publiziert, und im Nachhinein geändert werden. Diese *Revisions* legen sich jedes mal in der DB ab, so daß sich nach nur kürzester Zeit eine Menge an Revisions, wie natürlich auch anderem “Müll” in der Datenbank ablagert. Das selbe geschieht natürlich auch bei regem Wechsel des Themes, oder Installationen und Deinstallationen von Plugins. Beides entfernt sich nicht immer sauber aus der Datenbank, und müllt auch so wieder zu. Dieses hat zur Folge, dass beim Aufruf einer Website die Anzahl an Queries von mal zu mal steigt.

Manche mögen nun unnötige Queries händisch aus der Datenbank bügeln, anderen fehlt entweder das Wissen oder es stellt für sie kein Problem dar. Egal wie, es wird durch diesen Müll der Zugriff auf die Datenbank auf Dauer extrem behindert, und damit die Schnelligkeit einer Seite ebenso.

**Lösungswege**:

1. Die Wordpress-Datenbank sichern ist der wichtigste Schritt, denn man weiß ja nie, was passieren kann wenn man "am Herzen operiert".
2. Man kann in der `wp-config.php`eine Beschränkung einstellen, wie viele Revisionen zukünftig pro Artikel gespeichert werden. Diese habe ich auf 1 eingestellt. Fügt einfach folgende Zeile zu eurer wp-config.php hinzu:

    define('WP_POST_REVISIONS', 1);

3. Nun wird zukünftig nur noch eine Revision pro Artikel gespeichert. Was aber tut man mit all den alten Revisionen? Man löscht sie einfach per SQL-Befehl.
4. Dazu loggt man sich in seinem phpMyAdmin ein, welches bei vielen Hostern zur Verwaltung der Datenbank dient und gibt dort unter dem Punkt "SQL" folgenden Befehl ein:

    delete meta
    from wp_postmeta as meta
    left join wp_posts as post
    on (post.id = meta.post_id)
    where post.id is null

5. Und dann noch folgenden Befehl einfach kopieren und wie oben schon beschrieben, ausführen.

    delete termrel
    from wp_term_relationships as termrel
    left join wp_posts as post
    on (post.id = termrel.object_id)
    where post.id is null

6. So sah das dann bei mir aus:
[![wp_postmeta](//picdump.thafaker.de/2010/03/wp_postmeta-580x387.png)](http://picdump.thafaker.de/2010/03/wp_postmeta.png)[![wp_term_rela](//picdump.thafaker.de/2010/03/wp_term_rela-580x369.png)](http://picdump.thafaker.de/2010/03/wp_term_rela.png)
Das ganze muss man aber heutzutage nicht mehr per Hand machen, sondern kann es -richtig- durch ein Plugin automatisieren. Ich habe folgendes Plugin `DB-Optimize` ([Link](http://wordpress.org/extend/plugins/db-optimize/)) laufen und das funktioniert gut. Empfehlenswert ist weiterhin das Plugin `[WP-Optimize](http://www.ruhanirabin.com/wp-optimize/)`. Nach der Installation legt es sich im Backend in der Sidebar ab.
[![wp-optimize](//picdump.thafaker.de/2011/09/wp-optimize-150x150.png)](http://picdump.thafaker.de/2011/09/wp-optimize.png)
### Weiter mit den Queries.

Wenn Du selbst die Anzahl Deiner Queries testen willst gibt es bekannterweise natürlich einen einfachen Weg. Hierzu wird einfach im Footer oder der Single.php des Blogs folgende Syntax eingetragen:

        < ?php echo $wpdb->num_queries; ?>q, < ?php timer_stop(1); ?>s

Nett, doch leider nicht das was ich brauche weil ich damit nicht feststellen kann, woher diese Queries kommen. Hier hat Bueltge ein nettes Plugin namens `[Debug Queries](http://bueltge.de/wordpress-performance-analysieren-plugin/)` geschrieben, das meinem Zweck doch sehr entgegen kommt. Es listet im Footer alle Datenbankabfragen auf und ich kann erkennen, dass meine Frontpage thafaker.de allein 87 Abfragen startet und gleich zu Beginn ein riesengroßer Klumpen kommt, den ich kaum deuten kann. BÄM. Jetzt kann ich mich auf die Suche begeben, nachdem nun meine Datenbank geschrumpft und optimiert sowie  alle lästigen Plugins entfernt sind...

Ach ja, hat jemand ne Idee zu folgendem Screenshot... ?
[![schreckliche_queries_bueltge](//picdump.thafaker.de/2011/09/schreckliche_queries_bueltge-580x451.png)](http://picdump.thafaker.de/2011/09/schreckliche_queries_bueltge.png)[![Bildschirmfoto 2011-09-19 um 13.07.59](//picdump.thafaker.de/2011/09/Bildschirmfoto-2011-09-19-um-13.07.59-580x424.png)](http://picdump.thafaker.de/2011/09/Bildschirmfoto-2011-09-19-um-13.07.59.png)
Hier noch mal ausführlich, was der Klumpen ausgibt.

        Time: 0.000999927520752
        Query: UPDATE `wp_options` SET `option_value` = 'a:8:{i:0;b:0;s:27:\"a-year-before/ayb_posts.php\";s:19:\"ayb_posts_deinstall\";s:38:\"simple-tags/2.7/simple-tags.client.php\";a:2:{i:0;O:15:\"SimpleTagsAdmin\":12:{s:7:\"version\";s:5:\"1.6.6\";s:4:\"info\";a:4:{s:4:\"home\";s:18:\"http://thafaker.de\";s:7:\"siteurl\";s:18:\"http://thafaker.de\";s:11:\"install_url\";s:53:\"http://thafaker.de/wp-content/plugins/simple-tags/2.7\";s:11:\"install_dir\";s:65:\"/www/htdocs/w0089eb9/wordpress/wp-content/plugins/simple-tags/2.7\";}s:7:\"options\";a:64:{s:13:\"use_tag_pages\";i:1;s:18:\"allow_embed_tcloud\";i:0;s:9:\"no_follow\";i:0;s:14:\"auto_link_tags\";i:0;s:13:\"auto_link_min\";i:1;s:14:\"auto_link_case\";i:1;s:21:\"auto_link_max_by_post\";i:20;s:14:\"use_click_tags\";i:1;s:18:\"use_suggested_tags\";i:1;s:18:\"use_autocompletion\";i:1;s:14:\"use_embed_tags\";i:1;s:16:\"start_embed_tags\";s:6:\"[tags]\";s:14:\"end_embed_tags\";s:7:\"[/tags]\";s:7:\"rp_feed\";i:0;s:11:\"rp_embedded\";s:2:\"no\";s:8:\"rp_order\";s:10:\"count-desc\";s:12:\"rp_limit_qty\";i:5;s:13:\"rp_notagstext\";s:26:\"Keine passenden Eintraege!\";s:8:\"rp_title\";s:22:\"
    #### Related posts
    \";s:10:\"rp_xformat\";s:95:\"[%post_title%](\"%post_permalink%\") (%post_comment%)\";s:12:\"rp_adv_usage\";s:0:\"\";s:15:\"cloud_selection\";s:10:\"count-desc\";s:10:\"cloud_sort\";s:6:\"random\";s:15:\"cloud_limit_qty\";i:20;s:16:\"cloud_notagstext\";s:15:\"Keine TAGs, Man\";s:11:\"cloud_title\";s:25:\"
    #### Kleine Tag-Wolke
    \";s:12:\"cloud_format\";s:4:\"flat\";s:13:\"cloud_xformat\";s:155:\"[%tag_name%](\"%tag_link%\")\";s:15:\"cloud_max_color\";s:7:\"#000000\";s:15:\"cloud_min_color\";s:7:\"#CCCCCC\";s:14:\"cloud_max_size\";i:15;s:14:\"cloud_min_size\";i:4;s:10:\"cloud_unit\";s:2:\"pt\";s:14:\"cloud_inc_cats\";i:0;s:15:\"cloud_adv_usage\";s:0:\"\";s:7:\"tt_feed\";i:0;s:11:\"tt_embedded\";s:2:\"no\";s:12:\"tt_separator\";s:2:\", \";s:9:\"tt_before\";s:6:\"Tags: \";s:8:\"tt_after\";s:6:\"
    \";s:13:\"tt_notagstext\";s:30:\"Keine TAGs fÃ¼r diesen Artikel\";s:9:\"tt_number\";i:0;s:11:\"tt_inc_cats\";i:0;s:10:\"tt_xformat\";s:64:\"[%tag_name%](\"%tag_link%\")\";s:12:\"tt_adv_usage\";s:0:\"\";s:9:\"rt_number\";i:5;s:8:\"rt_order\";s:10:\"count-desc\";s:12:\"rt_separator\";s:1:\" \";s:9:\"rt_format\";s:4:\"list\";s:9:\"rt_method\";s:2:\"OR\";s:8:\"rt_title\";s:21:\"
    #### Related tags
    \";s:13:\"rt_notagstext\";s:21:\"No related tag found.\";s:10:\"rt_xformat\";s:91:\"%tag_count%[+](\"%tag_link_add%\")[%tag_name%](\"%tag_link%\")\";s:19:\"rt_remove_separator\";s:1:\" \";s:16:\"rt_remove_format\";s:4:\"list\";s:20:\"rt_remove_notagstext\";s:1:\" \";s:17:\"rt_remove_xformat\";s:105:\"» [Remove %tag_name%](\"%tag_link_remove%\")\";s:15:\"meta_autoheader\";i:1;s:19:\"meta_always_include\";s:0:\"\";s:17:\"meta_keywords_qty\";i:0;s:13:\"use_auto_tags\";i:1;s:6:\"at_all\";i:0;s:8:\"at_empty\";i:0;s:9:\"auto_list\";s:165:\"a:9:{i:0;s:5:\"liebe\";i:1;s:9:\"wordpress\";i:2;s:11:\"persÃ¶nlich\";i:3;s:6:\"sexual\";i:4;s:8:\"software\";i:5;s:8:\"hardware\";i:6;s:5:\"apple\";i:7;s:3:\"mac\";i:8;s:4:\"cute\";}\";}s:15:\"default_options\";a:64:{s:13:\"use_tag_pages\";i:1;s:18:\"allow_embed_tcloud\";i:0;s:9:\"no_follow\";i:0;s:14:\"auto_link_tags\";i:0;s:13:\"auto_link_min\";i:1;s:14:\"auto_link_case\";i:1;s:21:\"auto_link_max_by_post\";i:20;s:14:\"use_click_tags\";i:1;s:18:\"use_suggested_tags\";i:1;s:18:\"use_autocompletion\";i:1;s:14:\"use_embed_tags\";i:0;s:16:\"start_embed_tags\";s:6:\"[tags]\";s:14:\"end_embed_tags\";s:7:\"[/tags]\";s:7:\"rp_feed\";i:0;s:11:\"rp_embedded\";s:2:\"no\";s:8:\"rp_order\";s:10:\"count-desc\";s:12:\"rp_limit_qty\";i:5;s:13:\"rp_notagstext\";s:24:\"Keine verwandten Artikel\";s:8:\"rp_title\";s:26:\"
    #### Verwandte Artikel
    \";s:10:\"rp_xformat\";s:95:\"[%post_title%](\"%post_permalink%\") (%post_comment%)\";s:12:\"rp_adv_usage\";s:0:\"\";s:15:\"cloud_selection\";s:10:\"count-desc\";s:10:\"cloud_sort\";s:6:\"random\";s:15:\"cloud_limit_qty\";i:45;s:16:\"cloud_notagstext\";s:11:\"Keine Tags.\";s:11:\"cloud_title\";s:18:\"
    #### Tag Cloud
    \";s:12:\"cloud_format\";s:4:\"flat\";s:13:\"cloud_xformat\";s:155:\"[%tag_name%](\"%tag_link%\")\";s:15:\"cloud_max_color\";s:7:\"#000000\";s:15:\"cloud_min_color\";s:7:\"#CCCCCC\";s:14:\"cloud_max_size\";i:22;s:14:\"cloud_min_size\";i:8;s:10:\"cloud_unit\";s:2:\"pt\";s:14:\"cloud_inc_cats\";i:0;s:15:\"cloud_adv_usage\";s:0:\"\";s:7:\"tt_feed\";i:0;s:11:\"tt_embedded\";s:2:\"no\";s:12:\"tt_separator\";s:2:\", \";s:9:\"tt_before\";s:5:\"Tags:\";s:8:\"tt_after\";s:6:\"
    \";s:13:\"tt_notagstext\";s:29:\"Keine Tags zu diesem Beitrag.\";s:9:\"tt_number\";i:0;s:11:\"tt_inc_cats\";i:0;s:10:\"tt_xformat\";s:64:\"[%tag_name%](\"%tag_link%\")\";s:12:\"tt_adv_usage\";s:0:\"\";s:9:\"rt_number\";i:5;s:8:\"rt_order\";s:10:\"count-desc\";s:12:\"rt_separator\";s:1:\" \";s:9:\"rt_format\";s:4:\"list\";s:9:\"rt_method\";s:2:\"OR\";s:8:\"rt_title\";s:23:\"
    #### Verwandte Tags
    \";s:13:\"rt_notagstext\";s:22:\"No related tags found.\";s:10:\"rt_xformat\";s:91:\"%tag_count%[+](\"%tag_link_add%\")[%tag_name%](\"%tag_link%\")\";s:19:\"rt_remove_separator\";s:1:\" \";s:16:\"rt_remove_format\";s:4:\"list\";s:20:\"rt_remove_notagstext\";s:1:\" \";s:17:\"rt_remove_xformat\";s:107:\"» [Entferne %tag_name%](\"%tag_link_remove%\")\";s:15:\"meta_autoheader\";i:1;s:19:\"meta_always_include\";s:0:\"\";s:17:\"meta_keywords_qty\";i:0;s:13:\"use_auto_tags\";i:0;s:6:\"at_all\";i:0;s:8:\"at_empty\";i:0;s:9:\"auto_list\";s:0:\"\";}s:10:\"db_options\";s:10:\"simpletags\";s:14:\"posts_base_url\";s:42:\"http://thafaker.de/wp-admin/edit.php?page=\";s:16:\"options_base_url\";s:53:\"http://thafaker.de/wp-admin/options-general.php?page=\";s:7:\"message\";s:0:\"\";s:6:\"status\";s:0:\"\";s:8:\"all_tags\";b:0;s:7:\"nb_tags\";i:50;s:12:\"wp_filter_id\";i:8;}i:1;s:9:\"uninstall\";}s:31:\"zurueckzensur/zurueckzensur.php\";s:23:\"zurueckzensur_uninstall\";s:49:\"fsthickboxannouncement/fsThickboxAnnouncement.php\";a:2:{i:0;O:22:\"fsThickboxAnnouncement\":2:{s:40:\"\0fsThickboxAnnouncement\0showAnnouncement\";b:0;s:12:\"wp_filter_id\";i:14;}i:1;s:13:\"hookUninstall\";}s:39:\"si-captcha-for-wordpress/si-captcha.php\";s:24:\"si_captcha_unset_options\";s:27:\"wp-pagenavi/wp-pagenavi.php\";s:14:\"__return_false\";s:31:\"debug-queries/debug_queries.php\";a:2:{i:0;s:13:\"Debug_Queries\";i:1;s:10:\"deactivate\";}}' WHERE `option_name` = 'uninstall_plugins'
        Call from: require, require_once, require_once, require_once, include_once, Debug_Queries->debug_queries, register_uninstall_hook, update_option

[**UPDATE**] Bäm, selbst wenn ich ALLE Plugins deaktiviere, so braucht meine Startseite thafaker.de laut Ladezeitencheck (s.o.) noch immer folgende Zeiten:
[![Bildschirmfoto 2011-09-14 um 10.33.25](//picdump.thafaker.de/2011/09/Bildschirmfoto-2011-09-14-um-10.33.25-150x150.png)](http://picdump.thafaker.de/2011/09/Bildschirmfoto-2011-09-14-um-10.33.25.png)

Im normalfall stand ganz oben bei 28.8er Modem 3 Min 4 Sekunden, jetzt sind es noch immer 2,35. Das ist doch kack-scheiße. "Was tun?" sprach Zeus". Mir fällt echt nix mehr ein... außer... meinen Webhoster zu wechseln!
