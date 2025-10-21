---
title: Das Netzwerk-Protokoll Gemini - The Real IndieWeb
slug: das-netzwerkprotokoll-gemini
date_published: 2024-08-08T09:07:12.000Z
date_updated: 2025-07-09T13:34:11.000Z
tags: gemini, gopher, networking, theoldnet, vintage computing
---

Ich beschäftige mich ja sehr gern mit dem Thema [Retrocomputing](__GHOST_URL__/tag/vintage-computing/) und betreibe alte Netzwerke, Server, Computer, Spiele und *DiesDas*. Ich lese gern im *Usenet* via Text-Client (vulg. **SLRN**) und überhaupt - **I like the old net**. Kürzlich bin ich dort über **Gemini** gestolpert. Gemini ist ein Netzwerkprotokoll, das entwickelt wurde, um Inhalte im Internet auf eine Weise bereitzustellen, die zwischen den Komplexitäten des Webs (HTTP/HTTPS) und der Einfachheit von *****Gopher liegt. 

💡

[**UPDATE**] [Hier](https://herrmontag.de/welcome-to-the-smol-web-das-gemini-protokoll/) habe ich einen neuen, sehr ausführlichen Artikel zu Gemini:// und seinen Vorzügen geschrieben. HerrMontag.de

*Gopher ist ein nicht so populäres Netzwerkprotokoll Anfang der 90er Jahre, mit dem man Inhalte via Textdateien in einem speziellen Gopher-Browser zur Verfügung stellen konnte. Es gibt einen Wikipedia-Gopher-Server der auch heute noch die Enzyklopädie via Gopher-Protokoll zur Verfügung stellt. Das sieht dann so aus: ![Screenshot of Gopherpedia - Startseite](__GHOST_URL__/content/images/2024/08/Bildschirmfoto-2024-08-08-um-08.12.10.png)Screenshot of Gopherpedia - Startseite
Am Ende ist Gemini aber eine moderne, verschlüsselte Variante von Textfiles wie sie es bei Gopher schon gab. 

💡

Gemini is a new internet technology supporting an electronic library of interconnected text documents. That's not a new idea, but it's not old fashioned either. It's timeless, and deserves tools which treat it as a first class concept, not a vestigial corner case. Gemini isn't about innovation or disruption, it's about providing some respite for those who feel the internet has been disrupted enough already. We're not out to change the world or destroy other technologies. We are out to build a lightweight online space where documents are just documents, in the interests of every reader's privacy, attention and bandwidth.

### **Gliederung** des Artikels

1. **Grundlagen von Gemini**
1. Vergleich mit Gopher
1. Unterschiede
2. Ähnlichkeiten

2. Anwendung und Nutzung
3. Fazit

2. **Nutzung von Gemini**
1. Gemini Clients
1. Lagrange, Kristall, Amfora, Ariane

2. Erstellen einer Gemini Website
1. Gemtext Dokumente
2. Verzeichnisstruktur

3. Installation eines Gemini-Webserver

Hier sind einige der wichtigsten Merkmale und Prinzipien des Gemini-Protokolls:

## Grundlagen von Gemini

1. **Einfachheit und Minimalismus**: Gemini ist darauf ausgelegt, eine einfache und minimalistische Plattform zu bieten. Es legt Wert auf Text-basierte Inhalte und vermeidet die Komplexitäten und Sicherheitsprobleme des modernen Webs.
2. **Einheitliches Protokoll und Format**: Gemini verwendet ein einheitliches Protokoll und ein einfaches Markup-Format namens "Gemtext". Gemtext ist ähnlich wie Markdown, aber noch einfacher und minimaler.
3. **Sicherheit durch Design**: Alle Gemini-Verbindungen müssen verschlüsselt sein (TLS). Dies soll sicherstellen, dass die Privatsphäre und Sicherheit der Nutzer geschützt wird, ohne die Komplexität von HTTP/HTTPS zu übernehmen.
4. **Keine Scripting-Unterstützung**: Anders als das Web unterstützt Gemini keine Skripte (wie JavaScript). Dies fördert eine sichere und vorhersagbare Benutzererfahrung, ohne die Möglichkeit von Cross-Site Scripting (XSS) und anderen script-basierten Angriffen.
5. **Medientyp**: Der Medientyp *text/gemini* ist zeilenorientiert, was die programmatische Darstellung vereinfacht. Die verwendete vereinfachte Auszeichnungssprache bietet lediglich Konstrukte für Überschriften (drei Ebenen), flache Listenelemente sowie Link-Zeilen; Hervorhebungen einzelner Worte sind nicht vorgesehen. Verlinkungen der Dokumente untereinander spannen mehr oder weniger zusammenhängende Hypertext-Strukturen auf.
6. **Trennung von Inhalt und Darstellung**: Im Geminispace stellt der Server den Inhalt bereit, während der Client die Darstellung des Inhalts übernimmt. Hierdurch haben Verfasser von Inhalten weniger Kontrolle, wie ihre Inhalte bei den Empfängern dargestellt werden; vielmehr entscheiden die Nutzer durch die Wahl und Konfiguration ihres Clients über die gewünschte Darstellung der Dokumente. ([Quelle](https://de.wikipedia.org/wiki/Gemini_(Protokoll)))

### Vergleich mit Gopher

1. **Ähnlichkeiten**:
- Beide Protokolle sind darauf ausgelegt, einfache, textbasierte Inhalte bereitzustellen.
- Beide legen Wert auf Minimalismus und Einfachheit im Design.

2. **Unterschiede**:
- **Sicherheit**: Gemini verlangt zwingend Verschlüsselung (TLS), während Gopher unverschlüsselt arbeitet.
- **Markupsprache**: Gemini verwendet Gemtext, während Gopher keine standardisierte Markupsprache hat und Inhalte meist als reine Textdateien bereitstellt.
- **Moderne Anpassungen**: Gemini ist eine moderne Entwicklung und berücksichtigt aktuelle Anforderungen an Sicherheit und Datenschutz, die in den 1990er Jahren, als Gopher populär war, weniger im Fokus standen.

### Anwendung und Nutzung

Gemini ist ideal für Nutzer und Anbieter, die eine einfache, sichere und minimalistische Plattform suchen, um Inhalte bereitzustellen und zu konsumieren. Es eignet sich besonders für:

- **Persönliche Webseiten und Blogs**: Menschen, die unkompliziert und sicher Inhalte veröffentlichen möchten, ohne sich um die Komplexität des modernen Webdesigns kümmern zu müssen.
- **Dokumentationen und Texte**: Ideal für die Veröffentlichung technischer Dokumentationen oder literarischer Texte.
- **Datenschutzbewusste Nutzer**: Da Gemini alle Verbindungen verschlüsselt, ist es attraktiv für Nutzer, die Wert auf Privatsphäre und Sicherheit legen.

### Fazit

Gemini bietet eine interessante Alternative zum Web und Gopher, indem es eine sichere, einfache und textbasierte Plattform bereitstellt. Es richtet sich an eine Nische von Nutzern, die die Überladung und Komplexität des modernen Webs vermeiden möchten und gleichzeitig Wert auf Sicherheit legen.

Allerdings finde ich wenig Ressourcen und glaube, dass das Thema schon wieder vorbei ist, lange bevor ich es jetzt zufällig gefunden habe.

## Nutzung von Gemini

Um Gemini zu nutzen, benötigen Sie einen Gemini-Client, um Inhalte abzurufen und anzuzeigen, und einen Gemini-Server, um eigene Inhalte bereitzustellen.

### Gemini-Clients

Es gibt verschiedene Gemini-Clients für unterschiedliche Plattformen. Hier sind einige der bekanntesten:

1. **Lagrange (**[**Link**](https://github.com/skyjake/lagrange)**)**: Ein grafischer Gemini-Client für Windows, macOS und Linux. (**Download**[Windows Portable Version](https://github.com/skyjake/lagrange/releases/download/v1.17.6/lagrange_v1.17.6_windows-x64_portable.zip)) (**Download **macOS [arm](https://github.com/skyjake/lagrange/releases/download/v1.17.6/lagrange_v1.17.6_macos11.0-arm64.tbz)/intel)
2. **Kristall**: Ein weiterer grafischer Client für Linux und andere Unix-ähnliche Systeme.
3. **Amfora**: Ein Terminal-basierter Gemini-Client, der auf vielen Plattformen läuft.
4. **Ariane**: Ein Gemini-Client für Android.

Sie können diese Clients in der Regel über die jeweiligen Paketmanager oder Installationsanweisungen der Projekte installieren. Beispielsweise kann Lagrange unter Linux oft über Flatpak installiert werden:

    flatpak install flathub fi.skyjake.Lagrange

Unter macOS kann man mit einem freundlichen *brew install Lagrange* den grafischen Gemini-Browser installieren, das sieht folgendermaßen aus:

![](__GHOST_URL__/content/images/2024/08/Bildschirmfoto-2024-08-08-um-08.33.47-1.png)

![](__GHOST_URL__/content/images/2024/08/Bildschirmfoto-2024-08-08-um-08.33.57-1.png)

![](__GHOST_URL__/content/images/2024/08/thafaker.crabdance.com_gemini.png)

![](__GHOST_URL__/content/images/2024/08/thafaker_gemini.png)

Lagrange Gemini Browser. bbs.geminispace.org und Lagrange Projekt Website

### Erstellen einer Gemini-Website

1. **Gemtext-Dokumente erstellen**: Erstellen Sie einfache Textdateien im Gemtext-Format. Eine Beispielseite könnte so aussehen:

    # Willkommen zu meiner Gemini-Seite!
    
    Dies ist ein einfacher Text auf meiner Gemini-Seite.
    
    ## Ein Untertitel
    
    - Ein Listenpunkt
    - Noch ein Listenpunkt
    
    => gemini://example.com/ein-link Ein Beispiel-Link

Speichern Sie diese Datei als `index.gmi`.

1. **Verzeichnisstruktur**: Ordnen Sie Ihre Dateien in einem Verzeichnis an. Der Hauptindex sollte typischerweise `index.gmi` genannt werden.

### Installieren eines Gemini-Servers

Es gibt mehrere Gemini-Server, aus denen man wählen können. Hier sind einige Beispiele und wie man sie installiert:

💡

**Portfreigabe**
Standardport von Gemini ist: **1965** Dieser muss in der Firewall und im Router, je nachdem wo man den Server betreibt, frei gegeben werden.

##### **Agate**: 

Agate ist ein einfacher Gemini-Server, der in Rust geschrieben wurde. Installation unter Linux (vorausgesetzt, Rust ist installiert):

**Rust installieren**: Falls Rust noch nicht installiert ist:

    curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh
    source $HOME/.cargo/env
    

Dann installieren wir agate:

    cargo install agate

Konfiguration und Start:

Man kann Agate mit folgendem Befehl konfigurieren, wird an den Startcommand angehangen:

    agate --content path/to/content/ \
          --addr [::]:1965 \
          --addr 0.0.0.0:1965 \
          --hostname example.com \
          --lang en-US

Das Zertifikat wird beim ersten Start automatisch generiert.

Starte den Server:

    agate --content path/to/content/ \
          --addr [::]:1965 \
          --addr 0.0.0.0:1965 \
          --hostname example.com \
          --lang en-US

Nun sollte unsere zuvor erstellte **index.gmi** im Verzeichnis unserer Wahl per Gemini-Browser weltweit abrufbar sein. A*ufregend*!

💡

Mein kleiner Gemini-Server kann nun unter der URL g[emini://thafaker.crabdance.com](__GHOST_URL__/das-netzwerkprotokoll-gemini/), meinem Vintage-Server, aufgerufen werden.

💡

Als Vintage-Freund finde ich es sehr spannend, dass es tatsächlich einen [Gemini-Browser für Amiga OS 3](http://thafaker.crabdance.com/howtos/amigemini.html) und 4 gibt, man also auf seinem Amiga 1200 surfen kann.

### Gemini Ressourcen:

- **gemini://warmedal.se/~antenna/** - Geminispace aggregator
- **gemini://flounder.online** ([https version](https://flounder.online/)) - host small Gemini web pages over https and Gemini ([repo (archiviert)](http://web.archive.org/web/20211203125418/https://github.com/alexwennerberg/flounder)).
- **gemini://geminispace.info** - public search provider for Gemini ([repo](https://sr.ht/~rwa/geminispace.info)).
- **gemini://geddit.glv.one** - interactive link service (with comments).
- **gemini://glv.one** - free platform as a service (PaaS) that runs any Gemini server (packaged as a Docker image) in the cloud.
- **gemini://gemini.omarpolo.com/cgi/gempkg/** - interface for the OpenBSD ports collection.
- **gemini://gemplex.space/** - experimental Search Engine for Gemini written in Go
- **gemini://kennedy.gemi.dev/** - public search provider for Gemini
- **gemini://tictactoe.lanterne.chilliet.eu** - Tic Tac Toe game ([repo](https://framagit.org/MCMic/gemini-tictactoe)).
- **gemini://tilde.cafe/~spellbinding/game/cgi?** - make words with specified letters
- **gemini://tilde.cafe/~spellbinding/wordo/cgi?** - a wordle-like game
- **gemini://tilde.cafe/~spellbinding/wall/cgi** - A public wall where you can leave a message
- **gemini://ur.gs/** - translate from en->es and es->en ([repo (archiviert)](http://web.archive.org/web/20211119134326/https://code.ur.gs/lupine/capsule/src/branch/main/src/cgi-bin/translate)).
- **gemini://rawtext.club/~sloum/geminews/** - Daily news feeds proxied to gemini.
- **gemini://rawtext.club/~sloum/cgi/othello/** - Play othello/reversi against a computer opponent over gemini.
- **gemini://rawtext.club/~sloum/cgi/weather** - US weather reports by zip code.
- **gemini://tilde.cafe/~stack/weather** - weather forecast powered by wttr.in
- [gemlog.blue](https://gemlog.blue/) - Gemini hosting from a web frontend.
- **gemini://houston.gmi.bacardi55.io** - A simple tool to check if a capsule is up or not
- **gemini://tlgs.one** - ([http version](https://tlgs.one/)) Another public search provider for Gemini([repo](https://github.com/marty1885/tlgs)).
- **gemini://betahowto.duckdns.org** - Yggdrasil DokuWiki Satellite ([repo](https://github.com/YGGverse/bdoku))
- **gemini://kevachat.duckdns.org** - KevaChat clearnet node for Gemini ([repo](https://github.com/kevachat/geminiapp))
- **gemini://kvazar.duckdns.org** - Observe Kevacoin Universe ([repo](https://github.com/kvazar-network/geminiapp))

### Zusammenfassung

1. **Client installieren**: Wählen und installieren Sie einen Gemini-Client.
2. **Erstellen von Inhalten**: Erstellen Sie Gemtext-Dokumente und organisieren Sie sie in einer Verzeichnisstruktur.
3. **Server installieren und konfigurieren**: Wählen Sie eine Server-Software, installieren und konfigurieren Sie sie, und starten Sie den Server.

💡

Für alle die an dieser Stelle noch viel tiefer in die Materie Gemini Netzwerkprotokoll einsteigen möchten, bezüglich Philosophie und den Änderungen seit dem initialen Start, all denen sei die folgende Seite ans Herz gelegt: [**https://geminiprotocol.net/** (archiviert)](http://web.archive.org/web/20230909091115/https://geminiprotocol.net/) oder natürlich auch via gemini://geminiprotocol.net/ 

## Ressourcen
[

Welcome to the Smol Web - Das Gemini:// Protokoll

Ich bin ja ein großer Freund von offenen Standards, zumindest wenn es um die Grundlagen und Protokolle und das Miteinander geht. Deshalb bin ich ein z.B. Verfechter des Indiewebs mit seinen Möglichkeiten der Vernetzung und habe nun auch diverse Dinge in meinen Websites händisch implementiert, um das zu unterstützen.

![](__GHOST_URL__/content/images/icon/IMG_8150-1.ico)HerrMontag.deJan Montag

![](__GHOST_URL__/content/images/thumbnail/photo-1571842068535-9d7c7c1ddb18)
](https://herrmontag.de/welcome-to-the-smol-web-das-gemini-protokoll/)[

Das Netzwerk-Protokoll Gemini - The Real IndieWeb

Ich beschäftige mich ja sehr gern mit dem Thema Retrocomputing und betreibe alte Netzwerke, Server, Computer, Spiele und DiesDas. Ich lese gern im Usenet via Text-Client (vulg. SLRN) und überhaupt - I like the old net. Kürzlich bin ich dort über Gemini gestolpert. Gemini ist ein Netzwerkprotokoll, das entwickelt wurde,

![](__GHOST_URL__/content/images/icon/logo-3.png)thahipster.deHerr Montag

![](__GHOST_URL__/content/images/thumbnail/photo-1571845615528-6d8d60c459ef)
](__GHOST_URL__/das-netzwerkprotokoll-gemini/)[

gemini - thahipster.de

A Weblog about Vintage Computing, Apple, HowTos, Hardware, Gadgets, Software, Tutorials, Jailbreaking and everything else.

![](__GHOST_URL__/content/images/icon/logo-4.png)thahipster.de

![](__GHOST_URL__/content/images/thumbnail/photo-1495020689067-958852a7765e)
](__GHOST_URL__/tag/gemini/)
Tag Gemini at thahipster.de
