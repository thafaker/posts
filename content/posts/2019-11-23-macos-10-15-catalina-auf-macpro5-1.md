---
title: macOS 10.15 Catalina nativ auf MacPro5,1 - OpenCore
slug: macos-10-15-catalina-auf-macpro5-1
date_published: 2019-11-23T04:43:29.000Z
date_updated: 2020-12-31T09:13:37.000Z
tags: howto, anleitung, cMP, bigmac, macOS 10.15 Catalina, OpenCore, native, nativ, OpenCore on the Mac Pro, catalina
---

Wie Sie alle wissen, werte Leserinnen und Leser, besitze ich diesen wunderschönen **MacPro** samt **CinemaHD****Display** in 30", welches ich vor allem in Kombination auch heute noch unendlich schick finde und tatsächlich sehr gern benutze. Ich vermisse an diesem MacPro nichts, Thunderbolt hat mich nämlich nie wirklich interessiert und alles andere kann ich nachrüsten, wie ich unter diesem [Link](__GHOST_URL__/tag/bigmac/) ausführlich beschrieben habe.
![Apple CinemaHD 30&quot; Display](__GHOST_URL__/content/images/2019/11/cinema.jpg)Apple CinemaHD 30" Display
Lesen und benutzen Sie diesen Artikel auf eigene Gefahr

Um so schlimmer wiegt es, dass Apple mit dem aktuellen Betriebssystem, macOS 10.15 Catalina, den MacPro5,1 einfach aus der unterstützten Hardware heraus geschrieben hat. Denn während der BETA war ganz klar zu sehen: der MacPro kann das absolut problemlos. Jeder Mac der 10.14 kann, kann auch 10.15 - außer der MacPro5,1, weil Apple das nicht gefällt. Apple hat nämlich zwischenzeitlich einen [richtigen Nachfolger, eine neue Käsereibe](__GHOST_URL__/macpro7-1-die-neue-kasereibe/), herausgebracht. Da braucht es die Alte nicht mehr. Sehr zu meinem *Leidwesen*.
![](__GHOST_URL__/content/images/2019/11/cinema2.jpg)Furchtbares Foto: Mein MacPro5,1 mit CinemaHD Display 30"
Wenn man des *DosDudes Anleitung* ([Link](__GHOST_URL__/how-to-install-calatina-on-unsupported-hardware/)) folgt, dann wird man sofort feststellen: auch jetzt noch, in der finalen Version, läuft das neue macOS 10.15. auf dem MacPro. Leider aber ist bei jedem Update eine komplette Neuinstallation nötig, weil man nicht updaten kann. Apple baut hier quasi zwei Sperren ein - und so bietet der Updateserver einfach nichts an. Auch wenn man sich das große Comboupdate direkt von Apple lädt, quittiert der Installer auf *unsupported* Hardware den Dienst.

Und das ist natürlich keine gute Lösung, keine produktive und überhaupt: Abhilfe muss her. Aber wie? Nun… Apple erlaubt es, die Update-Sperre zu umgehen wenn das macOS feststellt, dass es in einer VM betrieben wird. Denn ein virtualisiertes System hat auch keinen realen Mac als Unterbau. Und muss trotzdem aktualisiert werden können. Wenn man macOS mit VMWare betreibt zum Beispiel. Und genau hier kann man ansetzen.

Man muss auf seinem MacPro5,1 also dem Betriebssystem 10.15 signalisieren, dass es a) auf einer VM läuft oder b) auf einem adäquaten anderen Mac neueren Datums, der nicht ausscheidet. Aber wie will man das anstellen? 

Mit **OpenCore**.

# **OpenCore on the Mac Pro 1,1 - 5,1**

==Vorsicht, OpenCore erfordert ein beherztes Hacken des Rechners==

Für Schäden an ihrem Gerät kann niemand, niemand außer Sie selbst aufkommen.

Dieser Artikel zeigt auf, wie man den großartigen [OpenCore](https://github.com/acidanthera/OpenCorePkg) (OC) Bootloader auf einem Mac Pro 5,1 installiert und laufen lässt, sodass man am Ende sein macOS Catalina benutzen kann wie ein normal installiertes System auf einem unterstützten Mac, also als ungepatchte Normalversion.

#### 1. Setup

- Festplatte 1: Mit APFS-formatierte Festplatte (GUID scheme)
- 	Auf dieses Drive kommen OC und die frische Installation von Catalina
- Festplatte 2: mit macOS 10.14 Mojave
- 	Die Installation und Konfiguration wird von hier aus erledigt.

#### 2. Utilities

Ihr benötigt:

- den vollen Installer von mac OS Catalina aus dem App-Store. Ladet ihn euch am Besten mit [DosDudes Tool](http://dosdude1.com/catalina/), ohne dass ihr das installiert, nur den Installer (8 GB) laden.
- OpenCore (OC) selbst. Schaut auf die [releases](https://github.com/acidanthera/OpenCorePkg/releases) Seite. Laded (aktuell) OpenCore-0.5.2-RELEASE.zip. Das ganze entpacken. Benennt den entpacken Ordner in OpenCore um.
- Support-Files. Schaut auf die [releases](https://github.com/acidanthera/AppleSupportPkg/releases) Seite. Ladet euch AppleSupport-2.1.2-RELEASE.zip, entpackt es. Benennt den entpackten Ordner in AppleSupport um.

![](__GHOST_URL__/content/images/2019/11/Bildschirmfoto-2019-11-22-um-20.28.11.png)OpenCore und AppleSupport entpackt.
- Die Konfiguration: Ladet die config.zip und entpackt sie, die Datei "config.plist" sollte extrahiert werden. [Download](http://thafaker.crabdance.com/grav/stuff/config.zip)! 
- [alternativer Download für die config.plist](http://thafaker.crabdance.com/nextcloud/index.php/s/jPa9E4wKMy6LK5n)

Das wars zunächst an Vorbereitungen, es geht los, wir installieren Open Core auf die zuvor erstellte, leere Festplatte 1.

#### 3. OpenCore installieren

1) Mounted die EFI-Partition von Festplatte 1, schaut mit 

    diskutil list

im Terminal zuerst nach wie sie heißt. Mounting geht mit 

    sudo diskutil mount /dev/disk0s1

Wobei *disk0s1* auch anders lauten kann. Durch sudo müsst ihr euer Passwort angeben. Die Partition sollte unter /Volumes/EFI gemounted werden und im Finder als "EFI" auftauchen. Sehr gut.

2) Kopiert den OpenCore/EFI Ordner auf die EFI Partition. Der neue Ordner /Volumes/EFI/EFI sollte die Ordner OC und Boot beinhalten.

3) Kopiert AppleSupport/Drivers/FwRuntimeServices.efi nach /Volumes/EFI/EFI/OC/Drivers

4) Kopiert die entpackte config.plist nach /Volumes/EFI/EFI/OC.

#### 4. Konfiguration

1) wir müssen die config.plist Datei editieren. Dazu nutzen wir einfach irgendeinen Editor, es tut auch TextEdit.app. Öffnet also die Datei in einem Texteditor.

2) Aktiviert das VMM flag: Findet dazu den Cpuid1Mask Eintrag und ändert den Wert von: `AAAAAAAAAAAAAAAAAAAAAA==` zu `AAAAAAAAAAAAAACAAAAAAA==`. Wichtig ist das C im zweiten Eintrag. Der Werte sollte nun der gleiche wie in **Cpuid1Data** sein. Das ist keine Verarsche, aber so sagen wir dem EFI, dass es in einer VM sitzt.

3) Aktiviert die "boot entry preservation": sucht dazu den Eintrag `RequestBootVarRouting` und ändert von `false` auf `true`.

4) Speichert und schließt die Datei.

#### 5. Booting

1) Rebootet das System in den Recovery-Mode indem ihr folgendes eingebt

    sudo nvram "recovery-boot-mode=unused" && sudo reboot recovery

Ihr müsst aufgrund des SUDO wahrscheinlich wieder euer Passwort eingeben. Bleibt geduldig, die MacPro-Boot-Zeiten können lange dauern, vor allem wenn er in den Recovery Mode startet. Bei einer unterstützten Grafikkarte seht ihr das, wenn ihr keine habt, dann bleibt der Bildschirm erst mal schwarz.

2) Führt im Recovery-Modus Schritt 3) 1. aus. Also das Mounten der EFI-Partition,  wie vorhin, siehe oben.

3) Stellt die Boot-Partition ein:

    bless --mount /Volumes/EFI --setBoot

4) Schaltet den Mac nun aus und führt einen SMC-Reset aus. (Stromkabel heraus ziehen, 15 Sekunden warten, das Stromkabel wieder anschließen, 5 Sekunden warten und dann wieder den Einschaltknopf drücken).

5) Die Maschine starten. OC sollte nun aktiv sein und Festplatte 2 booten, da es die einzige Platte mit einem System ist, wir haben 10.15. ja noch nicht auf Festplatte 1 installiert, nur den Bootloader bearbeitet.

(Seid wiederum geduldsam, der Boot kann ziemlich lange dauern. Wenn die Maschine wirklich hängt, dann haltet den Einschaltknopf gedrückt. Führt dann einen NVRAM Reset durch indem ihr nach dem Wiedereinschalten  `Command + P + R` gleichzeitig gedrückt haltet und nach 20 Sekunden wieder los lasst. Der Mac sollte jetzt ohne OpenCore booten. Geht alle Schritte noch mal durch, irgendwo lag ein Fehler.)

6) Wenn das System von Festplatte 2 gebootet ist, prüft bitte, dass es auch wirklich durch den OpenCore gestartet wurde, indem ihr folgendes im Terminal eingebt:

    nvram 4D1FDA02-38C7-4A6A-9CC6-4BCCA8B30102:opencore-version

Es sollte `REL-052-2019-10-30` ausgegeben werden. Wenn das so ist, dann habt ihr den schwierigsten Teil schon geschafft. 

    Jans-Big-Mac:~ thahipster$ nvram 4D1FDA02-38C7-4A6A-9CC6-4BCCA8B30102:opencore-version
        4D1FDA02-38C7-4A6A-9CC6-4BCCA8B30102:opencore-version	
        REL-052-2019-10-30

Folgende Antwort auf meinem MacPro
Er zeigt mir in dem Systemeinstellungen nun auch sofort mit einer roten 1 an, dass ein Update zur Verfügung steht, nämlich das Update von 10.14. auf 10.15, das hat also geklappt:
![](__GHOST_URL__/content/images/2019/11/Bildschirmfoto-2019-11-23-um-09.34.43.png)
Schaue ich nach, meldet sich macOS 10.15. Catalina und möchte installiert werden.
![Softwareupdate zeigt mir an, dass Catalina 10.15.1 zur Verfügung steht.](__GHOST_URL__/content/images/2019/11/Bildschirmfoto-2019-11-23-um-09.34.05.png)Softwareupdate zeigt mir an, dass Catalina 10.15.1 zur Verfügung steht.
Zeit also, *Catalina* tatsächlich zu installieren. Allerdings mit dem herunter geladenen vollen Installer und nicht per Software-Update. Ich will es ja als zweites System, ich will mein 10.14. nicht kaputt machen.

#### 6. Catalina installieren

1) Wir können also direkt weiter machen und starten den Catalina Installer, den wir unter 2. herunter geladen haben, um ihn auf Festplatte 1 zu installieren. Die Maschine sollte während des Setups neu starten, ihr seht wahrscheinlich den Install-Fortschritt.
![macOS 10.15 Catalina wird auf meinem MacPro5,1 installiert. Ohne Patches.](__GHOST_URL__/content/images/2019/11/Bildschirmfoto-2019-11-23-um-09.38.36.png)macOS 10.15 Catalina wird auf meinem MacPro5,1 installiert. Ohne Patches.
2) Beendet die Installation.

Von nun an sollte OpenCore automatisch Festplatte 1, also macOS 10.15 Catalina, starten. Auf jeden Fall wird OC immer auch den Startup-Disk Selektor beachten.

Das hat funktioniert, mein MacPro hat nun ein Catalina. Ich habe extra noch den alten Installer verwendet, also den mit 10.15.0, und direkt nach der Installation hat er mir ordnungsgemäß angezeigt, dass 10.15.1 zur Verfügung steht und installiert werden kann, die Update-Funktion läuft also auch tadellos.
![Updatehinweis MacPro5,1 Catalina 10.15.1](__GHOST_URL__/content/images/2019/11/catalina_15.15.1.png)Updatehinweis MacPro5,1 Catalina 10.15.1
#### 7. Updates

Solange die `VMM Flag` gesetzt ist, sollte das Software Update ganz normal funktionieren.

#### 8. Nach der Installation

Um das System so natürlich wie möglich zu machen, ist es eine gute Idee den VMM-Flag wieder zu deaktivieren, siehe Schritt 4) 2. Zumindest so lange bis man weiß was passiert, wenn man den VMM-Flag (virtuelle Maschine) auf nicht virtueller Hardware gesetzt hat. Für Updates muss das ganze wieder aktiviert werden. Folgt einfach immer dem Schritt die EFI Partition zu mounten, dass Flag mit einem Texteditor zu setzen oder zu deaktivieren, fertig.

#### 9. Disabling OC

a) Carry out step 3) 1.

b) Open config.plist with TextEdit.

c) Reverse step 4) 2.

d) Reboot.

e) Select the desired entry in Startup Disk.

f) Reboot.

#### 10. Disabling OC

a) Carry out step 3a.

b) Open config.plist with TextEdit.

c) Reverse step 4c.

d) Reboot.

e) Select the desired entry in Startup Disk.

f) Reboot.

It is also possible to boot Catalina natively, after using recovery to add the "-no_compat_check" boot argument. In this case replace step c above by 5a. In recovery, enter
Code:

    nvram boot-args="-no_compat_check"

and then carry out steps d and e in recovery. Catalina should boot without OC.

Failure to add the "-no_compat_check" boot argument may result in the machine suddenly shutting down when booting into Catalina. Although OC adds this argument, booting without OC does not guarantee that the argument will be there, unless it is added as described above.

#### 11. Uninstalling OC

a) Disable OC (see 10).

b) Carry out step 3a.

c) Delete the /Volumes/EFI/EFI folder.

Das wars auch schon wieder. Viel Spaß mit eurem MacPro5,1 und nativem Catalina Support. Ihr seid super.
