---
title: thafaker.de wechselt von wordpress zu ghost
slug: thafaker-de-von-wordpress-zu-ghost
date_published: 2015-03-30T18:00:48.000Z
date_updated: 2024-01-21T18:53:39.000Z
tags: ghost, migration, wordpress, weblog, export, import, xml, json, minimal, minimalismus
---

Hallo, wir bewegen (besser: migrieren) die Website thafaker.de, welche bisher ausschließlich auf der CMS-Weblog-Software **Wordpress** lief, hin zu **Ghost**. Ghost, kennen Sie? Wenn nicht, schauen sie doch mal [hier (archiviert)](http://web.archive.org/web/20150321074828/https://www.kickstarter.com/projects/johnonolan/ghost-just-a-blogging-platform) oder [hier](https://ghost.org).

Ghost ist ein *neues* Projekt, *krautgefunded* ([Kickstarter (archiviert)](http://web.archive.org/web/20150321074828/https://www.kickstarter.com/projects/johnonolan/ghost-just-a-blogging-platform)) und recht schnell recht erfolgreich geworden, damals mit viel Brimborium, allerdings aktuell auch noch in - *Version 0.5.10* - einem sehr frühen Stadium. Das merkt man z.B., als dass es eine automatische *Sitemap* erst seit kurzem gibt. Oder Benutzer. Oder keine Plugins (Plugins heißen Apps und werden gerade entwickelt). Die Liste ließe sich sicher weiter fortsetzen.

Aber die Frage die man sich hier auch ganz klar stellen muss: brauche ich das wirklich? Bisher habe ich eine sehr große Menge an Plugins benutzt und versuche jetzt absichtlich, den anderen Weg - weg von allem Ballast hin zur schnöden Schnelligkeit - zu gehen.

Und ich finde, das hat sich schon gelohnt: thafaker.de startet wesentlich schneller als bisher. Auch wenn Google Page Speed mir nur einen [Wert von 80](https://developers.google.com/speed/pagespeed/insights/?url=thafaker.de&amp;tab=desktop) (für die Desktop-Variante) erteilt.

Gemäß dem *minimalistischen Grundgedanken* hinter Ghost ist auch der Beitrags-Editor so einfach wie möglich aufgebaut. Im Gegensatz zu anderen bekannten Weblog-Softwares und Content-Management-Systemen besitzt Ghost **keinen** visuellen **WYSIWYG**-Editor, sondern baut stattdessen auf der **Markdown-Sprache** (Wir lieben Markdown, Danke oh [John Gruber](http://daringfireball.net/projects/markdown/syntax)) auf, mit der die Texte formatiert werden können. Auf Formatierungs-Buttons wird dabei ebenfalls bewusst verzichtet, um das Tippen nicht durch das Anklicken von Buttons unterbrechen zu müssen. Wir finden das absolut intuitiv und finden das super, haben so ein eher schlechtes Markdown-Plugin auch schon mit Wordpress benutzt und kennen Markdown nicht zuletzt durch unser beliebtes [Apfelhammer.de Weblog (archiviert)](http://web.archive.org/web/20150305014106/http://apfelhammer.de:80/) sowie [zurueckzumbeton.com (archiviert)](http://web.archive.org/web/20100722083632/http://zurueckzumbeton.com:80/).

[![thafaker.de Artikelthafaker.de Artikel Markdown Ghost](__GHOST_URL__/content/images/2015/03/markdown.png)

Es folgt noch mal ein Blick auf meine alte Website:
![thafaker.de alt Wordpress](__GHOST_URL__/content/images/2015/03/tf_dead.png)

Die Beweggründe zum Wechsel sind also *manigfaltig* und ergeben sich teilweise bereits aus dem oben geschriebenen, deshalb möchte ich hier auch nur ein paar derer aufzählen:

- Lust am Bloggen verloren… (nichts ist so tödlich wie der Alltag.)
- Wordpress ist laaaaannnnngggggsssssaaaaaammmmm - zumindest in meiner Konfiguration.
- meine Installation war soooooo alt, man konnte sie nicht mehr aufräumen und beschleunigen
- Lust auf was neues!
- …

### Export aus Wordpress

Die Schritte um all den Inhalt aus Wordpress heraus zu bekommen, vor allem wenn man eine Datenbank von 2005 bis heute, mit über 4000 Artikeln (3500 öffentlicht) besitzt, war nicht eben leicht. Hier möchte ich sie kurz aufzählen.

- sämtliche Export-Scripte liefen ins leere, zu große Datenbank, timeout.
- Entweder komplett SQL nutzen oder was anderes:
- Dann lieber was anderes:
- In Wordpress einfach Export-XML-Files pro Jahr gebaut, also 2005, 2006… 2015
![](__GHOST_URL__/content/images/2015/03/Bildschirmfoto-2015-03-30-um-21-20-26.png)
- Das ging am Ende gut, obschon da eine Datei schon gern mal 6 MB groß war. Ein Jahr.
- diese Dateien dann mit wp2ghost versucht, in das ghost-json Format umzuwnadeln. Ghost kann keine Wordpress-XML-Files direkt importieren. Nur seine eigenen json Files.
- Das nervt auch ziemlich, geht aber mit `homebrew` ([Link](http://brew.sh)) als Grundlage unterm Mac am Ende recht einfach. Wenn ihr kein Linux oder OSX habt, also *Windows* oder *Amiga OS*, weiß ich leider nicht, was ihr hier tun könnt.
- Eventuell schreibe ich für wp2ghost ein seperates Tutorial.
` $ cd wp2ghost $ npm install $ node bin/wp2ghost.js <your-wordpress-xml> > ghost.json`

*to be continued*

### Import in ghost

Nun will ich die einzelnen Schritte zusammenfassen, die nötig waren, um all den alten Inhalt, nicht nur die Texte sondern vor allem auch die vielen Biler (davon leben Tutorials wie hier auf der Website häufig nunmal), herüber zu retten.

*to be continued*

### weiterführende Ressourcen

- [wp2ghost (archiviert)](http://web.archive.org/web/20170403031254/https://www.npmjs.com/package/wp2ghost)
- ghost.org
- wordpress export function
