---
title: SMS Töne im iPhone ändern
slug: sms-tone-im-iphone-andern-2
date_published: 2009-07-11T12:55:45.000Z
date_updated: 2018-08-22T09:39:22.000Z
---

**ACHTUNG** liebe(r) LeserInnen: Hier gibt es [eine Seite (archiviert)](http://web.archive.org/web/20091107130920/http://thafaker.de:80/iphone-ipod) mit allen Artikeln die zum Thema iPhone, iPod, Jailbreak, IPA und so weiter existieren.

**Weiter mit dem Artikel:**

Wie kann man denn diese schrecklichen SMS-Töne im iPhone verändern? Natürlich nicht offiziell oder gar von Apple angedacht und gewollt, geht es natürlich nur mit einem durch den Jailbreak befreiten iPhone.

**Was wird benötigt:**

- iPhone
- Jailbreak
- **[openSSH (archiviert)](http://web.archive.org/web/20091204054014/http://revver.com:80/video/694666/openssh/)** auf dem iPhone damit man sich per SFTP verbinden kann
- ein paar MP3s die man als SMS/System Töne benutzen möchte

**Die Töne liegen in folgendem Verzeichnis:**
    /System/Library/Audio/UISounds

**HINWEIS: Bevor Ihr die Original Töne durch eure ersetzt solltet Ihr eine Sicherungskopie**** auf eurem Rechner ablegen, also alle Dateien mit den Namen (für SMS) **sms-received1.caf bis 6.caf **in einen Ordner auf der Platte ziehen.**
### **Anleitung:**

- **Schritt 1:**

Als erstes startet Ihr iTunes, importiert dort euren Ton den ihr als SMS/System Ton benutzen wollt
![](//img.skitch.com/20080821-p18pddps9atf8t7n1yfr5mesbq.png)

- **Schritt 2:**

Klickt nun mit der rechten Maustaste auf den Ton, wenn Ihr wie im folgenden Bild *“Auswahl konvertieren in MP3″* seht – müsst ihr erst Schritt 3 ausführen
![](//img.skitch.com/20080821-dn1fai7u43p74iue9ssn8cidpn.png)

- **Schritt 3:**

Geht in die Einstellungen von iTunes und unter Erweitert wählt ihr unter Importieren den AIFF-Codierer aus
![](//img.skitch.com/20080821-fm3cjh55sdsbeqsxay4r5k7pcn.png)
- **Schritt 4:**

Nun geht ihr wieder zurück auf euren Ton, wenn ihr nun die Rechte Maustaste drückt solltet Ihr *“Auswahl konvertieren in AIFF”* sehen – das macht ihr nun auch – also klickt drauf.
![](//img.skitch.com/20080821-fiyb279ind44d55a5s1ntytpci.png)
- **Schritt 5:**

Nun zieht Ihr eure neue Datei auf den Schreibtisch
![](//img.skitch.com/20080821-k85td4knhuan3224umqr9bisck.png)
- **Schritt 6:**

Benennt nun eure .AIF Datei in .CAF um – die Warnmeldung mit .caf verwenden bestätigen
![](//img.skitch.com/20080821-ruyj5xu775d3qr73dhw9mynkhi.png)
- **Schritt 7:**

Nun gebt Ihr eurem Ton den Namen der Original Datei die ihr auf dem iPhone ersetzen wollt, in diesem Fall habe ich den 2. SMS Ton gewählt.
![](//img.skitch.com/20080821-8gf5xfr7p1e36kn58fuss46pee.png)
- **Schritt 8:**

Nun verbindet Ihr euch per SSH mit eurem iPhone und geht in das folgende Verzeichnis und kopiert dort euren neuen Ton rein:

    /System/Library/Audio/UISounds

**HINWEIS:** Bevor Ihr die Original Töne durch eure ersetzt solltet Ihr eine Sicherungskopie auf eurem Rechner ablegen!
![](//img.skitch.com/20080821-k4gu3b9w6b3p7d86jr9m111a4f.png)

Nun könnt Ihr in den Einstellungen im iPhone den neuen Ton auswählen. ABER der Name wird sich nicht ändern! D.h. ihr habt nach wie vor die tollen Namen wie Glockespiel & Co ;-) Sollte euer Ton nicht sofort abspielen muss eventuell das iPhone einmal neugestartet werden.
