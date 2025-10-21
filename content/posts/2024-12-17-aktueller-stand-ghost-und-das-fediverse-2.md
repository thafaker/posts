---
title: Aktueller Stand zu Ghost und dem Fediverse
slug: aktueller-stand-ghost-und-das-fediverse-2
date_published: 2024-12-17T15:04:14.000Z
date_updated: 2025-03-14T21:37:53.000Z
tags: ghost, bluesky, fediverse, activitypub
---

Die Dezember-Meldung seitens Ghost CMS bezüglich der Entwicklung / Integration des ActivityPub Protokolls in Ghost um mit Ghost am Fediverse teilnehmen zu können.

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

### Was ist neu mit dem ActivityPub?

Zunächst haben die Jungs von Ghost letzte Woche in Bezug auf das Design einige Zeit damit verbracht, das Leseerlebnis in der ActivityPub-Client-App zu verbessern und weiterzuentwickeln. Diese Software wurde für lange Inhalte entwickelt, daher möchten sie sicherstellen, dass es sich gut anfühlt, darin Zeit mit Lesen zu verbringen.

Zu diesem Zweck haben sie Lesezeit, Lesefortschritt und einige benutzerdefinierte Anpassungsoptionen für Typografie und Abstand eingeführt – damit die User Ihr Leseerlebnis basierend auf den persönlichen Vorlieben optimieren können, bisschen wie Amazon Kindle Expirience.

Daneben haben sie Fehler behoben, die von Betatestern gemeldet wurden (und davon gab es viele). Sie arbeiten sich langsam aber sicher durch und nehmen jede Woche mehr Leute in die Beta auf. Falls wir uns angemeldet haben, kann es also täglich dazu kommen, dass wir in den Betakreis aufgenommen werden. Ich hoffe es für thahipster.de sehr.

Dann gibt es noch die andere riesige Arbeit, auf die sich alle Ghost Hacker in den letzten Wochen konzentriert haben.

## Databases.

In Bezug auf die kurze Erwähnung von Datenbankarbeiten in der letzten Woche gab es offenbar eine gewisse Vorliebe für Masochismus. Konkret wurde signalisiert, dass das Design von Datenbanken „super spannend“ ist und mehr darüber gewünscht wird.

Offensichtlich herrschen sehr unterschiedliche Auffassungen darüber, was „super spannend“ bedeutet.

Nichtsdestotrotz, da genügend Interesse vorhanden war, folgt hier eine detailliertere Beschreibung, wie die Speicherung von ActivityPub-Daten erfolgt. Aber denkt daran, das habt ihr euch selbst eingebrockt.

Langjährige Leser erinnern sich vielleicht, dass ursprünglich geplant war, die bestehende Ghost-Datenbank für ActivityPub-Daten zu nutzen. Obwohl dafür nur zwei zusätzliche Tabellen erforderlich gewesen wären, wurde dieser Vorschlag schnell vom restlichen Ghost-Produktteam abgelehnt – auf äußerst deutliche Weise.

Geläutert wurde der Ansatz geändert, und ActivityPub wurde als separater Service entwickelt, der außerhalb von Ghost mit einer eigenen Datenbank betrieben wird. So konnten beliebig viele Tabellen erstellt werden – Freiheit!

Für diejenigen, die sich bisher nicht mit den Höhen und Tiefen des Datenbankdesigns für große Anwendungen auseinandergesetzt haben, vorab ein wenig Kontext: Eine Datenbank kann man sich wie eine große Excel-Datei vorstellen, wobei jede Tabelle ein Blatt in dieser Datei darstellt. Daten zu speichern entspricht dabei dem Ausfüllen einer neuen Zeile in dieser Tabelle.

Solange es sich um eine kleine Anwendung mit wenigen Nutzern und etwas Datenvolumen handelt, spielt die Konfiguration der Datenbank keine große Rolle – es funktioniert einfach. Sobald jedoch größere Datenmengen ins Spiel kommen, wird die Organisation der Daten entscheidend, da sie die Performance beeinflusst, was später nur schwer zu korrigieren ist.

Normalerweise wird eine Datenbank so gestaltet, dass sie die eigenen Daten optimal speichert. Man entwickelt eine App, diese verarbeitet Daten und speichert sie anschließend. Dabei ist in der Regel klar, welche Daten gespeichert werden sollen, sodass die Datenbank entsprechend entworfen wird.

ActivityPub stellt hier jedoch eine besondere Herausforderung dar: Die zu speichernden Daten stammen von irgendwo. Vielleicht von Ghost. Vielleicht von Mastodon. Vielleicht von Flipboard, Threads, WordPress oder einem anderen Produkt, das von Personen genutzt wird, denen Nutzer folgen. Alle senden Daten auf leicht unterschiedliche Weise – ein einziges Chaos.

Von Anfang an war klar, dass es viele unbekannte Variablen geben würde. Weder das Aussehen der Daten noch die geplanten Funktionen oder die genaue Arbeitsweise waren wirklich absehbar. Ein klassischer Teufelskreis.

**Angesichts dieser Unsicherheiten wurde entschieden, zunächst auf ein formales Datenbankdesign zu verzichten. Der ActivityPub-Dienst von Ghost verwendet derzeit MySQL hauptsächlich als Key/Value-Store, ohne eine strukturierte Organisation der Daten. Falls das unverständlich klingt: Es ist vergleichbar mit dem blinden Kopieren und Einfügen von Blogbeiträgen in Excel-Tabellen.**

Das Ziel bestand darin, herauszufinden, wie echte (nicht theoretische!) ActivityPub-Daten aussehen, um auf dieser Basis das Datenbankschema sinnvoll zu entwerfen – und dieser Ansatz war erfolgreich! Inzwischen gibt es ein wesentlich besseres Verständnis dafür, welche Daten gespeichert werden müssen und wie dies umgesetzt werden sollte.

**Das führt zum nächsten Problem: Skalierung.**

Beim Aufbau einer neuen App oder eines Startups stellt Skalierung anfangs selten ein Problem dar. Die meisten Apps erreichen niemals Millionen von Nutzer*innen. Es ist daher möglich, zunächst einfache Lösungen zu entwickeln und diese bei Bedarf schrittweise anzupassen. Im Fall von Ghost jedoch gibt es bereits eine große, etablierte Nutzerbasis. Die Überlegung, ActivityPub für alle verfügbar zu machen (also nicht nur in der Beta), bedeutet, dass die Speicherung großer Datenmengen von Anfang an eingeplant werden muss.

Allein auf Ghost(Pro) existieren Zehntausende von Websites mit insgesamt mehreren Millionen Mitgliedern. Einfache Berechnungen zeigen schnell, dass ActivityPub in der Lage sein muss, Milliarden von Datensätzen zu verarbeiten. Und wenn die Anzahl in die Milliarden geht, muss die Datenbank gut durchdacht sein, um Leistungsprobleme zu vermeiden.

**Das führt zu den letzten Wochen:**

Es gibt nun ein klares Bild davon, welche Daten gespeichert werden sollen, eine bessere Vorstellung davon, wie diese genutzt werden, und eine grobe Einschätzung des erforderlichen Umfangs in der Umgebung von Ghost(Pro). Doch wie wird ein gutes Datenbankdesign ermittelt?

*Durch Tests*.

In den letzten Wochen wurde eine Testinfrastruktur eingerichtet, sowohl lokal als auch in einer Staging-Umgebung. In dieser Infrastruktur wird ein neues Datenbankdesign implementiert und mit Milliarden von Datensätzen gefüllt, um die Designentscheidungen bereits jetzt auf die erwartete Skalierung in den ersten 12–24 Monaten nach der allgemeinen Verfügbarkeit von ActivityPub zu überprüfen.

Dieser Prozess ist langsam und mühsam, aber entscheidend. Denn die Entscheidungen, die jetzt getroffen werden, werden langfristig Bestand haben müssen. Deshalb wird zusätzliche Zeit investiert, um sicherzustellen, dass alles richtig geplant ist.

Die gute Nachricht: Die Arbeit verläuft erfolgreich. Die schlechte Nachricht: Sie ist langsam und schwierig.

Es herrscht jedoch Zuversicht, dass eine sorgfältige Planung des Datenbankdesigns jetzt in Zukunft von großem Nutzen sein wird, wenn sowohl Ghost als auch das Fediverse weiter wachsen.

***Es bleibt spannend.***
