---
title: AeroFS ist da - Syncing ohne Cloud, aber besser
slug: aerofs-ist-da-syncing-ohne-cloud-aber-besser
date_published: 2013-04-03T17:01:00.000Z
date_updated: 2018-08-22T09:38:50.000Z
---

![aero fs](//picdump.thafaker.de/2013/04/Bildschirmfoto-2013-04-03-um-18.55.09-100x100.png)Wir haben bereits Ende 2011 am [Beta-Test Teil genommen und über **AeroFS** berichtet](__GHOST_URL__/aerofs-p2p-filesharing-mit-ohne-cloud/). Verhältnismäßig lange hat es seitdem gedauert, bis AeroFS so stabil läuft, dass es auch im produktiven Einsatz genutzt werden kann. Und jetzt ist es soweit. Heute kam die [Mail vom Entwickler](http://blog.aerofs.com/336/open-for-business), dass AeroFS endlich final Business geht. Somit steht der Dienst nun jedem Interessierten zur Verfügung. 

[AeroFS](http://www.aerofs.com/) ist eine auf P2P-basierende Technologie, welche die **verschlüsselte** Synchronisation der Daten über das lokale Netzwerk oder das Internet ermöglicht. Client-Software gibt es bisher für Windows, Mac OS X und Linux. Man kann via Peer to Peer nicht nur die eigenen Dateien synchronisieren, auch teilen ist möglich – so wie das Einladen zu einem Ordner bei Dropbox. Im Gegensatz zu Dropbox ((Dropbox kann auch LAN-Sync, aber das ist hier nicht gemeint)) besteht hier aber die Möglichkeit, seine zwei Macs ((Oder PCs)) in einem LAN direkt zu synchronisieren, ohne dabei den Umweg über das Internet gehen zu müssen. Andererseits kann man aber auch ganz simple einen Ordner für einen Freund frei geben, der die Daten dann über das Internet erhält.

Die jetzt frei gegebene Version ist für 1 - 3 Personen kostenlos, hiermit eingeschlossen ist auch ein 'collaborator', eine Person, die nicht direkt zu den 3 Personen gehört, aber auch zu einem Ordner eingeladen werden kann. Man bildet quasi ein Team, mit welchem man seine Daten shared. Dieses Team hat Zugriff auf die verschlüsselten Daten. Ein collaborator gehört nicht zum Team, darf aber auch auf die verschlüsselten Daten zugreifen, easy access.

AeroFS richtet auf dem eigenen Rechner einen Ordner ein, dessen Inhalte mit allen Geräten, auf denen der gleiche AeroFS-Account genutzt wird, automatisch synchronisiert werden.

AeroFS verschlüsselt sämtliche Dateien sowie ihre Metadaten bereits auf dem Client. Dabei kommt AES-256 mit 2.048-Bit-RSA zum Einsatz. Der Anbieter **Air Computing** hat zu keinem Zeitpunkt Zugriff auf die Inhalte der Dateien. Auch die Dateinamen kann dieser nicht einsehen.

Air Computing speichert nicht einmal die Dateien der Nutzer auf dem eigenen Server, sondern stellt lediglich verschlüsselte Verbindungen zwischen den einzelnen Geräten her, die die Daten dann direkt untereinander synchronisieren. Auf den AeroFS-Servern werden lediglich die Nutzernamen, Hashes der Passwörter und die Namen und Zugriffsberechtigungen von Ordnern gespeichert. (([Quelle](http://www.golem.de/news/aerofs-das-bessere-dropbox-1304-98485.html)))

Zum Glück setzt AeroFS aber nicht nur auf die Datenverteilung zwischen Endgeräten, sondern kann auch anderen Storage mit einbinden, z.B. Cloud-Storage. Dazu benötigt man den AeroFS-Serer, den es für OS X, Linux und Windows gibt. Hier werden die Daten durch die Software auf dem Dateisystem gespeichert, so dass praktisch jeder Server in das verteilte Dateisystem eingebunden. Unternehmen können mit dem AeroFS aber nicht nur eigene Dateiserver nutzen, sondern die Dateien auch bei Amazon in dessen Cloud-Speicherdienst S3 ablegen. Auch dabei gilt: Alle Dateien werden verschlüsselt gespeichert.

AeroFS ist sicher, keine Daten werden außerhalb der eigenen Infrastruktur gespeichert und dadurch hat man volle Kontrolle. AeroFS kann Revisionen jeder Datei anlegen, so dass man später problemlos auf eine alte Datei zugreifen kann. Um den benötigten Speicherplatz gering zu halten, nutzt der AeroFS-Server zudem eine Datendeduplikation auf Block-Ebene ((vergleiche [ZFS](http://de.wikipedia.org/wiki/ZFS_%28Dateisystem%29))).

Geplant sind auch Clients für Android und iOS, was wir für sehr wichtig erachten, denn erst dann kann man auf seine Daten von überall aus, wie auch bei Dropbox, zugreifen.

**Downloads**

- [AeroFS Client Mac (archiviert)](http://web.archive.org/web/20130420053823/https://aerofs.com/pricing)
- [AeroFS Client Win (archiviert)](http://web.archive.org/web/20130420053823/https://aerofs.com/pricing)
