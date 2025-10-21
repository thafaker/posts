---
title: Word-Count-Plugin
slug: word-count-plugin
date_published: 2007-06-25T13:35:21.000Z
date_updated: 2018-08-22T09:39:08.000Z
---

Ich habe nun dieses Schicke *Wörter-Zählen-Plugin* eingebaut. Es zählt die Anzahl der Worte in einem Artikel. Für jeden Artikel. Das ist so toll und erleichtert mein Leben doch so ungemein, vor allem wenn es um die Abrechnung von geschriebenen Artikeln geht *scnr*

Erfunden hat dieses Plugin der Murray Williams, und er bietet es [dort (archiviert)](http://web.archive.org/web/20070924105608/http://www.murraywilliams.com/software/word-count-plugin-for-wordpress/) auf seiner Website an. Downloaden, entpacken, uploaden und aktivieren. Dann muss man es natürlich einbauen. PHP Zeuchs. Entweder man lässt es nur im einzelnen Artikel anzeigen, oder auch gleich auf der Hauptseite. Ich habe beides getan, um zu testen wie das geht. Es geht gut.

Der Code zum Einbau lautet wie folgt:`

<?php _e('Word Count','mtw-wordcount'); ?>: < ?php echo mtw_wordcount(); ?>
`

und ist bei mir in der index.php über folgender Zeile eingefügt:
`<?php comments_template(); ?>`

In der single.php für einzelne Artikel steht der Code auch wieder über der Zeile:
`<?php comments_template(); ?>`

Bitte **daran **denken, vor dem Einbau den Code wieder richtig zusammen zu setzen, ich habe zwischen < und ? am Anfang ein Leerzeichen damit es im Weblog angezeigt wird (sonst würde er den PHP-Code ja direkt ausführen), aber das gehört natürlich zusammen, muss also ohne Leerzeichen eingetragen werden.

Links:

- Das tolle Plugin gibt es [hier (archiviert)](http://web.archive.org/web/20070924105608/http://www.murraywilliams.com/software/word-count-plugin-for-wordpress/).
