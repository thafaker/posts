---
title: Ein paar Erklärungen zu Ghost und ActivityPub #1
slug: ein-paar-erklarungen-zu-ghost-und-activitypub
date_published: 2024-05-11T07:40:56.000Z
date_updated: 2025-03-14T21:37:01.000Z
tags: activitypub, ghost, fediverse, newsletter
excerpt: Eine Beschreibung seitens Ghost, warum und wie sie das Web und die Inhalte der Nutzer den Usern wieder zurück geben wollen.
---

Ghost Newsletter #1
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

### Warum ActivityPub? Warum jetzt?

Während wir mit einigen der frühen technischen Arbeiten beginnen, um die Grundlagen für ActivityPub in Ghost zu legen, wollten wir mit einigen Hintergrundinformationen starten für alle, die sich fragen, wie wir hierher gekommen sind.

Wir haben seit 2016 mit Ideen für vernetzte Veröffentlichungen in Ghost gespielt, lange bevor ActivityPub überhaupt existierte.

Damals war Medium in der Online-Veröffentlichung sehr populär aus einigen Gründen: Erstens war es kostenlos. Zweitens bot es eine sofortige soziale Verbreitung an ein eingebautes Publikum. Und drittens sammelten sie eine Menge Geld und zahlten Prominente dafür, es zu nutzen. 😄

Im Gegensatz dazu war die Veröffentlichung mit offenen Plattformen wie Ghost oder WordPress eine relativ einsame Angelegenheit, die darin bestand, Blogposts ins Internet zu stellen und eine Vielzahl an anonymen Seitenaufrufen zu erhalten. Es schien einfach nicht so befriedigend zu sein.

Es war klar, dass Menschen viel mehr Interesse an der Veröffentlichung hatten, wenn sie eine direkte Verbindung zu echten menschlichen Lesern hatten, und so hatten wir zwei große Ideen, um die Veröffentlichung im Web mit einer offenen Plattform sozialer zu gestalten.

Unsere erste Idee war es, es möglich zu machen, dass Publikationen registrierte Mitglieder haben, damit die Menschen speziellen Zugang und Vorteile von den Verlagen erhalten würden — während die Verleger E-Mail-Adressen sammeln und eine direkte Verbindung zu denen hätten, für die sie schreiben.

Unsere zweite Idee war es, einen RSS-Reader in Ghost zu integrieren, der es den Menschen ermöglichen würde, sich gegenseitig im selben Format wie bei Medium und Tumblr zu folgen — aber mit einer API-gesteuerten sozialen Ebene oben drauf. Wir beabsichtigten, es "Pulse" zu nennen, und wir haben sogar einige Prototypen-Demos einigen unserer Top-Verlegern zu der Zeit vorgestellt.

Letztendlich mussten wir uns jedoch als Team von nur etwa ~7 Personen auf eine große Idee konzentrieren:

### Wir konzentrierten uns auf Mitgliedschaften.

In der Zwischenzeit gewann die Idee von Protokollen über Plattformen langsam an Fahrt. ActivityPub wurde 2018 als Webstandard veröffentlicht und bot einen neuen Satz von Funktionen, die über den einseitigen Feed von RSS hinausgingen, mit einem zweiseitigen System für Veröffentlichung und Interaktion. Keine Einbahnstraße, eine Autobahn.

An verschiedenen Punkten haben wir unsere alte Idee für vernetzte Veröffentlichungen in Ghost überprüft und einige Prototypen getestet, aber wir waren uns nie sicher, wie wir es skalieren könnten; noch, wie viele andere Plattformen unsere Idee  letztendlich annehmen würden denn nur so funktioniert so ein Standard: die anderen müssen es auch implementieren. Trotz all seiner Versprechungen schien ActivityPub (wie viele offene Standards) technisch recht klobig und schwer und deshalb am Ende Produkte (Mastodon etc.) zu generieren,  die verwirrend, technisch schwer umzusetzen und vor allem auf Endbenutzerebene nicht easy zu benutzen sind.

### Aber etwas anderes geschah in der Zeit zwischen 2016 und 2024:

Die Menschen wurden zunehmend genervt von dem Verhalten zentralisierter Plattformen und immer wollten einfach Alternativen. Indieweb ist z.B. eine andere Idee davon. Die Motivation, neue Technologien zu erkunden und zu verstehen, raue Kanten inklusive, stieg spürbar an.

2024 fühlt es sich zum ersten Mal so an, als hätten wir eine kritische Masse von Menschen und Plattformen, die daran interessiert sind, das Internet zurückzubesiedeln, um das wiederherzustellen, was wir verloren haben, und etwas Neues zu schaffen. Die Idee also, das Internet wieder zu der zentralen Plattform zu machen, ohne nur in einem Container wie dereinst Facebook, Twitter oder Instagram zu sitzen sondern z.B. auf seiner Website seine Inhalte zu veröffentlichen, dort also die Wurzel zu haben und das dann via Protokoll in die Welt zu schicken. So kann die Inhalte die immer noch mir gehören und nicht Elon Musk, eine andere Person in ihrem Mastodon Client lesen und sogar kommentieren. **Back to the roots. Inhalte zurückerobern. Wieder Herr seiner eigenen Inhalte werden**!
![ActivityPub Demo von Ghost.org](__GHOST_URL__/content/images/2024/05/mail.thahipster.de.png)ActivityPub Demo von Ghost.org
Allein in der vergangenen Woche haben wir Gespräche mit Mastodon, Flipboard, The Verge, Buttondown, WriteFreely und mehreren Mitautoren der ActivityPub-Spezifikation geführt. **Es herrscht das spürbare Gefühl, dass dies möglicherweise das Jahr des Linux-Desktops für das offene Web sein könnte**.

Wir thahipsters finden das großartig und verfolgen die verschiedenen Aktivitäten in diesen Richtung mit großem Interesse. Wir sind schon lange, eigentlich immer, der Meinung, dass wir unsere Inhalte für uns behalten und z.B. auf unserer Homebase zur Verfügung stellen und es von dort den Weg ins Web und zu anderen findet. Ein großer Impact war damals die Erfindung von Track- und Pingbacks seitens der Firma Moveable Type. Viele verschiedene Weblogs interagierten, erwähnten sich, hatten etwas zum Thema beizutragen und wuchsen zusammen. Das ist leider lange tot. **Wir wollen es zurück**!
