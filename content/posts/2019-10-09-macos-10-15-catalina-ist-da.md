---
title: macOS 10.15 Catalina ist da
slug: macos-10-15-catalina-ist-da
date_published: 2019-10-09T15:25:13.000Z
date_updated: 2019-10-09T16:19:40.000Z
tags: macOS 10.15 Catalina, catalina, macos 10.15
---

Ich installiere auf meinem uralten [Vintage PC](__GHOST_URL__/tag/retro-computing/) (der mit [DOS 6.22 und OS/2](__GHOST_URL__/vintage-pc-mit-dos-6-22-und-windows-3-11-und-os-2-warp/)) gerade ein textbasiertes *Ubuntu 10.04 LTS*, weil es das aktuellste noch unterstützende System dieser Hardware ist, und da veröffentlich *Apple* plötzlich **macOS Catalina**. Zufälle gibts :-)
![](__GHOST_URL__/content/images/2019/10/macos-catalina-b-768x453.jpg)
## Kompatibilität prüfen

Wenn Sie einen dieser Computer mit OS X Mavericks oder neuer* verwenden, können Sie macOS Catalina installieren. Der Mac benötigt außerdem mindestens 4 GB Arbeitsspeicher und 12,5 GB verfügbaren Speicherplatz bzw. bis zu 18,5 GB Speicherplatz, wenn Sie das Upgrade von OS X Yosemite oder älter durchführen.

- MacBook von 2015 oder neuer
- MacBook Air von 2012 oder neuer
- MacBook Pro von 2012 oder neuer
- Mac mini von 2012 oder neuer
- iMac von 2012 oder neuer
- iMac Pro (alle Modelle)
- Mac Pro von 2013 oder neuer

![](__GHOST_URL__/content/images/2019/10/Bildschirmfoto-2019-10-09-um-17.44.30.png)
Auf meinem **MacPro5,1** ([classic MacPro](__GHOST_URL__/tag/bigmac/) cMP) von 2009 laufen natürlich auch nativ Mavericks bis hin zu Mojave, aber mein MacPro wird nicht mehr unterstützt, die Ur-Käsereibe ist raus. Apple hat sie absichtlich ausgesperrt denn ich glaube nicht, dass es hardwareseitige Gründe gibt. Wir werden hier darüber berichten, wie sich die Hackintosh-Welt verhält und ob es einen Hack für den MacPro5,1 (2009 bis 2012) zur Installation von Catalina geben wird.

- [Macrumours Forum: Diskussion, warum Apple den Support entfernt hat.](https://forums.macrumors.com/threads/10-15-wont-support-mp5-1-anymore-support-starts-with-mp6-1.2183834/)
- [Maceumours Forum: Was braucht es, damit Catalina auf einem MacPro5,1 läuft](https://forums.macrumors.com/threads/what-you-need-to-do-to-make-catalina-work-with-macpro5-1.2183978/)

### [UPDATE] Catalina-Patcher

Der **Dosdude**, bekannt als wichtiger Mac-Hacker, programmiert schon geraume Zeit sogenannte Patcher die dafür sorgen, dass man eine neue macOS Version auf einem nicht mehr unterstützten System installieren kann. Dieser hat bereits einen Catalina-Patcher entwickelt und bietet ihn zum kostenlosen Download an. Die Hardware muss allerdings prinzipiell Catalina unterstützen, das heißt, man benötigt auf jeden Fall eine Metal-Kompatible-Grafikkarte. Wie das geht könnt ihr [hier nachlesen](__GHOST_URL__/how-to-install-calatina-on-unsupported-hardware/).

## macOS Catalina laden

Wenn Sie macOS Mojave verwenden, [holen Sie sich macOS Catalina über die Funktion "Softwareupdate"](https://support.apple.com/de-de/HT201541): Wählen Sie das Apple-Menü () > "Systemeinstellungen" aus, und klicken Sie dann auf "Softwareupdate".
![](__GHOST_URL__/content/images/2019/10/catalina.png)macOS Catalina über Apples Softwareupdate in den Systemeinstellungen
Oder verwenden Sie diesen Link, um die Seite von macOS Catalina im App Store zu öffnen: [macOS Catalina laden](https://itunes.apple.com/de/app/macos-catalina/id1466841314?ls=1&amp;mt=12). Klicken Sie dann auf die Taste "Laden" oder auf das iCloud-Download-Symbol. Auf meine MacPro klappt das Laden nicht, weder per Softwareupdate, noch von der Mac App Store Seite. Der Screenshot stammt von meinem Macbook Pro mit Touchbar, welches nativ Calatina unterstützt. Unten seht ihr den Screenshot von meinem MacPro5,1:
![](__GHOST_URL__/content/images/2019/10/calatina_not_supported.png)
# Neuerungen

### iPad-Apps kommen auf den Mac

Was Apple bereits vor einigen Versionen begonnen hat, wird weiter Realität. […] Mit Catalina öffnet sich der Mac für iPad-Software: iOS-Entwickler sind nun durch Apples "Project Catalyst" in der Lage, bestehende Apps mit geringerem Aufwand als zuvor für macOS anzupassen. Das soll eine ganze Reihe frischer Software auf den Mac bringen, erwartet wird unter anderem eine App des Kommunikationsdienstes Twitter und des Projektmanagers Jira. Wie umfangreich das Angebot und wie penibel die Umsetzung ausfällt, werden erst die kommenden Monate zeigen. […]

### iTunes ist weg

Der Moloch iTunes ist weg. Die Funktionen wurden auf fünf Apps aufgeteilt. Musik wird nun über die sogenannte *Musik-App* abgespielt. Diese bietet ähnliche (Verwaltungs)Funktionen wie dereinst iTunes.

Gekaufte Spielfilme oder TV-Serien werden nun über die iPhone-TV-App verwaltet, dies bringt neuen Macs die Funktion, erstmals 4K-Inhalte abzuspielen. Podcasts landen in der eigenständigen Podcasts-App, Hörbücher migriert Apple in die Bücher-App – auch das kennen iOS-Nutzer längst so. Die Funktionalität zum lokalen Synchronisieren und Sichern von iPhones, iPads und iPods übernimmt der Finder.

[*to be continued*]

### 32-Bit

Apple hat den Support für 32-Bit-Apps komplett eingestellt. Alle Entwickler hatten die Aufgabe, ihre aktuellen Apps die noch in 32-Bit geschrieben sind, zu updaten. Ist dies nicht geschehen, werden diese Programme unter Catalina nicht mehr funktionieren.
