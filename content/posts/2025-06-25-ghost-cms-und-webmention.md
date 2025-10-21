---
title: Ghost CMS und Webmention
slug: ghost-cms-und-webmention
date_published: 2025-06-25T07:23:34.000Z
date_updated: 2025-07-09T08:33:40.000Z
tags: indieweb, webmention
---

Ich habe in mühevoller Handarbeit einen Weg erarbeitet und die Indieweb [Funktionalität der Webmention](https://janmontag.de/mittwoch-25) nachgerüstet. thahipster.de kann nun Webmention empfangen (anzeigen) und senden (per Python-Script und Systemd). Warum das Indieweb und Webmention eine tolle und auch wichtige Sache sind, die wir für ein zukünftiges freies Internet brauchen, habe Ich auf [herrmontag.de](https://herrmontag.de/webmentions-und-das-indieweb/) beschrieben.

**Ghost** kann von sich aus zwar Webmention empfangen, aber sie verschwinden irgendwo, werden nicht angezeigt noch ausgewertet und es gibt auch keine Möglichkeit, das irgendwie anzuzapfen. Sehr nervig. Gerade, weil es ja die Nachfolge von Trackbacks/Pingbacks (die Älteren unter uns werden sich erinnern) darstellt und für Weblogs per se ein wichtiges Mittel der Wahl zur Kommunikation und Information anderer Websites darstellt. Ich glaube, Ghost hat das nur implementiert um andere Weblogs die ebenfalls mit Ghost laufen zu informieren, wenn diese sich gegenseitig "empfehlen". (**Update**: [Tatsache](https://ghost.org/docs/recommendations/)!) In Ghost ist in den letzten Jahren alles in Richtung **Webpublikation** mit Newsletter und Mitgliederportal gewachsen. 

Das ist cool und [Ghost braucht ein Alleinstellungsmerkmal](__GHOST_URL__/quo-vadis-ghost/) um in einer Welt von Wordpress oder vor allem Medium.com etc. überleben zu können. Aber ich, ich möchte einfach nur bloggen. (Am liebsten in Markdown. So reduziert wie möglich) *Das wars*. Aber in Ghost, das sind Funktionen die ich immer gleich deaktiviere oder ausbaue. Ich benötige auch keine Mitglieder die sich in meinem Weblog registrieren um "Premium-Features" zu erhalten. Ich möchte Artikel über Technik schreiben. Fertig. 

So kommt es auch zustanden, dass Ghost keine Kommentar-Funktion bietet. Diese habe ich mit dem großartigen ISSO-Comments System nachgerüstet. Und nun kam eben die Frage nach Webmention in mir auf. Und wie gesagt, auch da hat Ghost keine Funktionalität.

Also muss man das irgendwie per Hand nachrüsten.

- Zunächst habe ich mein WeblogIch via [Webmention.io](https://webmention.io) (es gibt noch ein paar andere Dienste) registriert um einen Endpoint zu haben. Dann habe ich die Header entsprechend angepasst. Andere CMS haben dafür Plugins, Kirby, Wordpress, Jekyll… you name it. Ghost nicht. 
- Dann habe ich in Javascript direkt im Blog-Theme (Datei post.hbs) die Funktionalität der Anzeige von Webmention nachgerüstet und per CSS gestylt, damit es irgendwie ein bisschen in mein Weblog hinein passt. Das funktioniert nun, aber die Fallstricke waren mannigfaltig. Es folgt ein Screenshot der eine Webmention unter einem ISSO Kommentar anzeigt:

![](__GHOST_URL__/content/images/2025/06/Bildschirmfoto-2025-06-25-um-08.37.55.png)Eine Webmention von JanMontag an mein Weblog
- Dann ging es darum, auch Webmentions senden zu können. Wie könnte man das erledigen? Ein Script könnte sich via API mit meinem Blog verbinden, jeden einzelnen Artikel durchgehen, nach Links prüfen, den Link auf einen Webmention-Endpoint kontrollieren und dann eine Webmention senden. Dann merkt es sich das in einer state Datei damit es beim nächsten Durchlauf des Scripts nur noch neue Artikel einbezieht. Klar ist das nicht perfekt, ändere ich später mal einen alten Artikel und ergänze einen Link, wird der nicht mehr geparsed, aber dafür habe ich noch keine Lösung
- Das funktioniert erst mal einigermaßen gut. Ich stoße aber ständig noch auf Kleinigkeiten. Vorhin brach das Script ab weil ich eine DMG Datei verlinkt hatte die es nicht mehr gab. Exception bauen…

**Woran ich deshalb für mein dickes Weblog hier arbeite:**

1. **Blocklist erstellen**: Fügt problematische Domains wie Adobe-Downloads zur Blocklist hinzu
2. **Timeouts reduzieren**: Setze kürzere Timeouts
3. **Parallelverarbeitung aktivieren**: Nutze ThreadPoolExecutor für schnellere Verarbeitung
4. **In Batches verarbeiten**: Teile sehr sehr viele Blog-Beiträge (hier 4300) in kleinere Gruppen auf:

Prinzipiell funktioniert es erst mal okayish und ich freue mich, dass mein Weblog jetzt mehr kommunizieren kann also nur durch mich und meine Kommentare irgendwo in der Blogosphäre. Und dass ist nicht der einzige bin der das Indieweb und seine Funktionen für maßgeblich und wichtig findet, wenn es um ein freies Web geht, das zeigt z.B. auch Maurice, der ein [Webmention-Plugin](https://github.com/mauricerenck/indieConnector) für Kirby entwickelt und sich mit dem [Web jenseits von Wordpress](https://maurice-renck.de/de/blog/2025/blogsysteme-jenseits-von-wordpress) beschäftigt.

Wenn ich etwas sicherer mit dem Code bin, kann ich das bei Bedarf auch gern zur Verfügung stellen und ein HowTo schreiben.

*Viele Grüße.*
[Link 1](https://janmontag.de/mittwoch-2), 
  [Link 2](https://herrmontag.de/lasst-x-sterben-damit-wir-leben-konnen/).
