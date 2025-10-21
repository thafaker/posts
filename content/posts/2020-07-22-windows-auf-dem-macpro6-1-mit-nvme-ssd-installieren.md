---
title: Windows auf dem MacPro6,1 mit NVMe SSD installieren
slug: windows-auf-dem-macpro6-1-mit-nvme-ssd-installieren
date_published: 2020-07-21T23:13:00.000Z
date_updated: 2020-08-03T17:07:39.000Z
tags: anleitung, howto, how to, windows 10, macpro6,1, trashcan, nvme ssd
excerpt: In diesem Artikel beschreiben wir die Installation von Windows 10 auf einem MacPro oder MacBook Pro mit nachgerüsteter NVMe-SSD. Viel Spaß mit Windows.
---

Wenn man seinen MacPro / MacBook Pro mit einer neuen SSD ausrüsten möchte, funktioniert dies nur mit einem Adapter für die NVMe-SSD und eben einer NVMe-SSD. Standardmäßig haben die Macs nur geringe SSD-Kapazitäten mit 128 GB oder 256 GB, eigentlich viel zu wenig, insbesondere wenn man neben macOS auch Windows (oder Linux) über Bootcamp installieren möchte. Seit etwa zwei Jahren sind dank speziellen Adaptern die oben erwähnten klassischen NVMe SSD Module nutzbar, die viel günstiger als Apples eigene Module sind. Ich habe mich für den **QNINE Adapter** (ca. 15 €) und eine **Sabrent Rockent 1 TB SDD** (ca. 119 €) entschieden. Das sollte genügend Platz für *macOS***und***Windows* bieten. Leider gibt es bei der Installation von Windows ein paar Schwierigkeiten, denn aufgrund der NVMe-SSD funktioniert Bootcamp nicht mehr. Wie man **Windows 1o** dennoch installieren kann, beschreibe ich in diesem Artikel.
![SINTECH NVMe SSD Adapter. Bild: Sintech.](https://maxwireless.de/wp-content/uploads/2019/04/SINTECH-NVMe-SSD-Adapter-540x406.jpg)SINTECH NVMe SSD Adapter. Bild: Sintech.
****Windows auf dem **MacPro6,1**: Bootcamp mit Fehler****

[**UPDATE**] Bei einem neuerlichen Versuch mit Bootcamp unter macOS 10.15 Catalina lief das Setup problemlos durch. Bootcamp brach nicht mit einem Fehler ab und die Installation funktionierte genau so, wie von Apple vorgesehen. Scheinbar ist die Problematik, die in diesem Artikel beschrieben wird, nun behoben.

---

[**ORIGINAL**] Wenn die NVMe SSD eingebaut ([[hier](__GHOST_URL__/upgrading-to-nvme-ssd-in-macpro2013-aka-macpro6-1-trashcan/)](__GHOST_URL__/ultimate-upgrade-guide-macpro6-1-aka-trashcan-2013/#6-festplatten-ssd-upgrade)[beschrieben](__GHOST_URL__/upgrading-to-nvme-ssd-in-macpro2013-aka-macpro6-1-trashcan/)) und MacOS installiert ist, dann habt ihr schon mal gute Voraussetzungen für die weiteren Schritte. Nun benötigt ihr eine Windows ISO Installationsdatei, welche ihr ganz legal bei [Microsoft herunter](https://www.microsoft.com/de-de/software-download/windows10ISO) laden könnt, Microsoft bietet sein Windows nämlich immer als Testversion an. 

Das kleine Hilfsprogramm „Bootcamp“ ist bereits auf dem Mac vorinstalliert und unterstützt den Benutzer im Normalfall bei der problemlosen Windows-Installation. Leider geht das mit NVMe SSDs nicht reibungslos, wie oben zuvor erwähnt, die Installation wird im Prozess abgebrochen. Dennoch nutzt ihr das Tool, um die Windows-Partition auf der SSD zu erstellen. Dazu wählt ihr das von Microsoft herunter geladene ISO Image im Bootcamp-Menü aus. (Wichtig ist auch, dass ihr sämtliche per USB oder Thunderbolt angeschlossene externe Peripherie abzieht. Das muss leider sein, sonst spielt Bootcamp gar nicht erst mit.) 
![](__GHOST_URL__/content/images/2020/08/Bildschirmfoto-2020-08-02-um-14.23.43.png)
Nach kurzer Zeit wird die Installation von Bootcamp abgebrochen. Ihr könnt Bootcamp nun schließen.

---

**Bootcamp** hat zwei neue Partitionen erstellt. Eine mit etwa 8 GB Größe (FAT Dateiformat) und eine mit eurer individuell festgelegten Größe. Nun öffnet ihr das *Festplattendienstprogramm* in macOS und löscht die 8 GB große FAT Partition. Das neue Dateiformat dieser Partition soll exFAT sein. Ist der Vorgang abgeschlossen, so muss die Partition neu ins System eingebunden werden („aktivieren“ klicken).
![8 GB exFAT Partition auf der SSD.](https://maxwireless.de/wp-content/uploads/2019/04/NVMe-exFAT-Partition-659x406.png)8 GB exFAT Partition auf der SSD.
****Windows installieren****

Ihr habt mit der 8 GB großen Partition nun eine Art USB-Stick auf der SSD, um es mal bildlich zu beschreiben. Hier kopiert ihr nun die Inhalte der Windows ISO rein. Dazu öffnet ihr die ISO Datei mit dem Finder in macOS und kopiert den kompletten Inhalt in die 8 GB große Partition, welche wir vorhin in exFAT formatiert haben. Sollte das ISO File nicht geöffnet werden können, so müsst ihr es ggfs. vorher „auswerfen“, wenn es von Bootcamp noch „gemountet“ sein sollte.

Ihr könnt den Mac nun neu starten. Direkt beim Start die „alt“ Taste gedrückt halten und „Windows“ auswählen. Windows wird nun ganz normal installiert. Nach dem ersten Neustart Shift+F10 auswählen und *„regedit“* eintippen. Im Menü sucht ihr dann nach folgender Datei:

*„HKEY_LOCAL_MACHINE\SYSTEM\Setup\Status\ChildCompletion“*

Den Wert der exe Datei setzt ihr dann von 1 auf 3 (durch Doppelklick auf den Dateinamen kann man den Wert ändern). Nach einem Neustart wird Windows dann ganz normal weiter konfiguriert und ihr könnt euch nach einiger Wartezeit das System nach euren wünschen einrichten. Eine kleine Anpassung muss man jedoch noch vornehmen.

****Energiespar-Einstellungen anpassen****

Damit es keine Probleme mit dem Energiesparmodus gibt, muss noch folgende Einstellung vorgenommen werden. Ihr klickt in Windows 10 auf: *Einstellungen, System, Netzbetrieb und Energiesparen,  Zusätzliche Energieeinstellungen, Energiesparplaneinstellungen ändern, erweiterte Energieeinstellungen ändern, PCI Express. *Hier muss nun sowohl bei Netzbetrieb als auch bei Akku „Mittel“ eingestellt werden. Das wars auch schon!

****Apple Treiber installieren****

Ihr startet nun noch einmal Mac OS und dort dann Bootcamp. Nun könnt ihr oben über die Menüleiste die Windows Support Dateien herunterladen. Als Speicherort bietet sich zum Beispiel die 8 GB große exFAT Partition an, die ihr ja für die Windows-Installationsdateien erstellt habt. Die könnt ihr vor dem Speichern der Support-Daten löschen, da ihr Windows ja eh erfolgreich installiert habt.
![Installation der Windows Supportdaten via Bootcamp.](https://maxwireless.de/wp-content/uploads/2019/04/Bootcamp-Windows-NVMe-SSD-Supportsoftware-610x406.png)Installation der Windows Supportdaten via Bootcamp.
In Windows kann man dann das Bootcamp Installationsprogramm aufrufen und die Treiber für die Macbook Hardware installieren.

*Das wars auch schon wieder, bis bald.*

---

### Fragen und Antworten:

- [Jans Ultimate Upgrade Guide to Trashcan MacPro6,1 2013](__GHOST_URL__/ultimate-upgrade-guide-macpro6-1-aka-trashcan-2013/)
- [Windows 10 auf MacPro6,1 mit NVMe SSD installieren](__GHOST_URL__/windows-auf-dem-macpro6-1-mit-nvme-ssd-installieren/)
