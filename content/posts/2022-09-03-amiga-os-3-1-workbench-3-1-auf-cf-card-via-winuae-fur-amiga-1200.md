---
title: AMIGA OS 3.1 Workbench 3.1 auf CF-Card via WinUAE für echten AMIGA 1200
slug: amiga-os-3-1-workbench-3-1-auf-cf-card-via-winuae-fur-amiga-1200
date_published: 2022-09-03T20:11:38.000Z
date_updated: 2022-09-04T10:00:38.000Z
tags: amiga, kickrom 3.1, workbench, workbench 3.1, amiga os, vintage computing, cf card, fs-uae, emulator, kickstarter, vintage-pc, vintage games, anleitung, howto, how to
---

Diese Anleitung dient dazu, eine CF-Karte am internen IDE-Port eines Amiga 1200 als Festplatte einzurichten. Eigentlich würde man dies direkt am Gerät mit den Installationsdisketten machen, aber manch einer hat nur einen A1200 und keine funktionierenden Installationdisketten mehr, kann aber grundsätzlich auf [ADFs](https://en.wikipedia.org/wiki/Amiga_Disk_File) der Disketten zugreifen weil er sich mal Abbilder erstellt hat oder welche im Netz fand. Hier hat man dann die Möglichkeit, die Installation am Windows-PC mit [WinUAE](http://www.winuae.net/) durchzuführen, das ist an vielen Stellen deutlich komfortabler als am echte Amiga.

Später werde ich eine ausführliche Anleitung zur problemlosen Installation von [WHDLoad](https://de.wikipedia.org/wiki/WHDLoad) schreiben.

Leider ist es so, dass nicht alle CF-Karten am IDE-Port des Amigas funktionieren. Mir ist keine Möglichkeit bekannt, einer CF-Karte anzusehen ob sie für den Betrieb am Amiga geeignet ist ohne dies durch Ausprobieren zu ermitteln. Dazu braucht man aber eben die Installationsdisketten...

Lange Rede, kurzer Sinn: es kann passieren, dass ihr eure CF-Karte anhand dieser Anleitung einrichtet und dass diese in WinUAE auch prima funktioniert, aber am echten Amiga dennoch den Dienst verweigert.

Zur Größe der CF-Karte: ein ungepatchtes AmigaOS kann mit Festplatten bis zu 4GB Größe und Partitionen bis zu 2GB umgehen. Praktisch würde ich es aber vermeiden diesen Bereich voll auszunutzen, da es in Grenzbereichen durchaus mal zu Überläufen kommen kann. Man riskiert im schlimmsten Fall damit Fehler die für Datenverlust sorgen, diese aber u.U. noch monatelang unbemerkt bleiben können. Ich würde daher maximal 1GB große Karten verwenden..

---

## [Die Ausrüstung](Die Ausrüstung)

Für den Betrieb einer Amiga-Emulation ist grundsätzlich ein Image eines [Kickstart](https://de.wikipedia.org/wiki/Kickstart)-ROM nötig, das das Basissystem des Amiga-Betriebssystems darstellt, welches urheberrechtlich geschützt ist und käuflich erworben werden muss. Wer einen echten Amiga besitzt, besitzt bereits ein Kickstart-ROM und kann es mittels entsprechender Software in eine Datei extrahieren und auf einen anderen Computer übertragen und nutzen. Alternativ können Emulator-Distributionen wie Amiga Forever und Amiga Classix im Handel gekauft werden, die diese ROMs und oft auch das AmigaOS (Workbench) mitliefern.

- Windows-PC oder Mac (FS-UAE statt WinUAE) mit Cardreader
- Amiga 1200 mit Kickstart 3.0 oder 3.1
- eine max. 4 GB große CF-Karte (WB 3.1 erkennt bis 4 GB, kleiner ist besser)
- WinUAE (Mac: FS-UAE) in der aktuellen Version (kostenfrei)
- Kickstart ROM file: 'KS ROM v3.1 (A1200) rev 40.68 (512k) [391773-01/391774-01]'
- Alle sechs Workbench 3.1 Disks als ADFs
- * WB3.1_Extras.adf
- * WB3.1_Fonts.adf
- WB3.1_Install.adf
- WB3.1_Locale.adf
- WB3.1_Storage.adf
- WB3.1_Workbench.adf

---

## [CF-Karte vorbereiten](CF-Karte vorbereiten)

CF-Karten sind normalerweise partitioniert und formatiert; damit wir aber die CF-Karte von WinUAE aus partitionieren können, muss die Karte komplett gelöscht werden, da ansonsten keine Schreibzugriffe auf den ersten Block stattfinden können. Das machen wir mit dem Programm DiskPart. Hierfür stecken wir die CF-Karte in den Kartenleser und starten eine Kommandozeile mit Administratorrechten:

![Command Prompt - Run as administrator](__GHOST_URL__/content/images/2022/09/01.png)
In der Administrator-Kommandozeile geben wir 'diskpart' ein und lassen uns dann per 'list disk' die Laufwerke am Rechner anzeigen. Aus der Liste suchen wir unsere CF-Karte aus und wählen die per 'select disk n' wobei 'n' für die Nummer der CF-Karte steht, also z.B. 'select disk 7'. Wenn die erfolgreich gewählt wurde löschen wir diese mit einem beherzten 'clean' (An dieser Stelle solltet ihr euch sehr sicher sein, dass ihr auch wirklich die CF-Karte gewählt habt und nicht etwa eure Systemfestplatte!)
Das wars auch schon, ihr verlasst DiskPart mit einem 'exit' und eure CF-Karte ist komplett gelöscht. Hier noch ein Beispiel wie das bei mir aussieht:
![Administrator: Command Prompt](__GHOST_URL__/content/images/2022/09/02.png)
---

## [WinUAE konfigurieren](WinUAE konfigurieren)

WinUAE muss hierfür nicht mit Administratorrechten gestertet werden:
![WinUAE - Run as administrator](__GHOST_URL__/content/images/2022/09/03.png)
Dort basteln wir uns erstmal einen A1200 zusammen:
bei 'Paths' geben wir den Pfad zu unserem 3.1-Rom bei 'SystemROMs' an und klicken 'Rescan ROMs'.

- Bei 'Quickstart' wählen wir als 'Model' einen 'A1200' aus.

Bei 'Hardware->Hard drives' binden wir unsere CF-Karte ein:

- Dort klicken wir auf 'Add Hard Drive...' worauf sich ein kleiner Dialog 'Harddrive Settings' öffnet. 
- Dort wählen wir als 'Hard drive' unsere CF-Karte aus, lassen 'HD Controller' auf 'UAE', setzen ein Häkchen bei 'Read/write' und klicken dann auf 'Add hard drive'. 
- Auch hier sollten wir uns sehr sicher sein, dass wir tatsächlich die CF-Karte ausgewählt haben. Vergleicht die Größen und da wir sie vorher gelöscht haben sollte sie als [UNK] ('unknown') geführt werden:

![Harddrive Settings](__GHOST_URL__/content/images/2022/09/04.png)
Wir starten jetzt WinUAE und sollten von einem freundlichen Kickstart-Screen begrüßt werden:
![WinUAE - Kickstart 3.1](__GHOST_URL__/content/images/2022/09/as.png)
---

## [CF-Karte in WinUAE partitionieren](CF-Karte in WinUAE partitionieren)

Wir legen jetzt das WB3.1_Install.adf ins virtuelle Laufwerk DF0: ein und es sollte nach einer Weile in die Workbench gebootet werden:
![Workbench 3.1](__GHOST_URL__/content/images/2022/09/a1200_02.png)
Dort öffnen wir uns eine Shell per 'Rechtsklick -> Execute Command...' und geben in dem Fenster dann 'newshell' ein:
![Execute a File](__GHOST_URL__/content/images/2022/09/a1200_03.png)
In die Shell geben wir ein:

    copy sys:hdtools/hdtoolbox ram:
    cd ram: 
    hdtoolbox uaehf.device

(bei einer deutschen Tastatur ist das 'y' unter dem 'z', das '/' unter dem '-' und der Doppelpunkt unter 'Shift-ö') 
Wir kopieren hierbei die HDTOOLBOX von der Diskette in die RAM-Disk und laden es von dort mit dem Treiber uaehdf.device um so auf unsere CF-Card zugreifen zu können.
![AmigaShell](__GHOST_URL__/content/images/2022/09/a1200_04.png)
In dem erscheinenden Fenster sollte nun eine Festplatte angezeigt werden:
![Hard Drive Preparation, Partitioning and Formatting](__GHOST_URL__/content/images/2022/09/a1200_05.png)
Wir klicken auf 'Change Drive Type' und in dem Fenster dann auf 'Define New...
![Set Drive Type](__GHOST_URL__/content/images/2022/09/a1200_06.png)
Dort lassen wir die CF-Karte einlesen durch Betätigen von 'Read Configuration'
![Define/Edit Drive Type](__GHOST_URL__/content/images/2022/09/a1200_07.png)
Zurück im 'Set Drive Type'-Fenster wählen wir unser neues Drive aus und klicken 'OK':
![Set Drive Type](__GHOST_URL__/content/images/2022/09/a1200_10.png)
Nun klicken wir auf 'Partition Drive' und legen unsere Partitionen an. Zwei Partitionen sind schon vorgegeben, ich empfehle jede Partition deutlich kleiner als 2GB zu halten und von der CF-Karte auch nur die ersten 2GB zu belegen. Vergebt noch passende Partitions-Device-Namen, auf dem Amiga üblich sind 'DH0', 'DH1', usw. und achtet darauf dass die erste Partition als Bootable markiert ist:
![Partitioning](__GHOST_URL__/content/images/2022/09/a1200_12.png)
**ACHTUNG**: Um später im echten Amiga Datenfehler zu vermeiden muss unbedingt für jede Partition ein Wert angepasst werden. Dafür öffnen wir das Fenster 'File System Characteristics' durch einen Klick auf 'Change...' und ändern dort den Wert 'MaxTransfer' auf '0x1fe00'. Dies wiederholen wir für jede Partition die wir angelegt haben.
![File System Characteristics](__GHOST_URL__/content/images/2022/09/a1200_12a.png)
Zurück im Fenster 'Partitioning' klicken wir auf 'OK' und dann auf 'Save Changes to Drive'. Dann beenden wir HDToolBox und resetten WinUAE. Nach dem Booten sollten die angelegten Partitionen als NDOS angezeigt werden:
![](__GHOST_URL__/content/images/2022/09/a1200_13.png)
Die Partitionen müssen noch formatiert werden, diese dazu anwählen und per 'Rechtsklick -> Icons -> Format Disk...' das Formatierungsprogramm starten. Hier nun einen passenden Volume-Namen eingeben und per 'Quick Format' formatieren:
![](__GHOST_URL__/content/images/2022/09/a1200_14.png)
Das nun mit allen Partitionen wiederholen, am Ende sehen wir für jede Partition frisch formatierte Disketten-Icons auf der Workbench:
![Workbench 3.1](__GHOST_URL__/content/images/2022/09/a1200_15.png)
Jetzt könnt ihr den Workbench-Installer von der Install-Disk starten und die Installation durchführen. Dabei sind die ADFs in WinUAE nach Ansage zu ändern:
![Install Workbench 3.1](__GHOST_URL__/content/images/2022/09/a1200_16.png)
Nach der Installation DF0 auswerfen und rebooten:
![Amiga OS 3.1 Installation beendet](__GHOST_URL__/content/images/2022/09/a1200_17.png)Amiga OS 3.1 Installation beendet
WinUAE sollte nun in die frisch installierte Workbench booten:
![Amiga Workbench zeigt Kickstart und Workbench Version](__GHOST_URL__/content/images/2022/09/a1200_18.png)Amiga Workbench zeigt Kickstart und Workbench Version
Jetzt ist eine gute Gelegenheit per WinUAE noch ein paar Programme und ADFs auf die CF-Karte zu packen, z.B. LHA, ansonsten sollte die Karte in den A1200 eingebaut ebenfalls in die Workbench booten und ihr habt eine fertig installierte CF-Card Festplatte für euren AMIGA 1200.
![Mein Amiga 1200 mit neuem Amiga.net Gehäuse, einer ACA1233n 40 Turbokarte nebst 128 MB Ram und einer 4GB CF mit OS3.1.4 und BetterWB](__GHOST_URL__/content/images/2022/09/background-2.JPG)Mein Amiga 1200 mit neuem Amiga.net Gehäuse, einer ACA1233n 40 Turbokarte nebst 128 MB Ram und einer 4GB CF mit OS3.1.4 und BetterWB
*Viel Spaß am Gerät, es bleibt spannend*.

Diese Anleitung erschien zuerst bei kaiiv.de (C) Kai Scherrer, wird dort aber scheinbar nicht mehr gepflegt.
