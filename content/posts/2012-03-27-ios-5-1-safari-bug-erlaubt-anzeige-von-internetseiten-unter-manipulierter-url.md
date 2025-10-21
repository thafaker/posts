---
title: [iOS 5.1] Safari-Bug erlaubt Anzeige von Internetseiten unter manipulierter URL
slug: ios-5-1-safari-bug-erlaubt-anzeige-von-internetseiten-unter-manipulierter-url
date_published: 2012-03-27T19:59:55.000Z
date_updated: 2018-08-22T09:38:11.000Z
---

Vorsicht bei der Eingabe von sensiblen Daten in den mobilen Safari-Browser: Über eine Schwachstelle in der Art und Weise, wie Seiten gerendert werden, können andere URLs als die der gerade angezeigten Seite in der Adresszeile angezeigt werden.

*David Vieira-Kurz* von *MajorSecurity* erklärt das Prinzip wie folgt: Der Fehler liegt in der Art, wie Safari mir der JavaScript window.open()-Methode umgeht, die im Browser eine neue Seite öffnet. Dieser Fehler erlaubt es, eine Seite zu öffnen, die mit einer angepassten Adress- und Headerzeile ausgestattet werden kann.

Damit könnte ein Nutzer dazu verleitet werden, Daten in eine eigentlich unsichere oder gar schadhafte Seite einzugeben – zum Beispiel Bank- oder Kreditkartendaten. Nachvollziehen konnte Vieira-Kurz diesen Fehler auf iPhone 4, iPhone 4S, iPad 2 sowie iPad 3, jeweils mit dem aktuellsten iOS 5.1 ausgestattet. Eine Demonstration kann man sich [hier](http://majorsecurity.net/html5/ios51-demo.html) (mit einem iOS-Gerät) anschauen.

([via](http://www.iphonenotes.de/2012/03/23/ios-5-1-safari-bug-erlaubt-anzeige-von-internetseiten-unter-manipulierter-url/?utm_source=feedburner&amp;utm_medium=feed&amp;utm_campaign=Feed%3A+Iphone-notesde+%28iPhone-notes.de%29))
