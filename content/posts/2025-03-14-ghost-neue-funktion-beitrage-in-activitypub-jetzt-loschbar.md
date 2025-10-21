---
title: "[GHOST] Neue Funktion: Beiträge in ActivityPub jetzt löschbar"
slug: ghost-neue-funktion-beitrage-in-activitypub-jetzt-loschbar
date_published: 2025-03-14T21:35:15.000Z
date_updated: 2025-05-28T09:57:53.000Z
---

Während das Wochenende genossen wurde, gibt es Neuigkeiten zu den aktuellen Entwicklungen in Ghost und ActivityPub.

In der vergangenen Woche wurden erhebliche Leistungsverbesserungen für ActivityPub in Ghost umgesetzt. Dies war das Ergebnis einer umfangreichen Optimierung der zugrunde liegenden Datenbankstruktur für Fediverse-Funktionalitäten. In dieser Woche wurde eine neue Funktion veröffentlicht: Die Möglichkeit, Beiträge zu löschen.

---

### Bereits veröffentlichte Artikel

1. [[Ghost] Was geht mit der Fediverse Integration?](__GHOST_URL__/ghost-was-geht-mit-der-fediverse-integration-2/)
2. [Mitte März'25 News (diese) - Beiträge in ActivityPub jetzt löschbar](__GHOST_URL__/ghost-neue-funktion-beitrage-in-activitypub-jetzt-loschbar/)
3. [Ende Februar'25 News](__GHOST_URL__/was-geht-bei-ghost-und-dem-fediverse-activitypub/)
4. [Mitte Dezember '24 News](__GHOST_URL__/aktueller-stand-ghost-und-das-fediverse-2/)
5. [Anfang November '24 News](__GHOST_URL__/aktueller-stand-ghost-und-das-fediverse/)
6. [Was gibt es neues seitens ActivityPub und Ghost? #3](__GHOST_URL__/was-gibt-es-neues-seitens-activitypub-und-ghost-3/)
7. [Ghost Activity Pub Neuigkeiten #2](__GHOST_URL__/ghost-activity-pub-neuigkeiten-2/)
8. [Ein paar Erklärungen zu Ghost und ActivityPub #1](__GHOST_URL__/ein-paar-erklarungen-zu-ghost-und-activitypub/)

---

### **Neuerungen bei ActivityPub**

Bisher war es mit Ghost möglich, Inhalte in das Fediverse zu veröffentlichen, jedoch waren diese dauerhaft sichtbar. Eine nachträgliche Änderung oder das Löschen eines Beitrags war nicht möglich. Dies wurde nun geändert: Ab sofort können Beiträge über ActivityPub gelöscht werden.

Das Löschen eines Beitrags mag auf den ersten Blick eine grundlegende Funktion sein, doch in verteilten Systemen stellt dies eine größere Herausforderung dar als in zentralisierten Anwendungen.

In einer klassischen Anwendung wird ein Beitrag als Datensatz in einer Datenbank gespeichert und kann durch Löschen dieses Datensatzes entfernt werden. In einem dezentralen Netzwerk stellt sich jedoch die Frage: In welcher Datenbank?

Ein über ActivityPub veröffentlichter Beitrag wird nicht nur in der eigenen Datenbank gespeichert, sondern auch an alle Follower gesendet. Die Server dieser Follower speichern den Beitrag ebenfalls in ihren Datenbanken. Um einen Beitrag zu löschen, muss er daher aus all diesen verteilten Datenbanken entfernt werden – was nicht automatisch geschieht.

0:00

                            /0:13
1×

Im Gegensatz zu herkömmlichen dezentralen Protokollen, bei denen einmal gesendete Inhalte nicht mehr zurückgenommen werden können (wie beispielsweise E-Mails), ermöglicht ActivityPub das Entfernen von Beiträgen. Beim Veröffentlichen eines Beitrags wird eine "Create"-Aktivität gesendet, die die Server der Follower zur Erstellung des Beitrags anweist. Um diesen Beitrag zu löschen, kann nun eine "Delete"-Aktivität gesendet werden, die alle betroffenen Server anweist, den Beitrag zu entfernen.

Zusätzlich muss das System in der Lage sein, eingehende "Delete"-Aktivitäten zu verarbeiten, wenn ein anderer Server die Löschung eines zuvor empfangenen Beitrags anfordert. Ghost unterstützt ab sofort sowohl eingehende als auch ausgehende Löschanfragen, sodass das System nun übergreifend im gesamten Fediverse korrekt funktioniert.

0:00

                            /0:45
1×

Dieses Prinzip – dass sämtliche Vorgänge in ActivityPub als Aktivitäten gesendet und empfangen werden – ermöglicht eine flexible und skalierbare Umsetzung verschiedener Funktionen über zahlreiche Anwendungen hinweg. Es führt zwar zu einer erhöhten Komplexität im Vergleich zu isolierten Systemen, ermöglicht jedoch eine funktionale, dezentrale Netzwerkstruktur mit Tausenden von Anwendungen und Millionen von Nutzern, die unabhängig voneinander agieren.

In der kommenden Woche ist, sofern alles planmäßig verläuft, ein größeres Update zur öffentlichen Beta-Version vorgesehen.
