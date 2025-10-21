---
title: [Ghost] Was geht mit der Fediverse Integration?
slug: ghost-was-geht-mit-der-fediverse-integration-2
date_published: 2025-05-28T09:57:18.000Z
date_updated: 2025-05-28T12:50:50.000Z
tags: fediverse, ghost, mastodon
---

Die Jungs von Ghost melden sich diese Woche mit einem schrittweisen Update zurück, um die Funktionen des Fediversums weiter zu vervollständigen. 

---

### Bereits veröffentlichte Artikel zum Thema

1. [[Ghost] Was geht mit der Fediverse Integration?](__GHOST_URL__/ghost-was-geht-mit-der-fediverse-integration-2/)
2. [Mitte März'25 News (diese) - Beiträge in ActivityPub jetzt löschbar](__GHOST_URL__/ghost-neue-funktion-beitrage-in-activitypub-jetzt-loschbar/)
3. [Ende Februar'25 News](__GHOST_URL__/was-geht-bei-ghost-und-dem-fediverse-activitypub/)
4. [Mitte Dezember '24 News](__GHOST_URL__/aktueller-stand-ghost-und-das-fediverse-2/)
5. [Anfang November '24 News](__GHOST_URL__/aktueller-stand-ghost-und-das-fediverse/)
6. [Was gibt es neues seitens ActivityPub und Ghost? #3](__GHOST_URL__/was-gibt-es-neues-seitens-activitypub-und-ghost-3/)
7. [Ghost Activity Pub Neuigkeiten #2](__GHOST_URL__/ghost-activity-pub-neuigkeiten-2/)
8. [Ein paar Erklärungen zu Ghost und ActivityPub #1](__GHOST_URL__/ein-paar-erklarungen-zu-ghost-und-activitypub/)

---

Letzte Woche haben sie die domänenbasierte Sperrung als Ergänzung zur Benutzersperrung eingeführt und die Anzeige von ActivityPub-Benachrichtigungen verbessert, damit Unterhaltungen leichter erkannt werden können, wenn Leute auf Beiträge antworten.

Es geht ja darum mit seinem Ghost-Blog am Fediverse wie Mastodon teilzunehmen, Kommentare zu schreiben, seine Blogposts rein zu senden und vor allem aber auch Antworten zu empfangen (das fehlt bei WriteFreely komplett).

### Was gibt es Neues bei ActivityPub?

Nachdem in den letzten zwei Wochen der Arbeit an den Blockierungssteuerungen im Vordergrund stand, wurde gerade ein neuer Moderationsbildschirm in den ActivityPub-Einstellungen eingeführt. Damit ist es möglich Listen von blockierten Benutzern und Domänen an einer Stelle zu verfolgen, zu bearbeiten und zu aktualisieren.
![](https://activitypub.ghost.org/content/images/2025/05/CleanShot-2025-05-19-at-09.57.48@2x.png)![](https://activitypub.ghost.org/content/images/2025/05/CleanShot-2025-05-19-at-09.59.15@2x.png)
Eine weitere schnelle Verbesserung: Wenn man nun jemandem nicht mehr folgt, löschen wir nun automatisch seine bisherigen Beiträge aus allen Feeds. Dies ist ein erwartetes/gewöhnliches Verhalten in den meisten sozialen Apps, aber es ist nicht das Standardverhalten in ActivityPub. Dort bleiben die Daten erhalten.

Jetzt funktioniert es so, wie wir es von Ghost.ActivityPub gewohnt sind.

## Magic Pages ActivityPub beta

Neben unserer offenen Beta von ActivityPub, die auf Ghost(Pro) verfügbar ist, gibt es jetzt eine unabhängige Beta des sozialen Webs, die auf Magic Pages läuft.

Jannis von MagicPages, stets einen Schritt voraus, erkannte bereits, wie man alles zum Laufen bringt, noch bevor wir unsere Dokumentation zur Selbst-Hospitierung fertiggestellt hatten!

Sehr geil den Dienst dadurch zum ersten Mal an mehreren Orten in Betrieb zu sehen.

## Next up: Mentions

Eine offensichtliche Sache, die in der Web-Beta fehlt, ist die Sache @Erwähnungen. Nächste Woche soll das Feature kommen.
