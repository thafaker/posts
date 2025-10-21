---
title: Ghost Activity Pub Neuigkeiten #2
slug: ghost-activity-pub-neuigkeiten-2
date_published: 2024-05-20T16:50:02.000Z
date_updated: 2025-03-14T21:37:12.000Z
tags: ghost, activitypub, newsletter, fediverse
excerpt: In dieser Artikelserie geht es um die Ankündigung und die Begleitung der Entwicklung seitens des Ghost CMS, das ActivityPub Protokoll zu implementieren.
---

Ghost Newsletter #2
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

Wir hatten an [dieser Stelle](__GHOST_URL__/ein-paar-erklarungen-zu-ghost-und-activitypub/) bereits darüber berichtet, dass Ghost, die Grundlage meines CMS auf thahipster.de, sich für das sogenannte **ActivityPub** Protokoll öffnen wird, also Teil des *Fediverse* wird. Heute ist es an der Zeit, weitere Neuigkeiten im Hinblick dieser Entwicklung zu publizieren 😄

### Was ist neu bei ActivityPub?

Die anfängliche Arbeit drehte sich größtenteils um eine Kombination aus der Schaffung technischer Grundlagen, dem Lesen der ActivityPub-Spezifikation, dem Versuch, das Kleinstmögliche zu implementieren.

Nachdem die Ghost-Jungs die anfänglichen Hürden eines einfachen "Posteingangs" und "Postausgangs" sprichwörtlich mit Kaugummi und Klebeband überwunden hatten (und alles in den Arbeitsspeicher schoben), machten sie sich an die Arbeit des allerersten Anwendungsfalls: k**ann ein Ghost-Weblog einem anderen Ghost-Weblog folgen**?

Der Vorteil sich zunächst einmal auf eine grundlegende Ghost <-> Ghost-Verbindung zu konzentrieren besteht laut der Macher darin, dass die Jungs beide Seiten kontrollieren können, sodass sie genau wissen, wie sich beide Akteure verhalten und dadurch einfacher Vorhersagen treffen können, was vor sich geht.

Der Nachteil besteht darin, dass Sie am Ende mit der lokalen Entwicklungsumgebung umgehen müssen, nämlich um ein dezentrales Netzwerkprotokoll auszuführen, das eigentlich nicht dafür konzipiert ist, offline lauffähig zu sein.

Man kann nun einem Ghost-Weblog folgen:
![](__GHOST_URL__/content/images/2024/05/mail.thahipster.de-1.png)
Dann sieht man, wie neue Beiträge im *Posteingang* angezeigt werden ...
![](__GHOST_URL__/content/images/2024/05/mail.thahipster.de-2.png)
Dann kann man so einen Post anklicken "mehr lesen…"
![](__GHOST_URL__/content/images/2024/05/mail.thahipster.de-3.png)
Allerdings warnen die Macher von Ghost davor, hier in Euphorie zu verfallen. Dieser Fortschritt ist nicht besonders groß, auch wenn es so aussieht, es funktioniert noch nichts so wie es sollte.

> Man kann sich das wie die Hülle eines Autos vorstellen, ohne Motor und auch ohne Sitze.

Wie lange die Implementierung letztendlich noch dauern wird, ist offen. Mehr als einen Monat, weniger als ein Jahr sagt Ghost.

Derzeit wird der Posteingang jedes Mal durch einen einzigen Neustart der App vollständig gelöscht. Der nächste Schritt wird die Implementierung einer Datenbank sein, aktuell ist alles im RAM und deshalb flüchtig.

*Es bleibt spannend*.
