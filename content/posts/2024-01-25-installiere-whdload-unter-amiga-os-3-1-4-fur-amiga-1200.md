---
title: "HSTWB: Installiere WHDLoad unter AMIGA OS für AMIGA 1200 via WinUAE"
slug: installiere-whdload-unter-amiga-os-3-1-4-fur-amiga-1200
date_published: 2024-01-25T08:45:00.000Z
date_updated: 2025-02-25T17:04:19.000Z
tags: whdload, retro gaming, hello again, ocs, specs, HSTWB, better wb, best wb, classic workbench, amiga os 3.2, amiga 1200, retro computing, fs-uae, win-uae, howto, anleitung, aga, vintage computing, vintage
excerpt: Dies wird ein etwas längerer Artikel in welchem ich beschreibe, wie man WHDLoad und AMIGA OS 3.2 auf einer CF-Card installiert. Ich nutze dafür das großartige Toolset HSTWB Installer und erkläre zu Beginn, wie dieser konfiguriert wird. 
---

Dies wird ein etwas längerer Artikel in welchem ich beschreibe, wie man **WHDLoad** und **AMIGA OS 3.2** auf einer* CF-Card* installiert. Ich nutze dafür das großartige Toolset **HSTWB Installer** und erkläre zu Beginn, wie dieser konfiguriert wird. 

## Table of Contents

1. **HSTWB: Installiere WHDLoad unter AMIGA OS für AMIGA 1200 via WinUAE**
2. [HSTWB Installer clickthrough unter WinUAE](__GHOST_URL__/hstwb-installer-unter-winuae/)

---

## HSTWB

💡

Automated installation of Amiga OS 3.9, 3.2, 3.1.4, 3.1, Kickstart roms and packages for Classic Amiga

Der *HstWB Installer* ist eine Anwendung, die die Installation von Amiga OS, Kickstart-ROMs und Software-Paketen mit zusätzlichen Inhalten automatisieren kann. Das heißt wenn man dieses Paket einmal richtig konfiguriert hat, dann übernimmt es die gesamte Arbeit: Die Festplatte (SD-Card) partitionieren, das System installieren (Diskettenwechsel, alles), zusätzliche Tools und Updates aufspielen und vor allem WHDLoad vollautomatisch dazu packen. 

Zunächst ladet ihr euch die Version herunter, die zur Größe eurer CF-Card passt. Ich habe eine 16 GB Karte. 16 GB sind gut weil dort WHDLoad in voller Gänze, also mit allen Spielen drauf passt und noch Platz für andere Software bleibt. Hat man nur eine 4 GB Karte zur Hand dann funktioniert das natürlich auch, allerdings passt dann WHDLoad nicht mit drauf. Hier könnte man sich überlegen *nur* den Teil von WHDLoad zu installieren, der die AGA-Spiele betrifft. Aber dazu kommen wir noch.

- [HSTWB Download](https://hstwb.firstrealize.com/download)

Wundert euch nicht: nachdem ihr den Download entpackt habt, seht ihr ein paar Ordner, eine 16 GB (je nachdem was für eine Version ihr geladen habt) große HDF Datei (das ist das Festplattenimage) und sehr viele Konfigurationsdateien. HSTWB ist eine Sammlung von Scripten die unter Windows, MacOS oder Linux lauffährig sind, aber es gibt keine EXE oder ähnliches um eine Softwareumgebung zu starten. Es läuft alles über Scripte. 

In meinem Beispiel nutze ich folgende Datei: [16GB HstWB self install HDF image v1.6.3](https://www.hstwb.com/releases/hstwb-installer_1.6.3/16gb_hstwb_1.6.3.zip)

💡

Man kopiert sich seine Dateien zusammen, in den Ordner HSTWB. Das geht los beim Kickrom, geht weiter über WHDLoad-Spiele und endet beim Amiga OS. Von 3.0 bis 4.1 lässt sich alles installieren, vollautomatisch über die Scripte.

### Konfiguration

Zunächst sollten wir die Ordner befüllen. Folgende Ordner gibt es im extrahierten Archiv:

- **amigaos**: Hier werden die Amiga-OS Installationsdisketten **.adf* hinein kopiert. Es empfiehlt sich, immer nur ein AmigaOS zu befüllen. Jenes, welches man auch installieren möchte. Ich kopiere also in den Unterordner amiga-os.3.2 meine original bei Hyperion erworbenen AMIGA-OS *.adf Diskettenfiles ein. Wenn man sich Amiga OS 3.2 kauft, erhält man eine CD mit allen ADF Dateien, den aktuellen Kickroms etc. pp. mit voller Lizenz, die man hier dann benutzen darf. Ansonsten gilt: all die Amiga Software steht noch unter Lizenzschutz.
- **fs-uae**: können wir außer acht lassen
- **kickstart**: hier kommen die *.rom Abbilder der Kickstarts hinein. Dies ist zwingend erforderlich, damit WHDLoad später funktioniert. WHDLoad emuliert ja den zu Grunde liegenden AMIGA, viele Spiele sind für den Amiga 500 programmiert. Es gibt von jedem Amiga ein entsprechendes Kickstart-ROM File, nötig sind das Kickrom 1.3 vom AMIGA 500 und das 3.X vom Amiga 1200. Das ist jedoch kein muss, wenn WHDLoad keine Rolle spielt.
- **userpackages**: Hier finden wir die mit HSTWB mitgelieferten Software-Pakete. Hier findet sich beispielsweise das berühmte SYSInfo, die Better oder BestWB, WHDLoad usw. usf..; grundsätzlich muss hier nichts konfiguriert werden, die Ausnahme jedoch bildet WHDLoad. Hier sollten wir unsere WHDLoad Spiele hinein kopieren. Diese können unter [whdload.de](http://whdload.de/) herunter geladen werden. Jedoch nur die Installer, die Spieldateien selbst stehen unter einem Copyright der Hersteller.

![](__GHOST_URL__/content/images/2022/09/Bildschirmfoto-2022-09-18-um-16.40.26.png)So sieht das bei mir aus: ich habe die Ordner mit den entsprechenden Dateien befüllt.
### WHDLoad

Zunächst brauchen wir die WHDLoad Titel. Diese können wir uns bei WHDLoad [herunter laden](http://whdload.de/games/all.html) (hier gibt es z.B. [Stunts](http://whdload.de/games/4DSportsDriving.html) oder [Prince of Persia](http://whdload.de/games/PrinceOfPersia.html)). Vorsicht, ich glaube auf all die Spiele liegt noch ein Copyright, oder häufig, d.h. wenn man sich nicht im Besitz der Originaldisketten befindet, darf man sich diese auch nicht digital aneignen. 

Unter **userpackages** --> **WHDLoad Packs** --> **EAB WHDLoad Games**
![](__GHOST_URL__/content/images/2022/09/whdload_struktur.png)
legen wir uns eine Ordnerstruktur A B C ... Z und  0 1 2 ... 9 an. Dann kopieren wir die jeweiligen *.lha gepackten Spieleabbilder unserer Originalversionen in dne zugehlörigen Ordner, also Prince of Persia in P und Stunts (weil es 4d Sports Driving heißt) in 4. 

Das HSTWB-Script welches wir für WHDLoad später laufen lassen erkennt alle Spiele in allen Ordnern und bereitet diese so vor, dass sie später in WinUAE oder FS-UAE automatisch entpackent und an die richtigen Stellen auf der CF-Card nebst dem korrekten Kickrom kopiert werden. Mega gut. Mega Service. Na klar geht das alles auch per Hand, aber wenn man 1000 Spiele besitzt und man öfter mal ein neues CF-Image anlegt weil man gern mal was probiert, dann ist das schon sehr viel Arbeit die da abgenommen wird. 

### BetterWB 4.3

So sieht Better WB aus.
![](__GHOST_URL__/content/images/2024/01/betterwb.png)BetterWB 4.3 Workbench mit diversen Tools und Erweiterungen, aber nicht sonderlich farblich oder eyecandy
### BestWB

So sieht BestWB aus. Am Ende spielt all der fancy Grafiklook keine Rolle, weniger ist immer schneller.
![BestWB Workbench mit Amiga OS 3.2](__GHOST_URL__/content/images/2024/01/bestwb_3.2_4.png)BestWB Workbench mit Amiga OS 3.2
### Amiga OS 3.9

AmigaOS 3.9 ist dazu im Gegensatz nahezu modern und sehr hübsch.
![Amiga OS 3.9 auf Amiga 1200](__GHOST_URL__/content/images/2024/01/amigaos_3_9_screenshot_by_amiga1200_dany5e-fullview.jpg)Amiga OS 3.9 auf Amiga 1200
Ich persönlich entscheide mich für das neue [Amiga OS 3.2](__GHOST_URL__/hallo-amiga-os-3-2/) und lasse dies automatisch durch **HSTWB** installieren, nutze auch WHDLoad und installiere diverse zusätzliche Tools. 
![Amiga OS 3.2.1 Kickrons und Installationsdiskette](__GHOST_URL__/content/images/2024/01/IMG_7280.jpg)Amiga OS 3.2.1 Kickroms und Installationsdiskette
## Let the scripts do their magic

### WHDLoad

Ich habe fest gestellt, dass Windows mit seinem Command.com Probleme hat, wenn die Ordnernamen zu lang sind oder Sonderzeichen beinhalten. Also habe ich meinen HSTWB Ordner einfach direkt auf C:\ kopiert. Dann lauf auch die Scripte. Ich wechsle also im Ordner in den Unterordner 

**userpackages** --> **WHDLoad Packs** --> **EAB WHDLoad Games**

und klicke dort doppelt auf die Datei **build_install_entries**
![](__GHOST_URL__/content/images/2024/01/hswtb.png)Builtscript für WHDLoad
Die Commandozeile geht auf und das sieht ungefähr so aus. Das Script hat 872 Demos und 3685 Spiele gefunden und diese konfiguriert.

    C:\16gb_hstwb_1.6.3\userpackages\WHDLoad Packs>powershell -ExecutionPolicy Bypass -File build_install_entries.ps1 -userPackagesDir "."                                                                                                          ---------------------                                                                                                   Build Install Entries                                                                                                   ---------------------                                                                                                   Author: Henrik Noerfjand Stengaard
    Date: 2021-12-02
    
    User packages directory: 'C:\16gb_hstwb_1.6.3\userpackages\WHDLoad Packs'
    
    Building install scripts for user package directories:
    EAB WHDLoad Demos
    - Finding entries...
    - Found 872 entries.
    - Building install entries...
    - Done.
    EAB WHDLoad Games
    - Finding entries...
    - Found 3685 entries.
    - Building install entries...
    - Done.

WHDLoad Script

### Hauptscript

Wir verlassen die Unterordner und wechseln in unseren Hauptordner, bei mir C:\16gb_hstwb_1.6.3 denn dort befindet sich das Hauptscript, welches die Ergebnisse der Unterschritte (bei mir WHDLoad) zusammen baut und in die Konfigurationsdatei schreibt.
![](__GHOST_URL__/content/images/2024/01/Bildschirmfoto-2024-01-25-um-11.21.51.png)
Wir befinden uns im Hauptordner und und klicken doppelt auf die** Install_Image_Setup**, es sollte ungefähr folgendeAusgabe entstehen, die Fehler stören nicht sonderlich:

    -----------------
    HstWB Image Setup
    -----------------                                                                                                       Author: Henrik Noerfjand Stengaard                                                                                      Date: 2021-12-30                                                                                                                                                                                                                                Install dir 'C:\16gb_hstwb_1.6.3'
    2 UAE configuration file(s)
    2 FS-UAE configuration file(s)
    One or more configuration files contain self install dirs
    Test-Path : Zugriff verweigert
    In C:\16gb_hstwb_1.6.3\hstwb_image_setup.ps1:89 Zeichen:11
    +     if (!(Test-Path $dir))
    +           ~~~~~~~~~~~~~~
        + CategoryInfo          : PermissionDenied: (X:\:String) [Test-Path], UnauthorizedAccessException
        + FullyQualifiedErrorId : ItemExistsUnauthorizedAccessError,Microsoft.PowerShell.Commands.TestPathCommand
    
    Amiga OS dir 'C:\16gb_hstwb_1.6.3\amigaos'
    Kickstart dir 'C:\16gb_hstwb_1.6.3\kickstart'
    User packages dir 'C:\16gb_hstwb_1.6.3\userpackages'
    
    Image directories
    -----------------
    Detecting Amiga OS...
    - Amiga OS dir 'C:\16gb_hstwb_1.6.3\amigaos'
    - 3 Amiga OS 3.9 files detected 'amigaos3.9.iso, boingbag39-1.lha, boingbag39-2.lha'
    - 34 Amiga OS 3.2 adf files detected 'Backdrops3.2.adf, Classes3.2.adf, DiskDoctor.adf, Extras3.2.adf, Fonts.adf, GlowIcons3.2.adf, Install3.2.adf, Locale.adf, Locale-DE.adf, Locale-DK.adf, Locale-EN.adf, Locale-ES.adf, Locale-FR.adf, Locale-GR.adf, Locale-IT.adf, Locale-NL.adf, Locale-NO.adf, Locale-PL.adf, Locale-PT.adf, Locale-RU.adf, Locale-SE.adf, Locale-TR.adf, Locale-UK.adf, MMULibs.adf, ModulesA1200_3.2.adf, ModulesA2000_3.2.adf, ModulesA3000_3.2.adf, ModulesA4000D_3.2.adf, ModulesA4000T_3.2.adf, ModulesA500_3.2.adf, ModulesA600_3.2.adf, ModulesCD32_3.2.adf, Storage3.2.adf, Workbench3.2.adf'
    - No Amiga OS 3.1.4 adf files detected
    - No Amiga OS 3.1 adf files detected
    Detecting Kickstart roms...
    - Kickstart dir 'C:\16gb_hstwb_1.6.3\kickstart'
    Es ist nicht möglich, eine Methode für einen Ausdruck aufzurufen, der den NULL hat.
    In C:\16gb_hstwb_1.6.3\hstwb_image_setup.ps1:51 Zeichen:9
    +         $md5Files.Add(@{
    +         ~~~~~~~~~~~~~~~~
        + CategoryInfo          : InvalidOperation: (:) [], RuntimeException
        + FullyQualifiedErrorId : InvokeMethodOnNull
    
    - 4 Kickstart rom files detected 'A1200.47.102.rom, amiga-os-120.rom, amiga-os-310-a1200.rom, Kickstart-v3.1-rev40.68-1993-Commodore-A1200.rom'
    Detecting User Packages...
    - User Packages dir 'C:\16gb_hstwb_1.6.3\userpackages'
    - 21 user packages detected 'Amiga Boot Selector, Amiga Test Kit v1.18, Archivers and unarchivers, CompactFlash and FAT95, DirOpus v4.12-4.17pre21, FastFileSystem v45.16, Full Palette v40.22, IconLib v46.4.555, iGame v1.6a, iGame v2.0, Kickstart roms, KingCON v1.3, Magic Menu v2.30-2.35, MMU Libs v47.1, MUI v3.8, MUI v3.8 iGame dependencies, Scsi.device v43.45, SysInfo v4.4, WBDock v2.560, WHDLoad Packs, WHDLoad v18.7'
    Done
    
    UAE configuration
    -----------------
    Patching and installing UAE configuration files...
    - UAE config dir 'C:\Users\Public\Documents\Amiga Files\WinUAE\Configurations\'
    - Using Amiga OS 3.9 iso file 'C:\16gb_hstwb_1.6.3\amigaos\amiga-os-3.9\AmigaOS3.9.iso'
    - 2 UAE configuration files
    - 'C:\16gb_hstwb_1.6.3\hstwb-installer_a1200.uae'. Using Kickstart file 'C:\16gb_hstwb_1.6.3\kickstart\A1200.47.102.rom' for A1200 model
    - 'C:\16gb_hstwb_1.6.3\hstwb-installer_a500.uae'. No Kickstart file for A500 model!
    Done
    
    FS-UAE configuration
    --------------------
    Patching and installing FS-UAE configuration files...
    - FS-UAE config dir '\\Mac\Home\Documents\FS-UAE\Configurations'
    - Using Amiga OS 3.9 iso file 'C:\16gb_hstwb_1.6.3\amigaos\amiga-os-3.9\AmigaOS3.9.iso'
    - 2 FS-UAE configuration files
    - 'C:\16gb_hstwb_1.6.3\hstwb-installer_a1200.fs-uae'. Using Kickstart file 'C:\16gb_hstwb_1.6.3\kickstart\A1200.47.102.rom' for A1200 model
    - 'C:\16gb_hstwb_1.6.3\hstwb-installer_a500.fs-uae'. No Kickstart file for A500 model!
    - HstWB Installer FS-UAE theme installed
    Done

Wenn man das durchgeht sieht man, dass ich keine Amiga 500 Kickstart Datei kopiert habe, ansonsten sieht es ganz gut aus und wir können die Konfigurations-Datei **hstwb-installer_a1200** in unser WinUAE laden.

## Konfiguriere und installiere Image mit WinUAE

Ich nutze in meinem Beispiel WinUAE in einer VM auf meinem Mac, weil das irgendwie gut funktioniert. Es gibt andere Emulatoren und andere Betriebssysteme, aber das ist meine Konfiguration.
![Logo WinUAE](__GHOST_URL__/content/images/2024/01/winuea_v10.png)Logo WinUAE
Es ist ganz einfach: Ihr zieht die Datei  **hstwb-installer_a1200** auf euer WinUAE Piktogramm, die Maschine startet, lädt die Konfiguration und nutzt unser 16 GB Image als Festplatte. Der Installer startet und fragt euch nach folgenden Dingen, in Amiga OS.

Die Konfiguration von HSTWB habe ich in einen [gesonderten Artikel](__GHOST_URL__/hstwb-installer-unter-winuae/) ausgelagert, da dieser sonst zu groß und lang werden würde. Für eine bebilderte Anleitung klickt ihr bitte hier, Teil 2 unserer HSTWB Reihe.
[

HSTWB Installer unter WinUAE

In diesem Artikel beschreibe ich den Weg, wie man den HSTWB Installer konfigurieren muss und was die einzelnen Einstellungsmöglichkeiten bedeuten, damit wir am Ende ein lauffähiges Amiga OS auf unserem 16 GB Image vorfinden, welches wir dann auf die CF-Karte übertragen können, um es in den echten Amiga einzusetzen. Table

![](__GHOST_URL__/content/images/size/w256h256/2019/06/logo.png)thahipster.deHerr Montag

![](https://images.unsplash.com/photo-1606422699425-f7122890005f?crop=entropy&amp;cs=tinysrgb&amp;fit=max&amp;fm=jpg&amp;ixid=M3wxMTc3M3wwfDF8c2VhcmNofDh8fHJldHJvJTIwZ2FtZXN8ZW58MHx8fHwxNzA2MjY0Njk4fDA&amp;ixlib=rb-4.0.3&amp;q=80&amp;w=2000)
](__GHOST_URL__/hstwb-installer-unter-winuae/)
Walkthrough HSTWB WinUAE Setup

Wenn wir hier durch sind - und das dauert unendlich lange - sollten wir einen virtuellen Amiga 1200 (bei mir) mit 16 GB Diskimage vorfinden, den wir über die Konfigurationsdatei auch immer wieder starten und bearbeiten können. Dieses Image schreiben wir jetzt im nächsten Schritt auf die CF-Card um sie dann im echten Amiga nutzen zu können.

---

## Das Disk-Image auf CF-Card schreiben

Der letzte und wichtigste Schritt nachdem wir unser Image erstellt und in WinUAE ausgiebig getestet haben ist es, das Image nun auf die CF-Karte zu übertragen. Jedoch ist das Dateiformat unbekannt und Windows-Image-Software versagt manchmal ihren Dienst. Wenn ihr wie ich auf MacOS oder Linux unterwegs seid, dann habt ihr alles an Board um das durchzuführen. Ich zeige Schritt für Schritt, wie das geht:

### Der Befehl zum Schreiben des Images auf die CF-Karte

💡

Solltet ihr euch hierbei vertun und nicht auf die CF-Karte sondern eure Festplatte schreiben, dann sind ALLE Daten weg. Ich wiederhole: passiert euch hier ein Fehler verliert ihr alles. Ich kann dafür leider keine Verantwortung übernehmen, ihr tut dies also auf eigene Gefahr hin.

Und jetzt aber los:

Unter macOS könnt ihr mit dem Befehl diskutil heraus finden, welche disk eure CF-Card ist. Meine 16 GB CF-Card ist disk7 und ich befinde mich im Ordner des Diskimages 16gb.hdf, welches ich auf die CF schreiben möchte.

`sudo dd if=16gb.hdf of=/dev/disk7 status=progress`

Zur Erklärung:

- dd ist der Befehl
- sudo bedeutet, wir tun dies als Root, Admin
- if = input file also unser Image
- of = output file also unsere CF-Karte
- status = damit wir sehen wie lange er noch braucht. Ne Stunde kann das dauern.

**Das wars, ihr könnt nun die erstellte CF-Carde in euren Amiga einsetzen und einschalten, er sollte Workbench 3.2 mit WHDLoad und etwas starten.**
