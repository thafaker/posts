---
title: [UPDATE] Wordpress 3.6 ist da - Es ist ein Oscar
slug: update-wordpress-3-6-ist-da-es-ist-ein-oscar
date_published: 2013-08-04T08:49:07.000Z
date_updated: 2018-08-22T09:38:46.000Z
---

![wordpress-logo_grey-xl](//picdump.thafaker.de/2010/09/wordpress-logo_grey-xl-150x150.png)Da ist man mal ein paar Tage betrunken und frönt der Leichtigleit des Seins, da kommt Freitag klammheimlich Wordpress 3.6 heraus. Neben vielen Neuerungen gibt es auch ein neues Standardtheme, [Twenty-Thirteen](http://core.trac.wordpress.org/ticket/23504).

### Die Highlights:

- Passwörter mit den Zeichen `"` oder `'`[funktionieren jetzt wieder](http://core.trac.wordpress.org/ticket/24367). `\` ist freilich weiterhin verboten.
- Die neue [WP Heartbeat API](http://core.trac.wordpress.org/ticket/23216) erlaubt Entwicklern eine regelmäßige Kommunikation mit dem Server im Hintergrund per AJAX. Die [Post locks](http://core.trac.wordpress.org/ticket/23697) beispielsweise benutzen diese API schon.
- Das [Revisions Easter Egg wurde entfernt](http://core.trac.wordpress.org/ticket/24852).
- Deutsche Umlaute werden jetzt [korrekt umgewandelt](http://core.trac.wordpress.org/ticket/3782).
- Die Einstellungsseite für Navigationsmenüs [wurde überarbeitet](http://core.trac.wordpress.org/ticket/23119).
- Die auf einer inzwischen heimlich eingestellten Google-API beruhende [Rechtschreibprüfung in TinyMCE wurde entfernt](http://core.trac.wordpress.org/ticket/24789).
- Medienelemente können nun leichter eingebunden werden wie auch die Dienste Spotify, Rdio und SoundCloud

### Neues farbenfrohes Theme

#### Einführung Twenty Thirteen

Das neue Standard-Theme legt Fokus auf deinen Inhalt mit einem bunten, einzel-spalten Design gemacht für Rich-Media-Blogging.

Inspiriert von moderner Kunst, Twenty Thirteen Funktionen schrulligen Details, schöner Typografie und fett, kontrastreichen Farben - alles mit einem flexiblen Layout, das sieht auf jedem Gerät gut aus, ob groß oder klein.
![wp36-2013](//picdump.thafaker.de/2013/08/wp36-2013-580x265.png)

### Schreibe mit Vertrauen

#### Entdecke Revisionen

Ab dem ersten Wort, das du schreibst, speichert WordPress jede Veränderung. Jede Revision ist immer an deinen Fingerspitzen. Der Text wird hervorgehoben, dass du dich in Windeseile durch die Revisionen scrollen kannst und siehst, welche Veränderungen du auf dem Weg gemacht hast.

Es ist einfach, zwei Revisionen von einem beliebigen Zeitpunk zu vergleichen und eine Revision wiederherzustellen, um dann zurück zum Schreiben zu gehen. Jetzt kannst du sicher sein, dass kein Fehler dauerhaft ist.

#### Verbesserte automatische Speicherungen

Verliere nie ein Wort, das du geschrieben hast. Automatisches Speichern ist jetzt noch besser; egal ob dein Strom ausfällt, dein Browser abstürzt oder du deine Internet-Verbindung verlierst, dein Inhalt ist sicher.

#### Bessere Beitragsbearbeitungssperre

Dank Live-Updates in der Artikelliste erfährst du, wer zeitgleich an Beiträgen arbeitet. Sollte ein Autor seinen Artikel ungespeichert verlassen, kannst du seine Änderungen übernehmen und damit weiterarbeiten.

### Unterstützung für Audio und Video

#### Neuer Media Player

Teile deine Ton-und Video-Dateien mit dem neuen integrierten HTML5 Media-Player. Lade die Dateien über die Mediathek hoch und füge sie in deine Beiträge ein.

#### Binde Musik von Spotify, Rdio und SoundCloud ein

Binde Songs und Alben von deinem Lieblings-Künstler oder Wiedergabelisten, die du selbst gemischt, hast ein. Es ist so einfach wie das Einfügen einer URL in einem Beitrag auf einer eigenen Zeile.

(Hast du einen anderen Lieblingsdienst? Check alle der [Embeds](http://codex.wordpress.org/Embeds), welche WordPress unterstützt.)

### Unter der Haube

#### Audio/Video API

Die neuen Audio/Video-APIs geben Entwicklern Zugang zu den Medien-Metadaten wie zum Beispiel ID3-Tags.

#### Semantisches Markup

Themes können nun wählen, ob HTML5-Markup in den Kommentarformularen, Suchformularen und Kommentarlisten verwendet werden soll.

#### JavaScript-Werkzeuge

Handliche JavaScript Werkzeuge ermöglichen einfache allgemeine Aufgaben wie Ajax Abfragen, Templating und Backbone View Management.

#### Shortcode Verbesserungen

Durchsuche den Inhalten nach Shortcodes mit `has_shortcode()` und passe diese mit einem neuen Filter an.

#### Revisionen Kontrolle

Detaillierte Revisions-Kontrolle erlaubt dir eine unterschiedliche Anzahl von Revisionen für jeden Beitragstyp zu halten.

#### Externe Bibliotheken

Neue und aktualisierte Bibliotheken: [MediaElement.js](http://mediaelementjs.com/), jQuery 1.10.2, jQuery UI 1.10.3, jQuery Migrate, Backbone 1.0.

 
