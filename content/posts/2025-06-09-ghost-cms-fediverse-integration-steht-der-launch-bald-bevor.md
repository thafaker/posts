---
title: Ghost CMS + Fediverse Integration - Steht der Launch bald bevor?
slug: ghost-cms-fediverse-integration-steht-der-launch-bald-bevor
date_published: 2025-06-09T10:03:01.000Z
date_updated: 2025-08-08T14:44:49.000Z
tags: mastodon, ghost, fediverse, activitypub
---

**Ghost 6.0 is coming soon**

### Bereits veröffentlichte Artikel (neu oben)

1. [Ghost 6 ist da - Integration vom Fediverse und noch viel mehr](__GHOST_URL__/ghost-6-ist-da-integration-vom-fediverse-und-noch-viel-mehr/)
2. [Ghost CMS + Fediverse Integration - Steht der Launch bald bevor?](__GHOST_URL__/ghost-cms-fediverse-integration-steht-der-launch-bald-bevor/)
3. [[Ghost] Was geht mit der Fediverse Integration?](__GHOST_URL__/ghost-was-geht-mit-der-fediverse-integration-2/)
4. [Mitte März'25 News (diese) - Beiträge in ActivityPub jetzt löschbar](__GHOST_URL__/ghost-neue-funktion-beitrage-in-activitypub-jetzt-loschbar/)
5. [Ende Februar'25 News](__GHOST_URL__/was-geht-bei-ghost-und-dem-fediverse-activitypub/)
6. [Mitte Dezember '24 News](__GHOST_URL__/aktueller-stand-ghost-und-das-fediverse-2/)
7. [Anfang November '24 News](__GHOST_URL__/aktueller-stand-ghost-und-das-fediverse/)
8. [Was gibt es neues seitens ActivityPub und Ghost? #3](__GHOST_URL__/was-gibt-es-neues-seitens-activitypub-und-ghost-3/)
9. [Ghost Activity Pub Neuigkeiten #2](__GHOST_URL__/ghost-activity-pub-neuigkeiten-2/)
10. [Ein paar Erklärungen zu Ghost und ActivityPub #1](__GHOST_URL__/ein-paar-erklarungen-zu-ghost-und-activitypub/)

---

Wieder einmal möchte ich einen kleinen Einblick in die Entwicklung von Ghost CMS hinsichtlich der Integration des Activypub Protokolls geben. Denn Ghost muss sich weiter enwickeln um gegen Platzhirsche wie Medium.com bestehen zu können.

Ich selbst finde die Entwicklungen vom klassisch-cool miniplastischen Markdown-Blogsystem hin zu einer Bezahl/Member/Paidcontent Verwaltungsplattform nicht so geil, nutze ich mein Ghost ja null in dieser Hinsicht: aber jeder muss Geld verdienen. Solange ich das ausschalten oder weg bauen kann, bin ich damit zufrieden, denn eine Alternative habe ich bisher nicht gefunden.

Entschuldigt diesen kurzen Exkurs, es ging um etwas anderes.

Die Entwickler von Ghost bereiten derzeit die Veröffentlichung von Version 6.0 vor. Die vergangenen Wochen waren geprägt von nächtlichen Deployments, zweifelhaften Snack-Entscheidungen und tiefgehenden Diskussionen über die Sinnhaftigkeit von Unit Tests.

Ein bemerkenswerter Fortschritt wurde kürzlich mit der Einführung von **@Mentions** erzielt. Nutzer können nun auf einen Namen klicken, ein Profil aufrufen und die betreffende Person direkt erwähnen – eine kleine Interaktion für den Einzelnen, jedoch mit potenziell hoher Datenbankbelastung für das Gesamtsystem.

### Der Stand bei ActivityPub

Vor etwa einem Jahr begann die Arbeit an der Integration von ActivityPub – zunächst mit einem provisorischen Prototypen und der öffentlich formulierten Ankündigung, Ghost föderieren zu wollen. Was damals als experimenteller Versuch begann, hat sich mittlerweile zu einer umfassenden Integration in das soziale Web entwickelt.

Auf diesem Weg gab es zahlreiche Herausforderungen, insbesondere im Zusammenhang mit Datenbankarchitektur. Hinzu kamen skurrile interne Obsessionen (unter anderem mit Möpsen), konstruktive Zusammenarbeit und konsequente Optimierung – fokussiert auf die einzige Kennzahl, die im Kontext der Social-Funktionalität wirklich zählt: **Kommentare**.

Das Team hinter der ActivityPub-Entwicklung bei Ghost ist im Jahr 2025 von ursprünglich drei auf acht Personen gewachsen. Ziel ist es, diese Funktionalität offiziell mit **Ghost 6.0** innerhalb des kommenden Monats bereitzustellen.

Auch wenn naturgemäß nicht alle geplanten Features bis zur ersten Veröffentlichung vollständig realisiert sein werden, steht fest: **Der Launch muss erfolgen.**

### Mehr als nur ein Feature

Die Einführung von ActivityPub ist für das Projekt weit mehr als eine technische Erweiterung – sie ist ein Bekenntnis zur Relevanz des offenen Webs.

Durch die Föderation von Ghost erhalten Publisher die Möglichkeit, ihre Inhalte auf der eigenen Domain zu veröffentlichen und gleichzeitig ein breites Publikum zu erreichen. Inhalte verbreiten sich über föderierte Netzwerke, ohne die Notwendigkeit der Plattformbindung. Genau dieser Netzwerk-Effekt – ohne Lock-in – entspricht der langfristigen Vision.
![](https://activitypub.ghost.org/content/images/2025/06/image.png)
In einer Zeit, in der zentrale Plattformen zunehmend unter Druck geraten und von wenigen mächtigen Akteuren kontrolliert werden, bietet das 

**Fediverse** einen alternativen Weg. Es ist die Antwort auf die Frage: *Was wäre, wenn niemand dieses Netzwerk besäße?* – dieselbe Frage, die Tim Berners-Lee bereits vor 35 Jahren stellte.

0:00

                            /0:08
1×

Damals ging es darum, Informationen und Dokumente durch Hypertext miteinander zu verbinden. Heute geht es darum, **Menschen** zu verbinden – erneut über spezielle Syntax, diesmal mit **@-Symbolen**.

Ob dieser Ansatz erfolgreich sein wird, bleibt offen. Der entscheidende Faktor liegt bei den Nutzenden.

### Netzwerke leben von Beteiligung

Ein Netzwerk gewinnt an Wert mit der Anzahl aktiver Teilnehmer. Je mehr sich beteiligen, desto größer der Anreiz für weitere, dazuzukommen – ein sich selbst verstärkender Kreislauf, der schwer in Gang zu setzen, aber kaum mehr aufzuhalten ist, sobald er läuft.

Mit dem bevorstehenden Release von **Ghost 6.0** in den nächsten Wochen richtet das Entwicklerteam daher einen klaren Appell an die Community des offenen sozialen Webs: **Mitmachen!**

Die bisher geschaffene Infrastruktur ermöglicht das gegenseitige Folgen, Kommentieren, Antworten auf Notizen, Reposten interessanter Inhalte, das Teilen von Gedanken und das gezielte Erwähnen anderer Personen per @mention.

Die Gelegenheit ist günstig, jetzt eine alternative Webkultur aktiv mitzugestalten. Der größte Fehler wäre es, darauf zu warten, dass andere den Anfang machen.

Denn: Die „Early Adopter“, auf die viele warten – sind genau die Menschen, die diesen Text gerade lesen.
[

Building ActivityPub

Ghost is federating over ActivityPub to become part of the world’s largest publishing network

![](__GHOST_URL__/content/images/icon/ghost-orb-white-squircle-07.png)Building ActivityPub

![](__GHOST_URL__/content/images/thumbnail/appp-1.jpeg)
](https://activitypub.ghost.org)
