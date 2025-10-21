---
title: [UNLOCK] jedes iPhone mit jedem Baseband und jeder Firmware iOS [Howto] [UPDATE #2]
slug: unlock-jedes-iphone-mit-jedem-baseband-und-jeder-firmware-ios
date_published: 2012-04-22T21:09:11.000Z
date_updated: 2018-08-22T09:38:10.000Z
---

---

---
**ACHTUNG**Leider hat Apple die Art und Weise der Authentifizierung geändert, serverseitig, die im folgenden Artikel beschriebene SAM-Methode sowie von woanders her bekannte Gevey-Sim-Karten-Methoden (benutzten alle die gleiche Lücke) funktionieren bis auf weiteres nicht mehr! Es tut uns Leid - aber ein Unlock ist derzeit nicht möglich.
---

---

**DISLCAIM:** Alles auf eigene Gefahr, wir haften nicht für eventuelle Schäden oder so, wenn ihr das nicht einseht, machts nicht. Ansonsten: [folgt uns auf Facebook](http://de-de.facebook.com/pages/thafaker-auf-Beton/154600141278763) für eventuelle Fragen oder Diskussionen usw.

Im zweiten Teil des Artikels ab dem How To Video folgt eine andere Anleitung die zum selben Ziel führen soll, nur einfach geschrieben und mit weiteren Screenshots zur Verdeutlichung geschrieben.

---

Etwas ganz heißes ist da heute über den großen Teich geschwappt. Es ist eine Möglichkeit aufgetaucht, jedes jailbroken iPhone unzulocken. Jeder der mit einem 3Gs oder ähnlichem und der schlechten Basebands fest hängt oder ein iPhone 4 mit hohem Baseband hat, wird nun endlich die Möglichkeit erhalten, einen Unlock durchzuführen und somit mit einer fremden als der vorgesehen SIM Karte telefonieren zu können.

Grundvoraussetzung für den Unlock ist ein Jailbreak, die Baseband Version ist dabei völlig egal. Das iPhone 4 kann mit >iOS 5.1 freigeschaltet das neue iPhone 4S mit >iOS 5.0.1.

Niemand geringeres als [Musclenerd (archiviert)](http://web.archive.org/web/20250905043545/https://twitter.com/) hat die Geschichte bestätigt, dass dem chinesischen Entwickler *Loktar_Sun* die [Möglichkeit](http://laforeta.blogspot.co.nz/2012/04/how-to-spoof.html) geglückt ist, den Unlock eines jailbroken iPhones unter Zuhilfenahme vom Subscriber Artificial Module (SAM) von Sam Bingner durchzuführen.
![Unlock-iPhone](//picdump.thafaker.de/2012/04/Unlock-iPhone.jpg)
## Wie funktioniert SAM?

Das Besondere an** SAM** ist nicht nur die Tatsache, dass alle iPhone Geräte vom Sim-Lock befreit werden können sondern zudem auch noch **nicht** einmal eine **originale SIM-Karte** des jeweiligen Providers **benötigt wird**. Einzig und allein die Kenntnisnahme des entsprechenden **Provider-Locks** genügt um das Gerät entsperren zu können. Schließlich nutzt SAM eine Lücke in Apples Aktivierungsservern.

---

Wenn man diesen Unlock durchführt, so funktioniert er nur mit der SIM, die sich zu dem Zeitpunkt im iPhone befindet. Will man auch eine andere SIM Karte benutzen, so muss man die Schritte mit der neuen SIM erneut durchführen, es wird quasi nicht das iPhone sondern die jeweilige SIM geunlocked, sozusagen.

**Welche Basebands können unlocked werden?** BB 05.15.04, BB 05.16.00, BB 05.16.02, BB 01.59.00, BB 02.10.04, BB 03.10.01, BB 04.10.01, BB 04.11.08 und theoretisch auch die Basebands vom iPhone 4s, aber weil das iPhone 4s noch nicht gejailbreaked werden kann, funktioniert auch diese Anleitung noch nicht. Aber bald :-)

Wer nicht so viel lesen will, für den haben wir ganz unten am Ende des Artikels auch ein How To Video eingefügt.

### **Voraussetzung**

- iPhone mit Jailbreak, egal welches (iPhone 4S ist noch nicht jailbreakable) ([hier (archiviert)](http://web.archive.org/web/20110918200244/http://thafaker.de:80/jailbreak-unlock-status/) steht wie es geht; in der unteren Tabelle einfach euer Gerät auswählen)
- Computer mit vollem Internetzugang ((lol?))
- aktuelleste Version von iTunes ([hier](http://www.google.de/url?sa=t&amp;rct=j&amp;q=&amp;esrc=s&amp;source=web&amp;cd=1&amp;ved=0CEQQFjAA&amp;url=http%3A%2F%2Fwww.apple.com%2Fde%2Fitunes%2Fdownload%2F&amp;ei=pv2UT5nWL8zLtAa55PTABA&amp;usg=AFQjCNEd8AKzralyLrcq6rxDh_23QAPwZg))
- the original carrier information of the locked device in question.

## **Anleitung**
**SCHRITT 1**: Öffnet Cydia auf dem iPhone und fügt das Repository von SAM hinzu.
- URL is *http://repo.bingner.com*

![Step1SAM](//picdump.thafaker.de/2012/04/Step1SAM-580x571.png)
**SCHRITT 2:** Startet das SAM Interface. Das macht ihr indem ihr das SAMPrefs Icon auf dem Bildschirm antippt. Achtet darauf, das die von euch zu benutzende SIM Karte im Handy ist.

**SCHRITT 3:** Nach dem Start von SAM wählt  ihr die ‘*Utilities*‘ Option und dann ‘*De-Activate iPhone*‘ auswählt. Danach sollte das Gerät als ‘*Unactivated*‘ angezeigt werden, wie nach nem neuen Kauf.

**SCHRITT 4:** SAM bleibt an und ihr wählt ‘*By Country and Carrier*‘ in den Method Options. Im nächsten Schritt findet ihr euren Carrier (Mobilcom, Telekom...) in der Liste. Manche Anbieter nutzen mehr als nur die network ID, deshalb sollte man eventuell auch noch ‘*SIM ID*‘ option auswählen, damit das jeweilige Netzwerk tatsächlich recocnized wird..

**SCHRITT 5:** Geht auf ‘*More Information*‘ und notiert euch die IMSI Nummer die in dem Bereich ‘*SAM Details*‘ steht, bevor ihr auf ‘*Spoof Real SIM to SAM*‘. Geht nun zurück zum Hauptmenü und wechselt bei ‘*Method*‘ zu manual und tragt dort den IMSI Code ein, den ihr euch gerade notiert habt.

**SCHRITT 6:** Verbindet das iPhone mit dem Computer und erlaubt iTunes das iPhone zu aktivieren. Dann klickt ihr auf die Handynummer und hoffenlich ist die angezeigte ICCID die gleiche die auch auf der SIM Karte gefunden wurde. Wenn sich die beiden Strings nicht gleichen, müsst ihr alles noch mal Schritt 1 an durchführen, bis es passt.
![Step6SAM1](//picdump.thafaker.de/2012/04/Step6SAM1-580x152.png)
**SCHRITT 7: **Wenn die beiden ICCIDs gleich sind, dann zieht das Gerät vom Kabel ab und deaktiviert SAM. Verbindet das Gerät wieder mit iTunes und lasst euch von eventuellen Fehlermeldungen nicht beirren (z.B. ein Popup was sagt das Gerät könne nicht aktiviert werden etc). Diese Fehler sind normal und zur Lösung muss einfach nur iTunes neu gestartet werden, dann gehts!

**SCHRITT 8: **Nach einem kurzen Augenblick sollte das iPhone die wunderschönen Signalpegel anzeigen und so, was natürlich bedeutet, dass jetzt alles geklappt hat und ihr euer gelocktes iPhone mit ner fremden Sim benutzen könnt. YAY! Wenn Push noch nicht richtig funktioniert, sollte ihr in SAM die Option ‘*Clear Push*‘ und dann das Gerät wieder mit iTunes verbinden - bingo.

Das wars, ihr habt ein (eigentlich locked) unlocked iPhone mit eurer Lieblingssimkarte und sobald ein Jailbreak für das iPhone 4s draußen ist, funktioniert die Methode auch mit einem iPhone 4s :-)

Um die Sache zu verdeutlichen, gibt es jetzt ein Video zur Durchführung, ein How To Video. Allerdings geht die schriftliche Anleitung natürlich auch problemlos.

*Viel Spaß am Gerät.
*

---

[http://www.redmondpie.com/how-to-unlock-any-jailbroken-iphone-on-any-baseband-and-firmware/](http://www.redmondpie.com/how-to-unlock-any-jailbroken-iphone-on-any-baseband-and-firmware/)

---

# **[UPDATE] AUS AKTUELLEM ANLASS HIER NOCH MAL EIN ANDERES HOW TO**

---

**Voraussetzungen:**

- Euer iPhone braucht den Jailbreak ab iOS 5.0.1
- Euer iPhone sollte nicht gesperrt sein, bzw. auf der schwarzen Liste stehen (Apple ID gesperrt)
- Ihr müsst wissen welchen Provider-Lock euer iPhone hat (T-Mobile, O2, Vodafone etc.)
- Neueste iTunes Version [hier](http://www.apple.com/itunes/download/) laden
- Eure Karte, welche ihr entsperren wollt, muss sich im iPhone befinden.

**Unterstützt folgende Geräte & Basebands:**
- für ALLE iPhone-Geräte und ALLE Basebands (z.B. 04.11.08)
- Auch iPhone 4S / 3GS

### **Anleitung: Unlock iPhone mit SAM aus Cydia**
**Schritt 1:** Öffnet Cydia und fügt folgende Quelle hinzu:

- http://repo.bingner.com

**Schritt 2:** Nun installiert euch SAM aus dieser Repo. Danach findet ihr ein SAMPrefs Icon auf eurem Springboard.

**Schritt 3:** Nun geht in die allgemeinen Einstellungen zu SAM und klickt auf “De-Activate iPhone”. Dadurch ändert sich der Status “ActivationState” unter “Weitere Informationen” in “Unactivated”.

**Schritt 4:** Nun klickt in “Method” auf “By Contry and Carrier” und füllt anschließend die beiden anderen Felder aus. Sucht also nach euren Provider, z.B. T-Mobile oder AT&T und dem Land des Providers, z.B. Germany für T-Mobile oder United States für T-Mobile USA. Zusätzlich wählt ihr noch die SIM ID aus.

Beispiel –> Ihr habt ein iPhone bei der Deutschen Telekom gekauft und wollt nun eine O2-Karte nutzen. Bei “Country” muss also Germany rein und bei Carrier “T-Mobile”.

[![SAM-Land-auswählen](//picdump.thafaker.de/2012/04/SAM-Land-auswählen.png)](http://picdump.thafaker.de/2012/04/SAM-Land-auswählen.png)

(Carrier auswählen)

[![SAM-Carrier-auswählen](//picdump.thafaker.de/2012/04/SAM-Carrier-auswählen.png)](http://picdump.thafaker.de/2012/04/SAM-Carrier-auswählen.png)

(SIM ID auswählen)

[![SAM-SIM-ID-auswählen](//picdump.thafaker.de/2012/04/SAM-SIM-ID-auswählen.png)](http://picdump.thafaker.de/2012/04/SAM-SIM-ID-auswählen.png)

**Schritt 5:** Nun geht zurück und klickt auf “Weitere Informationen” und notiert / kopiert euch die IMSI, welche unter “SAM Details” steht. Nachdem ihr diese kopiert oder aufgeschrieben habt, klickt auf “Spoof Real SIM to SAM”.

[![SAM-Mehr-Informationen-IMSI-kopieren](//picdump.thafaker.de/2012/04/SAM-Mehr-Informationen-IMSI-kopieren.png)](http://picdump.thafaker.de/2012/04/SAM-Mehr-Informationen-IMSI-kopieren.png)

[![SAM-Spoof-Real-SIM-to-SAM](//picdump.thafaker.de/2012/04/SAM-Spoof-Real-SIM-to-SAM.png)](http://picdump.thafaker.de/2012/04/SAM-Spoof-Real-SIM-to-SAM.png)

**Schritt 6:** Geht erneut zurück und stellt im Hauptmenü von SAM unter Method auf “Manual” um. Gebt nun eure gerade eben notierte IMSI ein in das Feld “IMSI” ein.

[![SAM-IMSI-einfügen](//picdump.thafaker.de/2012/04/SAM-IMSI-einfügen.png)](http://picdump.thafaker.de/2012/04/SAM-IMSI-einfügen.png)

**Schritt 7:** Nun müsst ihr euer iPhone an den Rechner anschließen und iTunes öffnen. Überprüft nun ob die UCCID’s übereinstimmen, in iTunes steht diese nun unter der Seriennummer oben bei den Geräte-Infos. Diese ICCID muss mit der in SAM unter “SAM Details” angezeigten ICCID übereinstimmen. Falls nicht, wiederholt die Anleitung.

[![ICCID-Abgleich](//picdump.thafaker.de/2012/04/ICCID-Abgleich.png)](http://picdump.thafaker.de/2012/04/ICCID-Abgleich.png)

**Schritt 8:** Entfernt euer iPhone vom Rechner bzw. vom USB-Kabel, schließt iTunes und deaktiviert SAM mit dem Enable-Button in SAM.

**Schritt 9:** Nun verbindet euer iPhone erneut mit dem Rechner und startet iTunes neu. Ihr dürftet eine Fehlermeldung angezeigt bekommen, öffnet iTunes nun noch einmal neu. Nachdem ihr etwas gewartet habt, solltet ihr langsam Netz bekommen.

**Geschafft**: Nun solltet ihr vom SIM-Lock befreit sein. Nach dieser Anleitung sollten Push-Benachrichtigungen nicht mehr funktionieren, diese könnt ihr aber mit einem Klick auf “clear Push” und einem verbinden mit iTunes wiederbeleben. Ein Video von dem kompletten Vorgang haben wir unten einmal für euch eingebunden.

**Hinweis**: Speichert euch den Ordner “Lockdown” bzw. legt eine Sicherung des Aktivierungs-Ticket. Zu finden in /var/root/Library/Lockdown/

Das Verfahren ist noch etwas umständlich, allerdings wurde bereits eine Vereinfachung für die nächsten Tage angekündigt. Wir hoffen bei euch klappt das Verfahren und ihr berichtet uns von euren Erfolgen oder eventuell auftretenden Problemen auf unserer [Facebook-Fanpage](http://www.facebook.com/pages/thafaker-auf-Beton/154600141278763).
