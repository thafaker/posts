---
title: Wie installiere ich CentOS 6 auf meinem Server
slug: wie-installiere-ich-centos-6-auf-meinem-server
date_published: 2011-10-01T16:09:10.000Z
date_updated: 2018-08-22T09:38:28.000Z
---

Dies ist eine Schritt-für-Schritt Anleitung wie man CentOS 6 *from scratch *auf einem neuen Rechner installiert. Die Installationsart ist *minimal* was PERFEKT für einen Server ist, da wird nämlich keine GUI installiert und die Installation ist so klein wie möglich. Diese Anleitung kann genau so gut für Desktops und Notebooks verwendet werden, nur bei Schritt 18 wählt man einfach eine andere Option.

Zuerst einmal besucht ihr die Website [http://www.centos.org (archiviert)](http://web.archive.org/web/20111001221826/http://www.centos.org:80/modules/tinycontent/index.php?id=30) und ladet euch die für eure Architektur passenden ISOs herunter und brennt die auf CD / DVD (i686, x86_64 etc). Ich empfehle immer den Torrent-Download, weil der Erfahrungsgemäßg am schnellsten funktioniert und nicht so lahm wie die FTP-Server ist.

#### Wie installiert man Linux – CentOS 6 für Server & Desktops

1. Erst mal das BIOS so einstellen, dass es von CD / DVD bootet
2. CentOS 6 DVD einlegen
3. Wenn der folgende Bildschirm erscheint, **enter **bei **Install or upgrade an existing system drücken.
![](//thafakerde.appspot.com/img/centos_6_install/install-centos-6-boot-screen.jpg)[![Install CentOS 6 - Boot Screen](//techspotting.org/wp-content/uploads/2011/08/install-centos-6-boot-screen-300x225.png) (archiviert)](http://web.archive.org/web/20111015065653/http://techspotting.org/wp-content/uploads/2011/08/install-centos-6-boot-screen.png)**
4. Nun erscheint der CD-Check. Ich persönlich überspringe diesen Test immer, weil es mir einfach viel zu lange dauert. Aber wenn mal eine Install nicht durchläuft weil das Medium im Eimer ist, weiß man wofür die Option da ist :-)![](//thafakerde.appspot.com/img/centos_6_install/install-centos-6-cd-check.jpg)
5. Jetzt sieht man wilden Text auf der Console durchrauschen. Der Rechner lädt die  X11 Umgebung für die grafische Oberfläche der CentOS Installation, nach 30 Sekunden sollte das CentOS-Logo begrüßen. Klickt auf NEXT
![](//thafakerde.appspot.com/img/centos_6_install/install-centos-6-welcome-screen.jpg)
6. Wählt nun die Sprache aus.
![](//thafakerde.appspot.com/img/centos_6_install/install-centos-6-language-selection.jpg)
7. Wählt eure Tastatur aus.
![](//thafakerde.appspot.com/img/centos_6_install/install-centos-6-keyboard-type.jpg)
8. Festplattentyp. Ich installiere auf meine interne Festplatte, also wähle ich “Basic storage type”. Wenn Du auf iSCSI oder so was installieren solltest, dann wähle es am Besten jetzt.
![](//thafakerde.appspot.com/img/centos_6_install/install-centos-6-basic-storage-type.jpg)
9. Wenn das eine Clean-Install ist und die Festplatte noch nie benutzt worden ist, dann wird die folgende *Initialize* Meldung erscheinen.
![](//thafakerde.appspot.com/img/centos_6_install/install-centos-6-initialize-drive.jpg)
10. Tragt den Hostname eures Servers ein.
![](//thafakerde.appspot.com/img/centos_6_install/install-centos-6-hostname.jpg)
11. Nun gebt ihr eure Zeitzone ein.
12. Gebt nun das Root Kennwort ein. Bitte benutzt keine Standard-Wörter aus dem Duden, oder ihr werden von 13-jährigen englischen *Scriptkiddies* (for teh lulz) gehackt.
![](//thafakerde.appspot.com/img/centos_6_install/install-centos-6-root-password.jpg)
13. Nun müsst ihr ein paar Angaben zur Festplattenpartitionierung angeben. Wenn das eine frische Neuinstallation ist, dann nehmt einfach die Option *Use All Space*.
[![](//thafakerde.appspot.com/img/centos_6_install/install-centos-6-partition-options.jpg) (archiviert)](http://web.archive.org/web/20111015065229/http://techspotting.org/wp-content/uploads/2011/08/install-centos-6-partition-options.png)
14. Jetzt erscheint die Partitionstabelle. Wenn ihr einen Server aufsetztz, so rate ich irgendwie andere Partitionen für /home and /var zu erstellen denn diese beiden Verzeichnisse lassen Linux-Server regelmäßig crashen: /home weil Benutzer ihre Homes überfüllen und das zum Crash führt und /var weil die Logfiles von FTP und ähnlichem das Verzeichnis überlaufen lassen.
![](//thafakerde.appspot.com/img/centos_6_install/install-centos-6-partition-review.jpg)
15. Die Formatierungswarnung , klickt auf FORMAT (das löscht natürlich alle eventuellen vorhandenen Daten).
![](//thafakerde.appspot.com/img/centos_6_install/install-centos-6-format-warnings_.png)
16. Jetzt kommt die Meldung, dass alle Änderungen auf die Platten geschrieben werden und es dann keinen Weg mehr zurück gibt, sowie natürlich den vollständigen Verlust alles Irdischen. Klickt "Write changes to disk".
![](//thafakerde.appspot.com/img/centos_6_install/install-centos-6-write-changes-to-disk.jpg)
17. Die Boot Loader Options. Ich lasse die immer so, das passt, keine anderen OS auf der Kiste oder andere Dinge, dich ich beachten müsste.
![](//thafakerde.appspot.com/img/centos_6_install/install-centos-6-boot-loader.jpg)
18. Den nächsten Teil halte ich für wichtig: für Server empfehle ich immer minimal, das installier ein minimales Setup was ideal für Server ist, für einen Desktop sollte man natürlich was anderes auswählen. Je mehr man installiert, desto aufgeblähter wird der Server und desto mehr Sicherheitslücken können sich im System befinden, so prinzipiell.
![](//thafakerde.appspot.com/img/centos_6_install/install-centos-6-minimal-install.jpg)
19. CentOS 6 wird installiert.
![](//thafakerde.appspot.com/img/centos_6_install/install-centos-6-installing.jpg)
20. CentOS 6 ist installiert worden, Glückwunsch ^^
![](//thafakerde.appspot.com/img/centos_6_install/install-centos-6-congrats.jpg)
21. Reboot und login als root
![](//thafakerde.appspot.com/img/centos_6_install/install-centos-6-login-as-root.jpg)
22. Updated das system mit dem Befehl “yum update”, eigentlich gibt es immer was zu aktualisieren.
![](//thafakerde.appspot.com/img/centos_6_install/install-centos-6-yum-update.jpg)

Das wars auch schon wieder! Jetzt könnt ihr fortfahren und installieren was immer ihr wollt, zum Beispiel LAMPP oder Asterisk oder weiß der Geier.* Viel Spaß und Bis bald.*
