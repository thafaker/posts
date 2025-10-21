---
title: Von b2evolution zu Wordpress [Update]
slug: von-b2evolution-zu-wordpress
date_published: 2005-05-08T23:03:05.000Z
date_updated: 2025-09-06T14:55:21.000Z
---

**Ich habe den wunderschönen Schritt vollzogen und mein Weblog-System von [b2evolution](http://b2evolution.net/) auf [WordPress](http://www.wordpress.de/) migriert.**

Das Update lief denkbar einfach und bestand im Wesentlichen aus dem Download der neusten Wordpress Version, dem Uploaden auf den Webserver, dem Starten des Installbefehls und des kurzen Konfigurierens. Fertsch. Ohne Probleme.

Was ich bisher feststellen konnte. [BloGTK (Link nicht mehr verfügbar)](http://www.blogtk.org/) ((Mitlerweile existiert der Link nicht mehr)) funktioniert endlich. Blog-Entry-Poster aus der GNome-Startleiste funktioniert endlich. Umlaute über die XMLRPC und Tools wie BlogJet funktionieren endlich. YEAH! Ich habe Momentan nur eine Kategorie, habe aber gesehen das man mit einer Installation auch mehrere, so wie bei b2evo, haben kann.

**WordPress:** Auf dieser [Seite](http://wordpress.org/download/) wahlweise der Download als *.zip oder *.tar.gz. Dann den Schmus entpacken und auf den Webserver uploaden, bei mir ist das kostenloser Lycos-Webspace mit 50 MB freiem WebSpeicher, einer MySQL Datenbank mit 10 MB und sehr viel Werbung. Dort läuft auch b2evo bisher. Dann einfach das Wordpressverzeichnis per Browser ansurfen und das Teil installiert sich fast von allein. Nur noch schnell die Daten von MySQL usw. angeben —> fertsch. EASY ;-) Ich habs natürlich gleich in die DBase vom b2evo installiert, habe ja nunmal nur eine. *Das läuft…*

**Moving from b2evo to WordPress:** Auch ziemlich easy. Es gibt da ein schönes [php.script (archiviert)](http://web.archive.org/web/20070314234535/http://mitglied.lycos.de:80/jmblogger/files/b2evo2wp.php.txt) welches die Datenbank ausliest und die alten Einträge vom b2evo in WordPress überträgt. *(Es gibt ein altes und ein neues Script, mit dem alten lief es bei mir nicht)* Na auf jedenfall muss man das neue Script einfach ins Wordpressverzeichnis auf dem Webspace uploaden und dann wieder per Browser ansurfen. Er fragt dann nach der alten Datenbank, dem Passwort und dem neuen Kram von Wordpress. Dann kann man noch auswählen was *gerockt* werden soll und er legt los… —> Fertsch **faszinierend** Schon waren alle alten Einträge im neuen Wordpress-Weblog-System, ohne echte Probleme.

Das einzige was mir auffiel:

Die Kommentare werden wohl nicht mit übertragen, kann aber auch sein das ich das nur übersehen habe, wie gesagt ist es erst knapp ‘ne Stunde her das ich mit dieser Migration angefangen habe… Jetzt werde ich mal schauen ob ichs auch auf German laufen lassen kann[*JM/WXP*]

- Hier noch ein [Beitrag (archiviert)](http://web.archive.org/web/20050223013614/http://ppleyard.org.uk:80/tutorials_b2evoimport.php) auf Englisch zum Umzug von b2evo nach WordPress
- Hier eine [Anleitung (archiviert)](http://web.archive.org/web/20050620003407/http://doku.wordpress.de:80/Installation_der_deutschen_Sprachdatei) um Wordpress auf Deutsch laufen zu lassen
- Und [hier (Link nicht mehr verfügbar)](http://files.wordpress.de/index.php?action=download&amp;id=18) gibts dann noch ein komplett überarbeitetes Kubrick-Theme (Standard) damit dann auch wirklich ALLES auf Deutsch ist. Und [hier (Link nicht mehr verfügbar)](http://www.journal.kylaloo.net/2005-02/wp-kubrick-template-in-deutsch) die Website dazu

[**Update**] Es ist wohl doch so das die Kommentare mit übernommen werden, ich habe nur falsch geschaut ;-) Beim upgraden sind aber trotzdem einige Fehler aufgetreten, z.B. wurden einige Sonderzeichen Bzw. Umlaute falsch kodiert. Macht aber nix, wenn mir mal sehr -*wirklich sehr*– langweilig sein sollte werde ich einfach alle 187 Einträge durchgehen und berichtigen **lol**

[*to be continued…*]
