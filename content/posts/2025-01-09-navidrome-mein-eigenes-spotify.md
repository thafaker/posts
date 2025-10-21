---
title: Navidrome - mein eigenes Spotify [UPDATE]
slug: navidrome-mein-eigenes-spotify
date_published: 2025-01-09T13:23:43.000Z
date_updated: 2025-08-28T06:27:03.000Z
tags: mp3, navidrome, Musik-Streaming-Dienst, streaming, anleitung, howto
---

Neulich stolperte ich im *Kabuff* (kleiner, dunkler, meist fensterloser [Neben]raum, Abstellraum) über (m)eine alte 1 TB Festplatte und nachdem ich etwas fand um diese alte "Spindel" in Betrieb zu nehmen, entdeckte ich meine MP3-Sammlung darauf. Stundenlange ripping-Sessions und elendes MP3-Tagging fielen mir wieder ein, Sharing-Nächte mit Freunden und der Blick zu meiner Vinyl-Sammlung. Denn all die Musik die ich liebe, die habe ich mittlerweile auf Schallplatte. Und ich liebe viel Musik. Ca. 400 Schallplatten nenne ich mein Eigen. Aber zurück zur MP3-Sammlung: so viele Erinnerungen stecken da drin. 20 Jahre.

Ich habe diese Dateien wahrscheinlich über 7 Jahre nicht mehr gesehen, was eigentlich schade ist. Was kann ich also tun, um diese zu nutzen, vor allem in Zeiten von *Apple Music,**Spotify *und Co? Wie ist eigentlich die Qualität der Files? Kann man das noch hören? Und überhaupt.

### Eigenes Spotify

Ich höre sehr viel Musik, vor allem auch unterwegs. Ich habe immer Kopfhörer im Ohr. Egal ob beim Sport, Spaziergang oder wenn ich mit dem [Rad unterwegs bin](https://herrmontag.de/tag/rennrad/). Und genau das möchte ich mit meiner "lokalen" Spotify-Sache auch erreichen. Meine Musik zu mir streamen: egal ob auf meine Vintage Stereo Anlage, mein Smartphone oder per Webbrowser. Vor allem kann ich so längst vergessene Musik wieder hören oder gar neues (altes) entdecken, ich liebe das.

## Navidrome MP3 Streaming Music Server

### Meine Navidrome-Erfahrung auf einem ARM-Server

Ich habe Navidrome auf meinem kleinen ARM(HF)-Server, einem Utilite Pro mit Ubuntu 22.04, installiert. Mit einer 1-TB-SSD als Speicherort für meine Musikbibliothek kann ich jetzt unterwegs oder zu Hause jederzeit auf meine Sammlung zugreifen. Dabei nutze ich die exzellente iOS-App [Arpeggi](https://apps.apple.com/app/arpeggi/id1529442328) sowie das intuitive Webinterface von Navidrome.

### Warum Navidrome?

Navidrome bietet viele Vorteile:

- **Plattformunabhängig**: Es funktioniert auf nahezu allen Betriebssystemen.
- **Benutzerfreundlich**: Die Weboberfläche ist modern und leicht zu bedienen.
- **Performance**: Selbst auf ressourcenschwachen Geräten wie meinem ARM-Server läuft Navidrome problemlos.
- **Freie Wahl der Clients**: Neben Arpeggi für iOS gibt es zahlreiche andere Apps ([Symfonium](https://symfonium.app/) für Android) und Tools, die mit Navidrome kompatibel sind.

### Antiquare MP3s im grünen Zeitalter

In einer Welt, in der sich alles ums Streaming dreht, ist es fast nostalgisch, wieder auf die eigene MP3-Sammlung zurückzugreifen. Doch das hat klare Vorteile: Du nutzt bereits vorhandene Ressourcen, ohne auf stromintensive Streaming-Server zurückzugreifen. Damit reduzierst du deinen ökologischen Fußabdruck – ein kleiner Beitrag zur grünen Energiebewegung. Zudem entfällt die Abhängigkeit von kostenpflichtigen Diensten wie Spotify, die ihre Inhalte nach Belieben kuratieren oder entfernen können. Mit Navidrome holst du dir die Kontrolle über deine Musik zurück.

### Herausforderungen auf ARM

Leider boten die offiziellen [vorkompilierten Pakete](https://github.com/navidrome/navidrome/releases/tag/v0.54.3) keine Unterstützung für mein ARM(HF)-Gerät. Daher musste ich selbst aktiv werden und Navidrome aus den Quellen kompilieren. Dieser Prozess war zwar etwas aufwendig, aber schlussendlich erfolgreich. Für Interessierte hier eine kurze Anleitung:

**Ausführbare Datei starten**:

    ./bin/navidrome

**Kompilieren**:

    make build

**Quellen klonen**:

    git clone https://github.com/navidrome/navidrome.git
    cd navidrome

**Abhängigkeiten installieren**:

    sudo apt update && sudo apt install -y golang git make

Nach erfolgreicher Einrichtung war mein Server bereit, meine Musikbibliothek zu streamen.

#### Download

[

navidrome_0.54.3-Snapshot_acce3c97_armHF

navidrome_0.54.3-Snapshot_acce3c97_armHF.zip

22 MB

.a{fill:none;stroke:currentColor;stroke-linecap:round;stroke-linejoin:round;stroke-width:1.5px;}download-circle
](__GHOST_URL__/content/files/2025/01/navidrome_0.54.3-Snapshot_acce3c97_armHF.zip)

### Fazit

Navidrome hat mich nicht nur durch seine Funktionalität, sondern auch durch die Philosophie der Eigenkontrolle über meine Daten überzeugt. Die Kombination aus der leistungsstarken Software und der Arpeggi-App macht es zu einem perfekten Setup für unterwegs oder für das Hören im Browser zu Hause. Die Möglichkeit, meine antiken MP3s sinnvoll einzusetzen und dabei umweltbewusst zu handeln, gibt mir ein gutes Gefühl. Wenn du also nach einer persönlichen, flexiblen Alternative zu kommerziellen Streaming-Diensten suchst, kann ich Navidrome wärmstens empfehlen!

Hast du Navidrome auch ausprobiert? Teile deine Erfahrungen in den Kommentaren!

---

## TerminalDrome

[**UPDATE**] Weil ich einen alten **Powermac G5 Vintage Computer** ([hier](__GHOST_URL__/ultimate-powermac-g5-guide/) ein Artikel dazu) besitze, gern damit herum spiele und es spannend finde, PowerPC 64 Architektur zu fahren, habe ich auf diesem diverse Linux-Distributionen installiert. Da es keinen Navidrome Client gibt, der darauf lauffähig war, habe ich in der Programmiersprache RUST einen Terminal Client programmiert, mit welchem man sich via Shel auf sein Navidrome verbinden und seine Musik hören kann. Das funktioniert natürlich auch auf jedem anderen Linux mit aktuellem Rust.
![TerminalDrome in Shell, connected to Navidrome - 4 Panes](__GHOST_URL__/content/images/2025/08/terminaldrome_cover_here.png)TerminalDrome in Shell, connected to Navidrome - 4 Panes
- [TerminalDrome Github Repo](https://github.com/thafaker/TerminalDrome)
- [TerminalDrome Weblog (archiviert)](http://web.archive.org/web/20250807224226/https://apfelhammer.de/category/terminaldrome/)
- [TerminalDrome Final Version 0.2.2 (archiviert)](http://web.archive.org/web/20250807225812/https://apfelhammer.de/post/new-version-022-of-terminaldrome)

[

New Version 0.2.2 of TerminalDrome

![](__GHOST_URL__/content/images/icon/logo_256x256-3.png)

![](__GHOST_URL__/content/images/thumbnail/herrmontag-4.JPG)
 (archiviert)](http://web.archive.org/web/20250621192957/https://apfelhammer.de/new-version-022-of-terminaldrome.html)
