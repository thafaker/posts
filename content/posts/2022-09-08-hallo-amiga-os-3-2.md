---
title: Hallo AMIGA OS 3.2
slug: hallo-amiga-os-3-2
date_published: 2022-09-08T11:38:54.000Z
date_updated: 2024-05-11T06:28:36.000Z
tags: retro computing, amiga os 3.2, update, kickrom 3.2, disketten, retro gaming, amiga 1200, vintage computing
---

Wie viele Computer aus dem Jahre 1993 existieren wohl noch, für welche nach wie vor Betriebssystemupdates und Aktualisierungen, gar neue Hard- und Software entwickelt und veröffentlich werden? Genau, *fast* keine.
![Amiga 1200 mit Sicht auf den Nummernblock und die LEDs](__GHOST_URL__/content/images/2022/09/6A8B1824-5D39-4A5C-A6EE-A0106279BE3F.JPG)Amiga 1200 mit Sicht auf den Nummernblock und die LEDs
Bis auf die verrückte Amiga Gemeinde. Der deutsche Hersteller *iComp* (Individual Computers) beispielsweise produziert nach wie vor hochwertige und nagelneue Turbokarten, mit besseren Prozessoren und mehr RAM für Amiga 500, 600 und 1200 und andere hochwertige Erweiterungen - bis hin zu einem DVI/HDMI-Ausgang (eine Art Flickerfixer, Scandoubler) um den Amiga an einem aktuellen Display nutzen zu können - nativ. *Hyperion* indes besitzt nun die Rechte an Amiga OS und entwickelt dieses anhand der Ursprungsversion weiter, Mitte 2021 kam das Update **Amiga OS 3.2** heraus. Es folgt auf AMIGA OS 3.1, welches im Jahr 1994 durch die AMIGA Nachfolgefirma ESCOM entwickelt wurde und das bis dato letzte offizielle AMIGA Betriebssystem darstellte.

AMIGA OS basiert auf zwei Stufen. Man hat den Kern des Systems in sogenannten Kickrom Bausteinen (zwei beim Amiga 1200, Hi und Lo, bei anderen Amigas ist es manchmal auch nur ein Baustein) fest auf dem Board, sie enthalten die grundlegenden Routinen zur Arbeit, ein bisschen wie ein stark erweitertes BIOS in x86 Computern - und als zweite Stufe kommt die sogenannte Workbench auf Softwareebene, das eigentliche präemptive Multitasking Betriebssystem mit grafischer Oberfläche. Von beidem gibt es nun also seit letztem Jahr ein Update und ich habe mir das für meinen AMIGA 1200 besorgt. Ein aktuelles Betriebssystem-Update für die alte Kiste, es ist unfassbar.
![AMIGA OS 3.2 Kickrom und INSTALL Diskette auf Amiga 1200](__GHOST_URL__/content/images/2022/09/IMG_7280-1.jpg)AMIGA OS 3.2 Kickrom und INSTALL Diskette auf Amiga 1200
Folgendermaßen sehen die beiden Kickrom-Bausteine aus. Wichtig ist:

- Der Sockel im AMIGA 1200 ist länger als das Kickrom selbst. Freibleibende Pins sind nach links, zum PCMCIA hin. Also rechts ansetzen.
- Der LOW, U6B wird "davor sitzend gesehen" *oben* eingesetzt
- Der HI, U6A wird "davor sitzend gesehen" *unten* eingesetzt

![](__GHOST_URL__/content/images/2022/09/IMG_7283.jpg)
Eingebaut sieht das in einem AMIGA 1200 folgendermaßen aus:
![AMIGA 1200 Kickrom Hi und Low AMIGA OS 3.2, Perspektive davor sitzend](__GHOST_URL__/content/images/2022/09/amiga1200_kickrom_hi_low_os32.jpg)AMIGA 1200 Kickrom Hi und Low AMIGA OS 3.2, Perspektive davor sitzend
Er funktioniert. Der Amiga läuft, der Austausch der physikalischen Kickroms war erfolgreich und das neue Betriebssystem läuft. 
![Amiga 1200 mit Kickrom 3.2 und Workbench 3.2](__GHOST_URL__/content/images/2022/09/IMG_7289.jpg)Amiga 1200 mit Kickrom 3.2 und Workbench 3.2
Meine Workbench hat nun bereits Version 47.3 denn Hyperion hat bereits ein Update 3.2.1 zu Amiga OS 3.2 veröffentlicht. Es steht allen Besitzern kostenlos zum Download auf den Seiten von [Hyperion](https://www.hyperion-entertainment.com/index.php/downloads?view=files&amp;parent=42) zur Verfügung.

*Es bleibt spannend.*

## Ressourcen

- [AMIGA OS 3.2 kaufen](https://www.amiga-shop.net/Amiga-Software/AmigaOS-Amiga-Betriebssysteme:::29_68.html) (kein Affiliate!)
- [AMIGA OS 3.2.1 Update downloaden](https://www.hyperion-entertainment.com/index.php/downloads?view=files&amp;parent=42)

---

# Background Infos und Neuerungen von Amiga OS 3.2

Das AmigaOS 3.2 ist die neueste Version des Amiga-Betriebssystems für den klassichen Amiga Computer mit 68k-Prozessor.

Es ist für Amiga 1000, 500, 600, 1200, 2000, 3000, 3000T, 4000, 4000T, CD32 und CDTV auf CD-Rom verfügbar. **Physikalische Kickstart-ROMs sowie die Install Diskette oder auch eine vorkonfigurierte CF-Karte sind optional.**

AmigaOS 3.2 kommt vollgepackt mit weit über 100 neuen Funktionen, dutzenden von Updates und Bugfixes, die fast alle AmigaOS-Komponenten abdecken. AmigaOS 3.2 ist das Ergebnis von mehr als 2 Jahren intensiver und unermüdlicher Arbeit eines Teams von über 60 Personen, um einen neuen Meilenstein in der AmigaOS-Geschichte zu setzen.

Die CD-Rom der AmigaOS 3.2 enthält alle Disketten und AmigaOS-Kickstart-ROMs für alle jemals produzierten Amiga-Maschinen. So kann der Amiga-Benutzer AmigaOS 3.2 auf viele verschiedenen Amigas gleichzeitig installieren, ohne weitere Lizenzen erwerben zu müssen.

**Systemvoraussetzungen**

- Amiga Computer oder Emulationsumgebung (wie WINUA, EUAE)
- Mindestens Kickstart 3.1 / oder höher (3.1.4). Kickstart ROM 3.2 (empfohlen, da geringste Bootzeit und geringster Speicherverbrauch)
- 2 MB Gesamtspeicher (Chip-Ram + Fast-Ram). Sollten Sie kein physisches Kickstart-ROM 3.2 verwenden, dann wird insgesamt 2,5 MB Gesamtspeicher benötigt
- 10 MB freier Festplattenspeicher

1. Integration des ReAction GUI-Toolkits
2. Integrierte ADF-Verwaltung (Amiga Disk File Image)
3. Integriertes Hilfe-Subsystem
4. Aktualisiertes Datentypsystem
5. Workbench und andere Verbesserungen der Benutzeroberfläche
6. Verbesserte Tools, Dienstprogramme und Systemanwendungen
7. Verbessertes Shell-Verhalten
8. Neuer und überarbeiteter Befehlssatz
9. Nachgebesserte Einstellungen
10. Poliertes MultiView
11. Überarbeitete Rohstoffe
12. Erweitertes BootMenü
13. Aufnahme und Verfeinerung des AmigaOS 3.1.4-Feature-Sets
14. Flexible Liefermedien
15. Viele bemerkenswerte Ergänzungen

## 1.  INTEGRATION DES REACTION GUI TOOLKIT

- Die Einbindung des ReAction GUI Toolkits eröffnet nicht nur eine Fülle bestehender Anwendungen für AmigaOS 3.2-Benutzer, sondern sorgt auch für eine viel einfachere Portabilität und Cross-Entwicklung zwischen verschiedenen Versionen von AmigaOS
- Keine zusätzliche Installation erforderlich, es funktioniert einfach, selbst auf Low-End-68000-Systemen
- Ein neuer Multi-File-Texteditor namens “TextEdit” ist als Showcase enthalten
- ReAction verfügt über einen eigenen Preferences-Editor, mit dem Sie Backfill-Muster für ReAction-basierte Programme festlegen können
- Neuer und fehlerbehobener Klassen-Backport von AmigaOS 4.x mit vielen exklusiven Eigenschaften und aufgefrischter Ästhetik

## 2. EINGEBAUTE ADF (AMIGA DISK FILE IMAGE) VERWALTUNG

- DAControl und trackfile.device bieten beispiellose Funktionalität, da sie es Benutzern ermöglichen, ADF-Dateien zu erstellen, zu mounten, einzufügen und auszuwerfen
- ADF-Bilder werden wie jede physische Diskette behandelt
- Auf “Workbench” können Sie ein ADF-Bild einbinden, indem Sie darauf doppelklicken
- Die ADF-Handhabung kann über Shell durch die Verwendung eines umfangreichen Satzes verfügbarer Optionen erfolgen
- Der Zugriff auf solche gemounteten ADF-Disk-Image-Dateien ist schnell und erfordert sehr wenig Speicher
- Mehrere ADF-Disk-Images können gleichzeitig gemountet werden
- Ein gemeinsam genutztes Cache-System ist verfügbar, um die ADF-Operationen zu beschleunigen

## 3. UNTERSYSTEM INTEGRIERTE HILFE

- Ein komplettes “Referenzhandbuch” deckt alle Befehle und die komplexesten Themen ab
- Ein AmigaGuide-basierter zentraler “Help-Hub” ist durch einfaches Drücken der HELP-Taste verfügbar
- Die Hilfedatenbank kann schnell über die Shell/CLI . abgefragt werden
- Einstellungen und viele andere Programme enthalten Hilfemenüpunkte
- Im WBStartup-Ordner fügt MenuTools den Menüpunkt “Hilfe” zum Menü “Tools” hinzu, kann aber auch angepasst werden, um andere Tools hinzuzufügen

## 4. AKTUALISIERTES DATENTYPSYSTEM

- Neuer unkomprimierter AIFF-Audiodatentyp
- Neuer GIF-Bilddatentyp
- Neuer WAV-Audiodatentyp
- Neuer JPEG-Bilddatentyp
- Neuer plattformübergreifender PNG-Bilddatentyp
- Neuer BMP-Datentyp für Windows/OS2-Bitmap-Bilder
- Neuer Icon.datatype ermöglicht die Verwendung von “.info”-Dateien als Bilder
- Neuer ACBM-Bilddatentyp (verwendet in AmigaBASIC & SpectraPaint)
- Der Datentyp AmigaGuide kann jetzt Inline-Bilder anzeigen
- Textdatentyp mit Suchfunktion
- Schnellere und besser konfigurierbare CDXL- und ANIM-Datentypen
- Sound.datatype verwaltet Bitraten-Samples von 8, 16, 24 und 32 Bit
- Picture.datatype ist jetzt auch auf Low-End-68000-Prozessoren erstaunlich schnell

## 5. AMIGAOS WORKBENCH UND ANDERE VERBESSERUNGEN DER BENUTZEROBERFLÄCHE

- Ändern Sie die Größe von Fenstern von jedem Rand aus
- Fenstersymbolik
- Anpassung der Workbench-Titelleiste
- Maximieren Sie ein Fenster, indem Sie die UMSCHALT-Taste gedrückt halten und auf das Fenster-Zoom-Gadget klicken
- Die [ESC]-Taste beendet Easy Requester
- Skalierbare “GadTools”-Benutzeroberfläche, die sich an unterschiedliche Schriftgrößen anpasst
- Workbench-Menü “Volume öffnen”
- Menüfenster -> Sortierreihenfolge (vorwärts oder rückwärts)
- Off-Screen-Fenster ist ein integrierter Standard, der jetzt konfigurierbar ist
- Scroller und Slider verfügen jetzt über geprägte Knöpfe im 3D-Stil und einen dunkleren Container-Hintergrund
- Neuere Look-Menüs: Paletteneinstellungen “Menü Helle Kanten” + “Menü Dunkle Kanten”
- Neuere Look-Menüs: Untermenüanzeige von “»” in ein schwarz gefülltes Dreieck geändert
- Neuere Look-Menüs: Häkchen in sich gegenseitig ausschließenden Optionen durch einen schwarz ausgefüllten Kreis ersetzt
- Workbench Prefs definiert Schubladenplatzierung im Textmodus

## 6. VERBESSERTE TOOLS, DIENSTPROGRAMME UND SYSTEMANWENDUNGEN

- Interaktive Partition “Mounter”
- Mit “Suchen” können Sie schnell nach Dateinamen oder Dateiinhalten suchen
- “ShowConfig” hat jetzt eine ästhetisch ansprechende Benutzeroberfläche und zeigt AutoConfig-Hardware in einer für Menschen lesbaren Form an
- HDToolBox kann jetzt bei Bedarf von schreibgeschützten Medien aus arbeiten

## 7. VERBESSERTES SHELL

- Konfigurierbare TAB-Autovervollständigung
- Möglichkeit, Symbole in Shell-Fenstern abzulegen
- Shell-Fehlerumleitung
- “Execute” ist jetzt ein interner Shell-Befehl
- “History” ist ein neuer interner Shell-Befehl
- Shell-Operatoren && und || für UND plus Verkettungsoperationen
- Eine Debug-Variable sendet ausgeführte Befehle an die serielle Schnittstelle
- Shell-Start wurde für eine einfachere Anpassung angepasst

## 8. NEUE UND ÜBERARBEITETE BEFEHLE

- C:Eval gruppiert Operationen richtig
- C:Copy erhält eine FORCE-Option zum Überschreiben von Zielen
- C:Protect erhält USER, GROUP, OTHER, CLONE, CLEAR, FILES und DIRS
- C:SetDate kann das Datum AUS einer Datei kopieren
- C:List bietet die Optionen FLAT, SORT, USERS, GROUP, LFORMATQUOTE
- C:Mount SHUTDOWN versucht, Handler herunterzufahren
- C: Weisen Sie integrierte DENIED- und DIMOUNT-Schalter zu
- C:Type unterstützt die Optionen AUTO, TEXTONLY, WIDTH und BUFFER
- C:Reboot startet Ihren Amiga neu, wartet aber auf laufende Schreibvorgänge , um Validierungsprobleme zu vermeiden
- C:Group- und C:Owner-Befehle für Netzwerkumgebungen hinzugefügt
- C:MD5Sum berechnet und vergleicht Prüfsummen von Dateien und Volumes
- C:MountInfo-Befehl hilft bei der Erstellung von MountLists
- C:Break und C:ChangeTaskPri NAME behandeln Wildcard-Optionen
- C:DefIcons identifiziert Dateien und wendet ein Standardsymbol auf sie an
- C:AssignWedge ermöglicht es Benutzern, eine Zuweisung im laufenden Betrieb zu erstellen oder abzulehnen
- C:LoadMonDrvs vereinfacht und startet Monitortreiber schnell.

## 9.  BERÜHRT PRÄFERENZ-EDITOREN

- Benutzerdefiniertes Druckerausgabegerät und Gerätenummer
- WBPattern bietet Layoutoptionen für Hintergründe, Bildschirme und Fenster, die sowohl Farbe als auch Dithering umfassen
- PointerPrefs wurde überarbeitet, um 40 verschiedene Zeigertypen zu unterstützen
- Schriftarteinstellungen werden mit Optionen für die Schriftarten Schatten und Kontur geliefert
- IControl erhielt eine massive Überarbeitung, die neue Funktionen wie die Anpassung des Seitenverhältnisses von Fenstern und Bildschirmrändern einführte

## 10. POLIERTE MULTIVIEW

- Ein neuer Menüpunkt “Bearbeiten/Einfügen” öffnet den Inhalt der Zwischenablage- Einheit 0 (und ergänzt damit “Bearbeiten/Kopieren”)
- Das „Info“-Fenster meldet jetzt die Breite, Höhe und Tiefe des aktuell angezeigten Bildes oder der Animation
- Die Namen von ARexx-Skripten für Benutzermenüs können jetzt bis zu 40 Zeichen lang sein und dürfen “Leerzeichen” enthalten
- Durch Drücken der [Shift]-Taste bei ausgewähltem Menüpunkt “Speichern unter…” wird MultiView gezwungen, das angezeigte Dokument im IFF-Format zu speichern
- Listet jetzt den Mustervergleich in seinem ASL-Requester auf, der, wenn er entfernt wird, auch Symbole anzeigen kann (nützlich in Verbindung mit dem neuen icon.datatype).

## 11.  ÜBERARBEITETE ROHSTOFFE

- “RAWBInfo” ist ein verbesserter Ersatz des Symbolinformationstools
- “AsyncWB” ist eine AmigaOS Workbench Erweiterung Commodity mit diversen Funktionalitäten
- “AutoPoint” KEEPSTRINGS verhindert, dass diese Ware automatisch den Fokus aus einem Fenster mit einem aktiven String-Gadget stiehlt
- “ClickToFront” TOBACK_QUALIFIER wählt einen Qualifier zum Zurücksenden von Fenstern (mit einem einzigen Klick)
- “ClickToFront” bringt beim Doppelklicken auf ein Icon keine Workbench-Fenster mehr in den Vordergrund
- „NumericPad“ ermöglicht Ziffernblock – Tasten auf den Standard neu zugeordnet werden Tastatur
- Der Commodity-ähnliche Satz von Skripten “AutoArrangeIcons” automatisiert die Anordnung und Momentaufnahme von Symbolen im aktiven Fenster

## 12. ERWEITERTES BOOTMENÜ

- Eine Option zum zeilenweisen Nachverfolgen der Startup-Sequenz ist jetzt verfügbar
- Der Benutzer kann ROM-Modul-Updates deaktivieren, indem er auf ein Gadget klickt
- Der Hardware-Erweiterungsbildschirm zeigt Adressen und Größen der Erweiterungskarten an
- Mit der Option “Systemprotokoll aktivieren” ist eine neue Option zum Umleiten der Ausgabe des seriellen Ports in eine Datei verfügbar.
- Das Boot-Gadget “Failsafe” startet den Amiga in einer robusten und sicheren Umgebung, um Wartungs- und Fehlerbehebungsaufgaben durchzuführen
- Weitere Tastenkombinationen für die meisten Optionen
- Zeigt AmigaOS Kickstart-Versionsnummern an

## 13. EINBEZIEHUNG UND VERFEINERUNG DES AMIGAOS 3.1.4 FEATURE SET

- Unterstützung für Speichermedien größer als 4 GB
- Modernisierte AmigaOS Workbench
- DiskDoctor für Datenträgerdiagnose und Wiederherstellungsvorgänge
- Native Unterstützung für Pipes, Softlinks, Hardlinks und lange Dateinamen
- CrossDOS unterstützt FAT 32 und lange Dateinamen
- CD-ROM-Dateisystem, das die Erweiterungen Rockridge und Joliet sowie UDF und jetzt auch Macintosh HFS unterstützt
- Sowohl FFS (FastFileSystem) als auch das CD-ROM-Dateisystem sind jetzt intelligenter, schneller und multithreaded
- Vollständig überarbeitete und fehlerkorrigierte Druckertreiber
- Integrierte GlowIcons-Unterstützung als installierbare Option
- Mehr als 2100 Icons im GlowIcon-Stil auf der AmigaOS 3.2 CD-ROM

## 14. FLEXIBLE LIEFERMEDIEN

- Die Distribution AmigaOS 3.2 CD-ROM enthält ADF-Disk-Images, die auf physische Disketten oder Gotek-Laufwerke übertragen werden können
- Alle Module-Festplatten funktionieren auch als Notfall-Boot-Festplatten
- Die DiskDoctor-Festplatte kann Benutzern helfen, bei Festplattenfehlern schnell wieder auf die Beine zu kommen
- Der Inhalt der AmigaOS 3.2 CD-ROM kann “as is” auf eine Amiga-formatierte Festplatte kopiert und dank der “Amiga Preinstallation Environment” (AmigaPE) sofort zur Installation gebootet werden.
- Alle Amiga-Modelldisketten und AmigaOS-Kickstart-ROM-Set-Images sind auf der AmigaOS 3.2-CD-ROM verfügbar
- Attraktive bedruckbare Etiketten sind für alle Ihre bevorzugten AmigaOS 3.2-Speichermedienvarianten verfügbar (nur AmigaOS 3.2 CD-ROM-Version)
- Experimentelle CD-ROM-basierte Unterstützung für Amiga CDTV und Amiga CD32

## 15. VIELE BEMERKENSWERTE ERGÄNZUNGEN

- Wheel-Maus-Unterstützung zum Scrollen in AmigaOS Workbench-Fenstern
- IPrefs stapelt mehrere Änderungen und aktualisiert den Bildschirm nur einmal
- IPrefs weist beim Aktualisieren auf Namen von blockierenden Fenstern hin
- Kein DF0 mehr:???? Symbole, da disk.resource jetzt eine ordnungsgemäße Überprüfung durchführt
- Erhöhte Flexibilität der ROM-Module, indem mehr Module von der Festplatte geladen werden, ohne dass ein zusätzlicher Neustart für sie erforderlich ist
- Neuimplementierung der Funktionalität “HappyENV/ENV-Handler” integriert
- Keine MaxTransfer-Werte mehr für eingebauten Commodore und andere bekannte Hardware-Controller verschiedener Hersteller erforderlich
- “Installer” ist besser mit früheren AmigaOS-Versionen kompatibel
- Mehrere Eingabeereignisse werden von input.device unterstützt
- Zwei neue Warnungen melden Modulprobleme für eine einfachere Systemdiagnose
- Neue API-Funktionen für Entwickler
- Optionale generische Prozessorunterstützungsbibliotheken für 68K CPU-Boards
