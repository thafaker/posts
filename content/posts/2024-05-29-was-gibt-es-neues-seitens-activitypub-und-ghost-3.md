---
title: Was gibt es neues seitens ActivityPub und Ghost? #3
slug: was-gibt-es-neues-seitens-activitypub-und-ghost-3
date_published: 2024-05-29T12:24:03.000Z
date_updated: 2025-03-14T21:37:25.000Z
tags: ghost, activitypub, newsletter, fediverse
excerpt: In dieser Artikelserie geht es um die Ankündigung und die Begleitung der Entwicklung seitens des Ghost CMS, das ActivityPub Protokoll zu implementieren. 
---

Ghost Newsletter #3
In dieser Artikelserie geht es um die Ankündigung und die Begleitung der Entwicklung seitens des Ghost CMS, das ActivityPub Protokoll zu implementieren.

---

### Bereits veröffentlichte Artikel (chronologisch absteigend)

1. [Ein paar Erklärungen zu Ghost und ActivityPub #1](__GHOST_URL__/ein-paar-erklarungen-zu-ghost-und-activitypub/)
2. [Ghost Activity Pub Neuigkeiten #2](__GHOST_URL__/ghost-activity-pub-neuigkeiten-2/)
3. [Was gibt es neues seitens ActivityPub und Ghost? #3](__GHOST_URL__/was-gibt-es-neues-seitens-activitypub-und-ghost-3/)
4. [Anfang November '24 News](__GHOST_URL__/aktueller-stand-ghost-und-das-fediverse/)
5. [Mitte Dezember '24 News](__GHOST_URL__/aktueller-stand-ghost-und-das-fediverse-2/)
6. [Ende Februar'25 News](__GHOST_URL__/was-geht-bei-ghost-und-dem-fediverse-activitypub/)
7. [Mitte März'25 News (aktuellste) - Beiträge in ActivityPub jetzt löschbar](__GHOST_URL__/ghost-neue-funktion-beitrage-in-activitypub-jetzt-loschbar/)

---

Wir hatten an 

[Letzte Woche](__GHOST_URL__/ghost-activity-pub-neuigkeiten-2/) haben die Jungs von Ghost auf dem Weg zur Implentierung des Activitypub Protokolls in ihr Ghost-CMS *Datenbankpersistenz* versprochen. Haben sie das erreicht? Haben sie **nicht**! 

Ohne jeglichen Kontext lauten die offensichtlichen Fragen: „Verfügt Ghost nicht bereits über eine Datenbank?“ und „Warum packst du nicht einfach Sachen hinein?“ – und die Antworten lauten natürlich „Ja“ und „Nun…“,

Als Ghost 2013 zum ersten Mal entwickelt wurde, waren die Datenanforderungen  einfach. Es gab Personen, Beiträge, Tags und Einstellungen. Die gesamte Datenbank hatte etwa 5 Tabellen. Im Laufe des letzten Jahrzehnts wurde die Funktionalität der Plattform jedoch erweitert, um den wachsenden Anforderungen der Benutzer gerecht zu werden. Jetzt gibt es Mitglieder, E-Mails, kostenpflichtige Abonnements, Angebote, Analysen, Verlauf... 

Die Aussage zur Implementierung der Datenbankpersistenz war also zu gewagt.

Aktuell wird diskutiert, wie ActivityPub mit minimalen (eigentlich: null) Auswirkungen auf bestehende Installationen eingebaut und getestet werden kann. Es kann sein, dass am Ende Dinge in einer separaten SQLite-Datenbank ausgelagert werden müssen. Das ist durchaus machbar, aber es ist ein neues Muster und nicht so trivial wie die einfache Wiederverwendung von etwas, das bereits existiert – es wird also etwas länger dauern.

In der Zwischenzeit wurden jedoch auf der Clientseite des ActivityPub-Lesererlebnisses einige Fortschritte erzielt:

Wenn man jetzt auf einen Beitrag klickt, verfügt dieser über alle erforderlichen Stile, um Rich-Media-Einbettungen und -Blöcke zu unterstützen, die im Ghost-Editor verwendet werden können.

Ein Beispiel:

0:08

                            /0:11
1×

Ghost sind ziemlich zufrieden mit den Fortschritten auf der Client-Seite, und wenn erst einmal die Datenpersistenz geklärt ist, wird es einen sehr frühen Beta-Test mit Einbezug der User geben.

**Das wird im nächsten Monat kommen**:

Arbeit am minimalen Funktionsumfang in der Form von: 

- mit Ghost-Sites den Beiträgen anderer folgen, 
- nicht mehr folgen, 
- lesen und liken zu können. 

Sobald dies erfolgt ist, wird Zeit damit verbracht, herauszufinden, wie das mit einer gesunden Architektur skaliert werden kann.

*Es bleibt also spannend.*
