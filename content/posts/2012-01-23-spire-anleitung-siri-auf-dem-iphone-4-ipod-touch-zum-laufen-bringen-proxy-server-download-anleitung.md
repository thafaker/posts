---
title: "Spire-Anleitung: Siri auf dem iPhone 4 & iPod Touch zum Laufen bringen + Proxy-Server [Download + Anleitung]"
slug: spire-anleitung-siri-auf-dem-iphone-4-ipod-touch-zum-laufen-bringen-proxy-server-download-anleitung
date_published: 2012-01-23T21:30:20.000Z
date_updated: 2018-08-22T09:38:14.000Z
---

Es gibt ja bereits seit seit längerer Zeit die durch den Hacker Chpwn als ersten legalen Siri-Port veröffentlichte Software Spire, welche seitdem via Cydia zum Download bereit steht. Seit Tagen sind viele von euch auf der Suche nach funktionierenden Proxy-Server-Adressen, die Siri letztendlich auf eurem iPhone oder iPod Touch zum Laufen bringen. Da damit sehr viel Schindluder getrieben wird und man sogar hin und wieder fast von *Abzocke* sprechen kann, haben wir nun eine Anleitung erstellt, womit Siri auch auf eurem Gerät antworten wird.

WERBUNG

---

---

---

Insgesamt gibt es mittlerweile mehrere Möglichkeiten Siri auf seinem iDevice zum Reden zu bringen, eine davon ist die wohl bekannteste über den Cydia-Tweak „Spire“. Wie ihr Spire installiert, könnt ihr in unserer extra hierfür angelegten Anleitung nachschauen. [[Spire-Installation](__GHOST_URL__/siri-auf-iphone-4-oder-ipod-touch-4g-installieren-anleitung-download-video/)]

Wenn Spire installiert ist, fehlt jedoch noch die Verbindung zum Apple-Server. Diese muss nach wie vor über einen Proxy-Server hergestellt werden. Wie das Ganze funktioniert, erfahrt ihr nun hier.

**Hinweis**: Es ist uns wichtig, das ihr wisst, dass eure Daten (SMS, Mails, Kontakte, Musik-Listen) an die Proxy-Server gesendet werden. Der Betreiber (wer auch immer) kann diese komplett sehen und damit anstellen was er will. Es ist gut möglich, dass eure Daten verkauft bzw. für kriminelle Sachen verwendet werden! Nutzung ist auf eigene Gefahr!!

**Anleitung – Spire bzw. Siri zum Laufen bringen:**

- Ganz wichtig ist, dass ihr die Reihenfolge der Anleitung einhaltet!

**Schritt 1**: Installiert euch Spire aus Cydia [[Anleitung Spire](__GHOST_URL__/siri-auf-iphone-4-oder-ipod-touch-4g-installieren-anleitung-download-video/) und hier für [Jailbreak an sich (archiviert)](http://web.archive.org/web/20110918200244/http://thafaker.de:80/jailbreak-unlock-status/)]
**Schritt 2**: Nun müsst ihr euch ein Zertifikat installieren. Geht mit eurem Device in Safari und öffnet: http://siriport.ru/1.crt und installiert das “apple.guzzoni” Zertifikat.

**Schritt 3**: Zieht euch iFile aus Cydia und navigiert zu /etc und öffnet eure Host-Datei mit dem Textviewer. Nun ersetzt ihr den kompletten Inhalt durch diesen hier.

> ##
> # Host Database
> #
> # localhost is used to configure the loopback interface
> # when the system is booting. Do not change this entry.
> ##
> 127.0.0.1 localhost
> 225.225.225.225 broadcasthost
> ::1 localhost
> fe80::1%lo0 localhost
> 31.170.134.60 guzzoni.apple.com
> 31.170.134.60 17.174.4.4

**Schritt 4**: Nun must ihr mit iFile zu var/mobile/Libary/Preferences navigieren und folgende Zeilen bzw. plist’s löschen.

- com.apple.assistant.plist
- com.apple.assistant.support.plist

**Schritt 5**: Aktiviert nun Siri in den Einstellungen.

**Schritt 6**: Öffnet nun Spire und fügt folgende Host-Adresse in den Optionen ein.

- https://guzzoni.Apple.com

**Schritt 7**: Nun müsst ihr euer Gerät noch rebooten. Falls es nicht funktioniert, immer wieder rebooten und versuchen bis es klappt. Es kann auch einige Stunden dauern, bis ihr einen Auth. Key zugewiesen werdet.

Siri sollte nun bald bei euch antworten und viel Spaß! Wenn nicht sind die Server gerade überlastet oder keine Auth- Keys verfügbar. In diesem Fall ist warten angesagt!

**Hinweis**: Es ist uns wichtig, das ihr wisst, dass eure Daten (SMS, Mails, Kontakte, Musik-Listen) an die Proxy-Server gesendet werden. Der Betreiber (wer auch immer) kann diese komplett sehen und damit anstellen was er will. Es ist gut möglich, dass eure Daten verkauft bzw. für kriminelle Sachen verwendet werden! Nutzung ist auf eigene Gefahr!!

Solltet ihr weiterhin Hilfe brauchen oder nicht weiterwissen, könnt ihr auf unserer [Facebook-Fanpage](http://www.facebook.com/pages/thafaker-auf-Beton/154600141278763) jederzeit um Rat fragen. Die neusten News und Tipps bekommt ihr ebenfalls dort.

([via](http://tinyurl.com/7xsmny3))

---

*Um auf dem Laufenden zu bleiben, könnt ihr uns auf [Twitter (archiviert)](http://web.archive.org/web/20250905043545/https://twitter.com/) folgen oder die [Facebook-Seite](http://de-de.facebook.com/pages/thafaker-auf-Beton/154600141278763) besuchen.*

---
