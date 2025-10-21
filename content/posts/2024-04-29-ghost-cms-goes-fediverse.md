---
title: Ghost CMS goes Fediverse
slug: ghost-cms-goes-fediverse
date_published: 2024-04-29T06:39:40.000Z
date_updated: 2024-04-29T14:03:35.000Z
tags: ghost, activitypub, mastodon, pleroma
---

Ich habe ja bereits vor sehr langer Zeit ([Link](__GHOST_URL__/social-network-mastodon/)) über **Mastodon** als Alternative zu X-*Twitter* berichtet und mich mit dem **Fediverse**[[1]](#fn1) beschäftigt. Ich finde es schon immer sehr spannend neue Technologien auszuprobieren und war immer auch gern early adopter. Mastodon ist natürlich nur *ein* Teilnehmer des Fedirverse, unter vielen anderen.

**Neulich** betrieb ich dann für ca. ein Jahr eine eigene **Pleroma**-Instanz, Pleroma ([Link](https://pleroma.social)) ist ein leichteres Mastodon, und war so im Microblogging aktiv. Ich finde freie Technologien, das geht bei *OER*[[2]](#fn2) los und hört bei "meine Daten sind mir", Indieweb oder ähnlichem, auf, absolut wichtig. Aber wie dem auch sei, die eigentliche **News** in diesem Artikel ist die Ankündung seitens [Ghost](http://ghost.org), dem *CMS* was ich hier auf thahipster.de verwende, Teil des Fediverse zu werden und es aktiv zu unterstützen. Das heißt, ich kann mit meinem Weblog z.B. auf Mastodon aktiv sein, als ein Client dessen. Ohne große Content-Dienste die meine Daten als ihre Eigenen betrachten. Als Teil des dezentralen großen Netzwerks. *Und das finde ich großartig*.

Genauer geht es um das ActivityPub Protokoll, welches Ghost implementieren wird. Dieses ist ein 2018 veröffentlichtes, offenes, *dezentrales Protokoll* für soziale Netzwerke, das vom W3C verwaltet wird. Es bietet ein Client-zu-Server-API zum Erstellen, Hochladen und Löschen von Inhalten sowie ein Server-zu-Server-API für eine dezentrale Kommunikation.

Dann können Autoren und Autorinnen nicht nur direkt Accounts auf Mastodon, Flipboard, WordPress und anderen Plattformen folgen, auf Ghost veröffentlichte Inhalte können auch von dort abonniert werden. Die Verantwortlichen von Ghost sehen darin die einzige Möglichkeit, im anhaltenden Wettbewerb um die Aufmerksamkeit einer nicht mehr groß wachsenden Zahl von Menschen mithalten zu können. Der Schritt unterstreicht einmal mehr, dass ActivityPub vor allem in den USA immer mehr Aufmerksamkeit bekommt und sich vom Fokus auf die Twitter-Alternative Mastodon lösen könnte.

*Es geht dabei um Freiheit*. Nicht mehr und nicht weniger. Auf einer eigenen Seite zum Projekt ([Link](https://activitypub.ghost.org)) vergleicht Ghost ActivityPub mit der **E-Mail**, dem größten offenen Protokoll des Internets. Genauso wie man darüber mit Menschen kommunizieren kann, ganz egal, bei welchem Anbieter diese ihre E-Mail-Konten haben, ermögliche ActivityPub eine plattformübergreifende Kommunikation. Auch Accounts auf Threads können z.B. inzwischen in mehreren Ländern für das Fediverse geöffnet werden, an einer Brücke zu dem Kurznachrichtendienst Bluesky[[3]](#fn3) wird gearbeitet.

Es gibt derzeit keine wirkliche Alternative. Es gibt noch das **Indieweb** und ich finde die [Idee dahinter](__GHOST_URL__/indieweb-thahipster-de/) sehr gut, allerdings ist die Implementierung nicht ganz einfach und spricht derzeit und eigentlich auch alle Zeit Enthusiasten an, die sich ein eigenes Netzwerk aufbauen. Dabei nehme ich meine eigene Domain, z.B. ein Blog und stelle dort meine Inhalte ein [[4]](#fn4). Diese werden dann z.B. über eine Technik namens Webmentions verteilt, ich beschreibe vorher welche Domains mit gehören und kann so födeieren, kommunizieren und *trackbacken*. Mein Dude *Pftnhr* hat das auf seiner Domain [https://frittiert.es](https://frittiert.es) eingebunden und sicher kann man ihn dazu befragen, per Mail.

---

1. 
Fediverse oder Fediversum bezeichnet ein Netzwerk föderierter, voneinander unabhängiger sozialer Netzwerke, Mikroblogging-Dienste und Webseiten für Online-Publikation oder Daten-Hosting. [↩︎](#fnref1)

2. 
Als Open Educational Resources werden freie Lern- und Lehrmaterialien mit einer offenen Lizenz wie etwa Creative Commons oder GNU General Public License in Anlehnung an den englischen Begriff für Freie Inhalte (open content) bezeichnet. [↩︎](#fnref2)

3. 
Hierüber würde sich der Author sehr freuen. [Dort (archiviert)](http://web.archive.org/web/20240529031630/https://bsky.app/profile/herrmontag.de?ref=herrmontag.de) kann man mir übrigens auf BSKY folgen. [↩︎](#fnref3)

4. 
The IndieWeb is a people-focused alternative to the “corporate web”. It is a community of independent and personal websites connected by open standards and based on the principles of: owning your domain and using it as your primary online identity, publishing on your own site first (optionally elsewhere), and owning your content. [↩︎](#fnref4)

*Matthew Bogart* hat sich ebenfalls Gedanken zum Thema gemacht (eng):
[

My thoughts on how Ghost might join Fediverse

The folks who make Ghost, the wonderful software that runs this site, and my comic site incredibledoom.com recently put up a poll asking how folks would like them to implement one of their most requested features: ActivityPub support. Here’s what I told them.

![](https://www.matthewbogart.net/content/images/size/w256h256/2021/11/Untitled_Artwork.png)Matthew BogartMatthew Bogart

![](https://www.matthewbogart.net/content/images/size/w1200/2024/04/CleanShot-2024-04-16-at-13.03.34@2x.jpg)
](https://www.matthewbogart.net/2024/04/17/ghost-asks-for-input-about-how-to-join-the-fediverse/)
John Nolan von Ghost im Announcement:
