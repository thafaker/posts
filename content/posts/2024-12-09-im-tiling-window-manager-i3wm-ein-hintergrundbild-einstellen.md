---
title: Setup Wallpaper in tiling Window Manager i3WM - ein Hintergrundbild einstellen
slug: im-tiling-window-manager-i3wm-ein-hintergrundbild-einstellen
date_published: 2024-12-09T08:11:35.000Z
date_updated: 2024-12-15T08:38:33.000Z
tags: linux, i3wm, howto, anleitung, background, Powermac G5
---

In **i3wm** (i3 Window Manager) kannst du ein Hintergrundbild einstellen, indem du ein separates Programm wie **feh** oder **nitrogen** verwendest. Hier sind die Schritte, wie du dies in **Debian 12 SID** (der PowerPC64 Linux-Distribution auf meinem Powermac G5) umsetzen kannst.

Mein Bild habe ich in meinem User-Verzeichnis unter Bilder gespeichert, der Pfad lautet also "/home/thahipster/Bilder/rennrad.jpg" für das Bild meines Rennrades.

### 1. **Feh installieren**

Feh ist ein leichtes Tool zur Bildanzeige, das sich gut für das Setzen von Hintergrundbildern eignet.

    sudo apt update
    sudo apt install feh

### 2. **Hintergrundbild mit Feh einstellen**

Führe den folgenden Befehl aus, um ein Bild als Hintergrund festzulegen:

    feh --bg-scale /home/thahipster/Bilder/rennrad.jpg

- `--bg-scale`: Passt das Bild proportional an, um den Bildschirm zu füllen.
- Alternativen:
- `--bg-center`: Zentriert das Bild.
- `--bg-fill`: Füllt den Bildschirm ohne Verzerrung.
- `--bg-tile`: Kachelt das Bild.

### 3. **Automatisches Laden des Hintergrundbildes**

Damit das Hintergrundbild beim Start von i3wm automatisch geladen wird, füge die Feh-Anweisung zur **`~/.config/i3/config`** (dort liegt die Konfigurationsdatei von i3) hinzu:

    exec --no-startup-id feh --bg-scale /home/thahipster/Bilder/rennrad.jpg

### 4. **Optional: Nitrogen installieren**

Falls du ein grafisches Tool bevorzugst, kannst du **nitrogen** verwenden:

    sudo apt install nitrogen

- Starte **nitrogen** mit: **`nitrogen`**
- Wähle das gewünschte Bild aus und speichere die Einstellung.
- Füge der **`~/.config/i3/config`** folgende Zeile hinzu, um die Nitrogen-Einstellung beim Start zu laden:

    exec --no-startup-id nitrogen --restore

### 5. **Konfiguration neu laden**

Nach der Bearbeitung der i3-Konfiguration lade diese neu, indem du `Mod+Shift+R` drückst (wobei `Mod` bei mir die Apfel/Windows-Taste ist).
