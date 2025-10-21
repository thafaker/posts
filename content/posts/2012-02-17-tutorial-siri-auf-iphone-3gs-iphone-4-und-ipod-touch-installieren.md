---
title: [Tutorial] Siri auf iPhone 3GS, iPhone 4 und iPod touch installieren
slug: tutorial-siri-auf-iphone-3gs-iphone-4-und-ipod-touch-installieren
date_published: 2012-02-17T18:21:13.000Z
date_updated: 2018-08-22T09:38:13.000Z
---

An dieser Stelle noch ein mal sehr ausführlich -und in aller Ruhe beschrieben- der Weg, wie man Siri auch auf einem iPhone 4 oder dem iPod touch oder gar einem alten iPhone 3Gs zum Laufen bekommt. Vorab sei allerdings gesagt: es gibt keine Neuigkeiten, wer unser Weblog aufmerksam verfolgt, wird die in diesem Tutorial zu Grunde liegenden Informationen bereits kennen.

[![assistantconnect_artikel2](//picdump.thafaker.de/2012/02/assistantconnect_artikel2-125x125.jpg)](http://picdump.thafaker.de/2012/02/assistantconnect_artikel2.jpg)Apples intelligenter Assistent Siri lässt sich schon seit einiger Zeit auch auf älteren iOS-Geräten installieren, ein Jailbreak natürlich vorausgesetzt. Bis vor kurzem war die Portierung von Siri aber relativ kompliziert und auch nicht immer von Erfolg gesegnet. Im folgendenen Tutorial zeigen wir die derzeit einfachste und schnellste Methode Siri auf iPhone 3GS, iPhone 4, iPod touch 3 und iPod touch 4 zu installieren.

**Kurze Einführung:**

Um Siri auf einem älteren iOS-Gerät mit den Apple-Servern kommunizieren lassen zu können, benötigen wir grob gesagt einen Zugangsschlüssel eines iPhone 4S. Jedes iPhone 4S besitzt einen uniquen bzw. einzigartigen Zugangsschlüssel für die Siri-Server. Ohne diesen Schlüssel gibt es keinen Datenaustausch mit den Siri-Servern. Möchte man also ein älteres iOS-Device mit einem funktionstüchtigen Siri-Assistenten nachrüsten, benötigt man einen Schlüssel eines iPhone 4S.

Seinen persönlichen iPhone 4S-Zugangsschlüssel sollte man nicht frei zugänglich im Web bereitstellen, da die Gefahr besteht, dass Apple den Schlüssel sperrt wenn überdurchschnittlich viele Zugriffe erkannt werden. Folglich könnte Siri dann auch auf dem jeweiligen iPhone 4S nicht mehr funktionieren. Bisher gibt es jedoch keine Berichte wonach Apple einen Schlüssel deaktiviert hat.

Wenn man seinen iPhone 4S-Schlüssel nur mit einer vertrauenswürdigen Person teilt, sollte es keine Probleme geben. Zu beachten ist jedoch, dass wenn der Siri-Schlüssel auf zwei Geräten verwendet wird, diese nicht gleichzeitig Abfragen starten können.

Die Durchführung der Anleitung auf eigene Gefahr!

**Voraussetzungen:**

- Zugang zu einem gejailbreakten iPhone 4S
- Gejailbreaktes iPhone 3GS oder iPhone 4 bzw. gejailbreakter iPod touch 3 oder iPod touch 4
- Internetverbindung
- Mail-Account auf den jeweiligen Devices
- 10 Minuten Zeit

**Anleitung iPhone 4S:**
1. Wir öffnen Cydia auf dem gejailbreakten iPhone 4S
2. Installieren “**AssistantConnect4S**”
[![assistantconnect4s](//picdump.thafaker.de/2012/02/assistantconnect4s-580x435.jpg)](http://picdump.thafaker.de/2012/02/assistantconnect4s.jpg)
3. Nach der Installation von AssistantConnect4S öffnen wir es und starten danach das iPhone 4S neu
4. Nach dem Neustart öffnen wir AssistantConnect4S erneut und aktivieren Siri, fragen beispielsweise nach dem Wetter
5. Wir tippen direkt auf “**Email Siri Data**” und senden die Email mitsamt Anhang an das jeweilige Device, welches mit Siri nachgerüstet werden soll
6. Wir schliessen AssistantConnect4S.

**Anleitung iPhone 3GS/iPhone4/iPod touch 3/iPod touch 4:**

1. Wir öffnen Cydia und installieren “**AssistantConnect**” (NICHT “AssistantConnect4S”)
Normalerweise wird “**Spire**” automatisch mitinstalliert. Ist dies nicht der Fall auch Spire installieren.
2. Wir öffnen die Mail-App, suchen die Email “New Assistant Connection File.” welche wir uns zuvor über das iPhone 4S zugesandt haben,
[![openassistantconnect](//picdump.thafaker.de/2012/02/openassistantconnect-580x435.jpg)](http://picdump.thafaker.de/2012/02/openassistantconnect.jpg)
3. klicken auf den idR knapp 0,9 KB grossen **Dateianhang** und **öffnen diesen mit AssistantConnect**
4. AssistantConnect sollte nun wie folgt ein Popup anzeigen: “**File Copied – AssistantConnect File Loaded Succesfully**“
5. Wir öffnen **Einstellungen > Allgemein > Siri** und **aktivieren Siri**
6. Jetzt wechseln wir zu **Einstellungen > Spire** und tragen in das Feld “Proxy Host” ***https://guzzoni.apple.com*** ein
7. Wir starten Siri in dem wir lange den Homebutton drücken. Die erste Suchanfrage kann einige Sekunden dauern. Danach sollte Siri weitestgehend problemlos funktionieren.
8. Spaß haben!
