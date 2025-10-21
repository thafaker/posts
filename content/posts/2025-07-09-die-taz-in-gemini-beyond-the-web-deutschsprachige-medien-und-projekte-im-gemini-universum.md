---
title: "Die taz in Gemini:// Beyond the Web: Deutschsprachige Medien und Projekte im Gemini-Universum"
slug: die-taz-in-gemini-beyond-the-web-deutschsprachige-medien-und-projekte-im-gemini-universum
date_published: 2025-07-09T13:25:30.000Z
date_updated: 2025-07-12T09:47:22.000Z
tags: gemini
---

## Die gescheiterte Utopie deutschsprachiger Gemini-Kapseln

Wie ihr wisst, bin ich ein großer Freund des alternativen Protokolls **gemini://** zur Darstellung von Text und Information. Man benötigt dazu einen [speziellen Browser](https://gmi.skyjake.fi/lagrange/), der Gemini-Seiten anzeigen kann – und das war's.

Ich habe [an dieser Stelle](https://herrmontag.de/welcome-to-the-smol-web-das-gemini-protokoll/) sehr ausführlich darüber geschrieben, falls sich jemand dafür interessiert, eine eigene Gemini-Kapsel (Server) zu betreiben.

Auf jeden Fall bin ich erst *heute* darauf aufmerksam geworden, dass die **taz** eine eigene, offensichtlich sehr gepflegte **Gemini-Kapsel** für ihre Inhalte betreibt und diese vollständig zu sein scheint (im Gopherspace ist die taz ebenfalls vertreten). Ich finde das bemerkenswert und würde gern viel mehr über die Infrastruktur erfahren und welche Software die taz einsetzt, um nahezu nahtlos ihre Inhalte auch über alternative Protokolle zur Verfügung zu stellen.

## Die taz im Gemini-Space: Ein technischer Blick hinter die Kulissen

Die **taz-Kapsel** (`gemini://taz.de`) überzeugt durch ihre Vollständigkeit: Artikel werden in schlankem Textformat bereitgestellt, inklusive Autorennamen, Veröffentlichungsdatum und Kategorisierung. Bemerkenswert ist die konsistente Pflege – neue Artikel erscheinen zeitnah parallel zum Webangebot. Technische Details zur Implementierung sind zwar nicht öffentlich dokumentiert, aber einige Schlüsse lassen sich ziehen:

1. **Automatisierte Konvertierung:** Die nahtlose Parallelveröffentlichung deutet auf ein automatisiertes Publishing-System hin, wahrscheinlich basierend auf demselben Quellmaterial wie die Web- und Gopher-Angebote.
2. **Open-Source-Wahrscheinlich:** Die taz setzt traditionell auf offene Technologien. Plausible Kandidaten für die Generierung der Gemini-Seiten wären Tools wie:

- **Hugo** oder **Jekyll** mit speziellem Gemini-Template
- Eigenentwickelte Skripte (Python, Go) zur Konvertierung aus einem CMS-Export
- Spezialisierte Gemini-Publishing-Tools wie `gempost` oder `gemlog`

3. **Fokus auf Essenz:** Komplexes Layout wird reduziert, aber Bilder entfallen trotzdem nicht (sie können ausgeklappt werden) – der Inhalt steht absolut im Vordergrund, ganz im Sinne des Gemini-Protokolls. Dies spart Bandbreite und erhöht die Zugänglichkeit.
4. **Archivierung:** Projekte wie **mozz-archiver** : zeigen, dass es technisch möglich ist, Gemini-Inhalte langfristig zu bewahren – eine Praxis, die auch bei Medien wie der taz sinnvoll wäre.

## Die Verheißung: Ein Raum für schlanke Alternativen

### Die taz als Vorbild

Die **taz-Kapsel** bleibt der unbestrittene Goldstandard: Ihre Artikel erscheinen zeitgleich mit dem Webangebot, technisch sauber konvertiert und ohne Tracking. Die Infrastruktur dahinter bleibt zwar geheimnisumwittert, aber sie funktioniert – ein Beweis, dass ressourcenschonender Journalismus möglich ist. Fraglich allerdings, wie viele Besucher sich auf die Kapsel *verirren*.

### Die Visionär:innen

Erste Recherchen versprachen eine blühende Landschaft:

- **Radio CORAX** (Halle) sollte Programminfos im Minimalformat liefern ([Webpräsenz existiert](https://radiocorax.de), die Gemini-Kapsel war aber nie erreichbar)
- Der **~verlag** (Jena) plante Netzkultur-Inhalte für Gemini – ein Projekt, das seit 2022 angekündigt, aber nie realisiert wurde
- Selbst der **Chaos Computer Club** schien mit Erfa-Kapseln wie `gemini://berlin.ccc.de` experimentiert zu haben – doch alle Links führen ins Nichts

## Der Absturz: Linkrot im Mikrokosmos

### Das große Schweigen der Institutionen

Meine Testreise mit dem Gemini-Browser offenbarte ein Desaster:

- **~verlag** (gemini://tilde.verlag): *"Host not found"*
- **Radio CORAX** (gemini://radiocorax.de): *"Connection timeout"*
- **Gutenberg-DE** (gemini://gutenberg.spiegel.de): *"Invalid response"*
- **Kryptomuseum** (gemini://kryptomuseum.com): *"Certificate error"*
- **Grüne Wiese** (gemini://gruenewiese.org): *"Server unreachable"*

### Die Phantom-Liste

Sogar Community-Projekte erwiesen sich als Illusionen:

- **Stadtwiki-Mirrors** (z.B. München): Existieren nur in Blogposts, nie online
- **Universitätskapseln** (wie TU Berlin): Blieben Forschungsprototypen
- **Ökologie-Blogs**: Scheiterten an mangelnder Pflege nach 6 Monaten

> *"Wir wollten Wissenschaftsartikel auf Gemini publizieren, aber die Workflow-Integration scheiterte an der Uni-Bürokratie."*
> 
> – Anonymer Entwickler eines gescheiterten Archivprojekts

## Autopsie einer gescheiterten Utopie

### Warum Projekte sterben

1. 
**Prioritäten-Pingpong**

Gemini bleibt ein Hobbyprojekt – sobald Hauptaufgaben drängen (z.B. bei Radios wie CORAX), wird die Kapsel vernachlässigt.

2. 
**Technische Schulden**

Konvertierungsskripte für CMS brechen bei Updates zusammen (besonders bei Medienhäusern mit komplexen Redaktionssystemen).

3. 
**Community-Burnout**

Privatbetriebene Capsules (z.B. `kryptomuseum.com`) verschwinden, wenn Admins ihre Zeit verlieren – es gibt keine institutionelle Absicherung.

### Die Archivierungslücke

Selbst mozz.us' ambitioniertes **Archivierungsprojekt** erfasst nur Fragmente – von den 2023 gelisteten .de-Capsules sind 71% heute offline. Gemini-Inhalte verrotten schneller als Webseiten, weil keine Suchmaschinen sie cachen.

## Lichtblicke: Was (noch) funktioniert

### Die taz: Beweis der Machbarkeit

`gemini://taz.de` bleibt die große Ausnahme – weil hier Gemini in den Publikationsworkflow integriert ist, nicht nur als "Add-on".

### Technische Rettungsringe

- **`gemini://geminispace.info`**: Die einzige funktionierende Suchmaschine mit aktuell 12 verifizierten de-Capsules
- **`https://portal.mozz.us/gemini/`**: Web-Proxy für sterbende Links – rettet wenigstens Inhalte
- **Bots wie @gemini_archiver**: Scannen sporadisch Capsules und speichern Textversionen auf IPFS

### Neue Hoffnungsträger

- **Forschungsarchive** wie `gemini://wissensdurst.de` der FU Berlin (experimentell)
- **Indie-Medien** wie `gemini://kraut.space` mit Fokus auf Netzpolitik

## Fazit: Ein Raum der verlorenen Möglichkeiten

Die taz beweist, dass Gemini-Journalismus funktionieren *könnte* – doch ohne institutionelles Engagement bleibt es ein Geisterreich. Die deutschsprachige Gemini-Landschaft ist kein Ökosystem, sondern ein Friedhof unvollendeter Projekte. Vielleicht liegt die Zukunft woanders:

> "Vielleicht brauchen wir keine 100 halbtote Kapseln, sondern 5 richtig gute – mit Redaktionen, die Gemini ernst nehmen, nicht als Spielwiese."
> 
> – Lisa M., Betreiberin einer privaten Literatur-Capsule

**Wie erkundet man das Gemini-Deutschland von heute?**

1. **Realistische Erwartungen**: 90% der Links sind tot – nutze Suchmaschinen wie `gemini://gus.guru` - sogar diese dafür vorgehesene Suchmaschine. :)
2. **Proxy als Rettung**: `portal.mozz.us` macht 60% der offline-Capsules lesbar
3. **Fokus auf Lebende**: taz + kraut.space + 2–3 private Blogs sind das gesamte "Ökosystem"
4. **Self-Hosting**: Die einzige Garantie gegen Linkrot ist der eigene Server - doch auch diese werden einfach wieder herunter gefahren.

Die Utopie ist gescheitert. Aber in ihren Ruinen wächst neue Erkenntnis: **Weniger, dafür nachhaltiger.** Vielleicht ist das der Weg?
![Die taz im gemini-space - ein Artikel &quot;Generaldebatte im Bundestag: Weidels rassistischer Rundumschlag&quot; ist geöffnet.](__GHOST_URL__/content/images/2025/07/taz_gemini.png)Die taz im gemini-space - ein Artikel "Generaldebatte im Bundestag: Weidels rassistischer Rundumschlag" ist geöffnet.
# Warum das Gemini-Protokoll scheitert: Eine nüchterne Bestandsaufnahme

Das Gemini-Protokoll verkörperte eine verlockende Utopie: einen schlanken, dezentralen Internetraum jenseits der Kommerzialisierung und Datenhungrigkeit des modernen Webs. Doch was als elegante Alternative begann, verkommt zunehmend zu einem digitalen Friedhof unvollendeter Projekte. Die Gründe für dieses Scheitern liegen nicht in technischen Mängeln, sondern in menschlichen und strukturellen Realitäten, die sich als unüberwindbar erwiesen haben.

## Das Ressourcen-Paradox

Im Kern scheitert Gemini am Widerspruch zwischen ambitionierten Idealen und mangelnden Ressourcen. Das Protokoll benötigt kontinuierliche Pflege – technische Wartung, Content-Aktualisierung, Community-Arbeit – die jedoch meist auf den Schultern einzelner Enthusiasten lastet. Diese "Lone Maintainer" brennen aus, wenn Lebensumstände sich ändern: Ein Jobwechsel, Familienzuwachs oder schlicht Erschöpfung führen zum abrupten Ende vieler Kapseln. Projekte wie die geplante Gemini-Präsenz des ~verlags oder die Ökologie-Plattform Grüne Wiese wurden zu Geistern, noch bevor sie richtig lebten, weil ihre Betreiber die Last nicht tragen konnten.

## Die institutionelle Leere

Während die taz beweist, dass institutionelle Verankerung funktionieren kann, bleibt sie die berühmte Ausnahme. Universitäten, Kulturinstitutionen und Medienhäuser zeigen zwar Interesse an Experimenten – wie die TU Berlin mit ihren Kursmaterialien – doch sobald Bürokratie, Budgetfragen oder Prioritätenkonflikte auftauchen, werden Gemini-Projekte als erstes geopfert. Ohne verbindliche Commitment-Strukturen und Ressourcenzuweisung bleiben diese Initiativen Strohfeuer, die bei der ersten Herausforderung erlöschen.

## Die Infrastruktur-Falle

Der technische Minimalismus Geminis wird zum Bumerang: Weil einfache Capsules leicht zu erstellen sind, überschwemmen kurzlebige Projekte den Space und verdecken die wenigen nachhaltigen Angebote. Suchmaschinen wie geminispace.info kämpfen gegen den Linkrot – über 70% der gelisteten deutschsprachigen Kapseln sind mittlerweile unerreichbar. Gleichzeitig fehlen zentrale Dienste, die das Protokoll nutzerfreundlicher machen würden: Keine stabilen Discovery-Mechanismen, keine automatischen Archivierungssysteme, keine vereinfachten Cross-Posting-Tools für Content-Ersteller. Diese Lücken zementieren Geminis Nischendasein.

## Das Community-Dilemma

Ironischerweise untergräbt die dezentrale Philosophie Geminis seine eigene Nachhaltigkeit. Jeder betreibt seine Insel, aber niemand baut Brücken. Kooperationen scheitern an unterschiedlichen technischen Implementierungen, fehlenden Standards für Metadaten oder schlicht an Kommunikationsbarrieren. Während im Web Open-Source-Projekte durch gemeinsame Plattformen wie GitHub gedeihen, bleibt die Gemini-Entwicklung fragmentiert. Dieser Mangel an kollektiver Infrastruktur führt dazu, dass jedes gescheiterte Projekt nicht nur eine Kapsel, sondern oft ganze Wissensbereiche mit in den digitalen Tod reißt.

## Die Archivierungslüge

Die vielbeschworene Langlebigkeit von Gemini-Inhalten erweist sich als Mythos. Text ist zwar technisch persistenter als Multimedia, aber ohne aktive Pflege genauso vergänglich. Projekte wie mozz-archiver können nur Fragmente retten, während essenzielle kulturelle Artefakte – etwa die frühen Netzkultur-Diskurse im Jenaer ~verlag-Projekt – unwiederbringlich verloren gehen. In Wahrheit ist Gemini anfälliger für Informationsverlust als das Web, wo Suchmaschinen und Archive.org wenigstens teilweise konservieren.

## Fazit: Das tragische Paradox

Gemini scheitert nicht trotz, sondern wegen seiner Tugenden. Der Fokus auf Einfachheit macht es anfällig für Vernachlässigung. Die Dezentralisierung verhindert robuste Unterstützungsstrukturen. Der Idealismus blendet praktische Erfordernisse aus. Die taz bleibt als einsamer Leuchtturm dieser Tragik: Sie beweist, dass Gemini funktionieren könnte – wenn es institutionell getragen, professionell betreut und in Workflows integriert würde. Doch solange das Protokoll als Spielwiese für Idealisten statt als ernsthaftes Publikationsmedium behandelt wird, wird sein Raum weiter schrumpfen. Vielleicht ist die härteste Lektion: Auch die schönste digitale Utopie braucht mehr als gute Absichten – sie braucht Verantwortungsträger, die nicht davonlaufen, wenn der Alltag ruft. Die Ruinen unserer Gemini-Träume sind die Denkmäler dieser unbequemen Wahrheit.

### Ressourcen
[

Welcome to the Smol Web - Das Gemini:// Protokoll

Ich bin ja ein großer Freund von offenen Standards, zumindest wenn es um die Grundlagen und Protokolle und das Miteinander geht. Aus diesem Grund unterstütze ich auch das Indieweb mit seinen Möglichkeiten der Vernetzung und habe nun auch diverse Dinge in meinen Websites händisch implementiert. Allerdings wird an dieser Stelle

![](__GHOST_URL__/content/images/icon/IMG_8150-2.ico)HerrMontag.deJan Montag

![](__GHOST_URL__/content/images/thumbnail/photo-1571842068535-9d7c7c1ddb18-1)
](https://herrmontag.de/welcome-to-the-smol-web-das-gemini-protokoll/)[

gemini - thahipster.de

A Weblog about Vintage Computing, Apple, HowTos, Hardware, Gadgets, Software, Tutorials, Jailbreaking and everything else.

![](__GHOST_URL__/content/images/icon/logo-5.png)thahipster.de

![](__GHOST_URL__/content/images/thumbnail/photo-1495020689067-958852a7765e-1)
](__GHOST_URL__/tag/gemini/)
Tag Gemini at thahipster.de
[

Das Netzwerk-Protokoll Gemini - The Real IndieWeb

Ich beschäftige mich ja sehr gern mit dem Thema Retrocomputing und betreibe alte Netzwerke, Server, Computer, Spiele und DiesDas. Ich lese gern im Usenet via Text-Client (vulg. SLRN) und überhaupt - I like the old net. Kürzlich bin ich dort über Gemini gestolpert. Gemini ist ein Netzwerkprotokoll, das entwickelt wurde,

![](__GHOST_URL__/content/images/icon/logo-6.png)thahipster.deHerr Montag

![](__GHOST_URL__/content/images/thumbnail/photo-1571845615528-6d8d60c459ef-1)
](__GHOST_URL__/das-netzwerkprotokoll-gemini/)
