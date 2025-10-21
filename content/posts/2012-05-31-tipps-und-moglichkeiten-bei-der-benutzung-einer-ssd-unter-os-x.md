---
title: Tipps und Möglichkeiten bei der Benutzung einer SSD unter OS X [UPDATE]
slug: tipps-und-moglichkeiten-bei-der-benutzung-einer-ssd-unter-os-x
date_published: 2012-05-31T19:38:48.000Z
date_updated: 2024-05-24T08:16:01.000Z
---

Wie ihr vielleicht schon in meinem [kleinen Artikel](__GHOST_URL__/ssd-via-fw800-an-imac-27/) gelesen habt, besitze ich seit kurzer Zeit eine SSD in einem externen *FW800 Gehäuse*. Um diese ordentlich unter Mac OS betreiben zu können, möchte ich ein paar Hinweise sowie Tipps und Tricks für ein langes Leben der SSD mit auf dem Weg geben.

### TIPP 1: TRIM ENABLER

An erster Stelle sollte der legendäre [TRIM ENABLER](__GHOST_URL__/trim-support-os-x-10-7-3-mit-trim-enabler-reaktivieren/) genannt werden. Diese freie Software rüstet die Möglichkeit in OS X 10.7 Lion nach, für alle, also auch für nachträglich eingebaute nicht-Apple-SSDs, den sogenannte TRIM-Support durch das Betriebssystem zu aktivieren. Wenn man eine SSD im Rechner hat die nicht von Apple stammt, dann ist diese Software die allererste und eine sehr wichtige Wahl!

### TIPP 2: Hibernate

Im nächsten Schritt sollte man dann den *Hibernate Modus* von Mac OS deaktivieren, da dadurch immer wieder der komplette Arbeitsspeicher-Inhalt auf die SSD geschrieben wird. Im Terminal werden die beiden folgenden Zeile eingeben und man hat Hibernate deaktiviert und auch das ggf. vorhandene letze RAM-Image gelöscht: ((Wenn in einer Zeile im Terminal 0 am Ende steht, dann heißt das "aus", einschalten kann man es also, wenn man das selbe mit 1 noch ein mal durchführt.))

`sudo pmset -a hibernatemode 0`

`sudo rm /var/vm/sleepimage`

### TIPP 3: FÜR NOTEBOOKS - Deckel Power

Als nächstes sollte man einstellen, WENN MAN EIN NOTEBOOK HAT, dass das Macbook nur per Druck auf den Power-Button wieder aufgeweckt wird. Beim Aufwecken wird immer relativ viel geschrieben auf der Platte, daher sollte man es vermeiden das MacBook immer wieder ausversehen durch öffnen zu starten. Dafür im Terminal folgendes eingeben:

`sudo pmset lidwake 0`

### TIPP 4: NO ATIME für SSD

Um noch ein ganz bisschen mehr Geschwindigkeit zubekommen und sich noch ein paar Schreibzugriffe zu sparen, kann man die SSD im noatime-Modus mounten. Dies bedeutet, dass die Daten über den letzten Zugriff auf Dateien nicht in Filesystem vermerkt werden. Da ich meine eigentlichen Daten auf meiner HDD habe stört mich dies nicht weiter, diese schreibt weiterhin die Zugriffsdaten. Wenn ihr allerdings die SSD alleine im MacBook habt müsst ihr selber wissen, ob es euch stört wenn ihr z.B. Dateien nicht mehr nach letztem Zugriff sortieren und suchen lassen könnt.

## Um noatime zu aktiveren geht wie folgt vor

1. Legt eine Textdatei mit dem Namen com.noatime.plist an. Ihr könnt die Datei auch hier runterladen. Den Inhalt könnt ihr hier sehen.
2. Kopiert die Datei nach /Library/LaunchDaemons/ (nicht im Userverzeichnis)
3. Damit die Datei richtig geladen werden kann müssen, die Benutzerrechte noch angepasst werden. Führt daher im Terminal fogendes aus: sudo chown root:wheel /Library/LaunchDaemons/com.noatime.plist
4. Jetzt den Rechner neustarten
5. Um zu überprüfen ob es geklappt hat, könnt ihr im Terminal den Befehl mount ausführen. Hinter der SSD sollte nun noatime stehen.

Einige Leute empfehlen auch, den Dienst *Spotlight* zu deaktivieren, allerdings nutze ich Spotlight recht häufig und habe daher nur meine System-SSD in den Privatshären-Einstellungen hinzugefügt. So kann ich meine Datenfestplatte weiterhin durchsuchen.

### Cache des Browsers

Häufig gibt es die Empfehlung, den Caches des Browsers zu deaktiveren bzw. in eine RAM-Disk auszulagern, damit nicht immer auf der SSD geschrieben wird. Eine Beschreibung werde ich nachrreichen.

Folgender Befehler sollte eine RAM-Disk mit 1GB Speicher erstellen:

`diskutil erasevolume HFS+ "ramdisk" `hdiutil attach -nomount ram://2165430``

Folgender Befehle sollten nun den Browserchache von Google Chrome auf diese RAM-Disk auslagern.

Open a terminal and enter the following commands :

cd ~/Library/Caches/Google/Chrome/Default/ (Enter drücken)

sudo rm -rf Cache (Enter drücken; Kennwort eingeben)

sudo ln -s /Volumes/ramdisk Cache (Enter drücken)

Chrome Neustarten

Website besuchen.

Gucken ob in der Ramdisk nun Dateien liegen.

Wenn ja, dann cached Chrome jetzt in die Ram-Disk und erspart euch viele Zugriffe auf die SSD.

Das funktioniert übrigens auch analog dazu mit Firefox, der hat sein CacheVerzeichnis auch im Ordner Library/Caches, Dieses kann man auch auf die Ramdisk auslagern.

### TIPP 5: Sudden Motion Sensor deaktivieren

Sollte man die SSD als einzige Platte im Gerät haben, kann man den *Sudden Motion Sensor* deaktivieren. Dieser Sensor ist ein Beschläunigungssensor der die normale Festplatte anhält, wenn das Gerät vom Tisch stürzt, damit kein Datenverlust auftritt, wenn die Magnetköpfe einer normalen Festplatte bei Erschütterungen auf die Platte krachen. Der SSD machen Erschütterungen nichts und der Sensor könnte daher kontraproduktiv sein. Solltet ihr zusätzlich eine normale Festplatte im Gerät haben, ignoriert dies. Zum deaktivieren des Sensors folgende Zeile im Terminal eingeben:

`sudo pmset -a sms 0`

### TIPP 6: Benutzerverzeichnis (Home Ordner) auslagern.

Solltet ihr übrigens eure SSD nur für das System nutzen wollen und nicht für eure Daten, ist es am praktischsten euer Benutzerverzeichnis komplett auf die HDD zu verschieben. Dies könnt ihr wie folgt erledigen:

Erstellt euch einen zweiten Admin Benutzer. Diesen braucht ihr um eueren eigentlichen Benutzer ordentlich umzuziehen. Denn zwei Benutzer mit dem selben Namen sind logischerweise nicht möglich. Loggt euch also mit eurem neuen Admin ein. **Kopiert** (Kopieren ist sicherer als verschieben) jetzt euren eigentlichen Benutzerordner komplett und vollständig auf die HDD und stellt dann das Home-Verzeichnis um. Dafür geht ihr in die Mac OS Systemeinstellungen für Benutzer. Klickt dort mit einem Rechts-Klick (oder crtl+Klick) auf euren Benutzer, der auf die HDD umziehen soll. Nun könnt ihr die “Erweiterten Optionen” auswählen und beim Benutzerordner, euren Ordner auf der neuen HDD auswählen (siehe Screenshot). Nun könnt ihr euch von eurem Umzieh-Admin ausloggen, ein mal neu starten und in euren originalen bisherigen Benutzer einloggen, sollten alle Dateien da sein und das Homeverzeichnis auf der HDD liegen könnt ihr die Daten von der anderen Festplatte löschen.

### Hinweise

[**ACHTUNG**] Die SSD wird im Firewire-Gehäuse nicht als selbige erkannt, OS X sieht nur den Firewire-Chipsatz. Somit funktionieren auch Programme wie der sehr gute Trim-Enabler nicht. Dies kann zu einem Problem werden, wenn die SSD von sich aus nicht über Garbage-Collection verfügt und auf TRIM durch das Betriebssystem angewiesen ist.
[![Systeminformation FW800 SSD](//picdump.thafaker.de/2012/05/Bildschirmfoto-2012-05-31-um-19.13.38-580x472.png)](http://picdump.thafaker.de/2012/05/Bildschirmfoto-2012-05-31-um-19.13.38.png)

([via](http://apple-gadgets.de/ssd-tipps-fuer-mac-os/))
