---
title: Google Calendar und iCal mit CalDAV
slug: google-calendar-und-ical-mit-caldav
date_published: 2008-09-15T19:14:37.000Z
date_updated: 2018-08-22T09:39:03.000Z
---

![ical](//picdump.thafaker.de/2008/09/ical.jpg)
So, dann male ich jetzt mal mit Bildchen auf, wie man den [Google Kalender](https://www.google.com/accounts/ServiceLogin?service=cl&amp;passive=true&amp;nui=1&amp;continue=http%3A%2F%2Fwww.google.com%2Fcalendar%2Frender%3Fhl%3Dde&amp;followup=http%3A%2F%2Fwww.google.com%2Fcalendar%2Frender%3Fhl%3Dde&amp;hl=de) mit Apple's iCal benutzt. Die darunter liegende Technik heißt übigens CalDAV, welche iCal ab OSX 10.5 unterstützt. Los gehts:

1. Das Wichtigste zuerst: man benötigt natürlich einen fertig eingerichteten und funktionierenden Google Kalender. [Hier (archiviert)](http://web.archive.org/web/20070910005531/http://www.google.com:80/intl/de/googlecalendar/tour.html) gibt es Unterstützung.
2. Dann natürlich erst mal iCal öffnen. Finder -> Programme -> **iCal**
3. Aus dem iCal Menü oben -> **Einstellungen** wählen, oder einfach die beiden Tasten Apfel + Komma gleichzeitig drücken.
4. Im neuen Fenster zum Tab -> **Accounts** wechseln.
5. Unter der Accounts-Leiste das Plus **+** anklicken.
[![ical_dav1](//picdump.thafaker.de/2008/09/ical_dav1.png)](http://picdump.thafaker.de/2008/09/ical_dav1.png)
6. Im dann erscheinenden Pop-Up Fenster nun bitte folgende Informationen eintragen, wobei es jetzt wohl etwas tricky werden könnte:
[![cal_dav3](//picdump.thafaker.de/2008/09/cal_dav3.png)](http://picdump.thafaker.de/2008/09/cal_dav3.png)- Beschreibung ist klar: kann man nennen wie man will
- Benutzername: der Login von Google
- Kennwort: Logisch, das Kennwort von Google 
- Account-URL: Hier muss nun die folgende Adresse eingetragen werden: **http****s****://www.google.com/calendar/dav/****BenutzerName****@googlemail.com/user** 
- Wichtig hierbei: BenutzerName mit dem eigenen ersetzen und vorn das S bei HTTPS nicht vergessen. Die Verbindung erfolgt verschlüsselt.
7. Erledigt? Gut! Nun einfach auf Hinzufügen klicken, eine kleine Weile warten (Google sagt 5 bis 7 Minuten beim erstmaligen adden eines Kalenders, aber bei mir gings in 8 Sekunden) und fertig ist die Laube.
[![cal_dav4](//picdump.thafaker.de/2008/09/cal_dav4.png)](http://picdump.thafaker.de/2008/09/cal_dav4.png)

Der Google Kalender erscheint nun in der Liste der iCal-Kalender und iCal wird jede Änderungen automatisch mit dem Online-Kalender synchronisieren. Ich finde das total geil. Ich habe einen Kalender für private, wichtige Termine und einen für so öffentliche Sachen wie Parties und Zeugs. Die Kalender habe ich auf dem Macbook, dem iMac und auf Arbeit via Sunbird abonniert. Klappt alles prima und ich bin jederzeit im Bilde was mein Zeitmanagement ((Früher hatte ich keins)) angeht. Den Google Kalender kann man natürlich auch online besuchen und anschauen. Man kann auch einstellen ob er öffentlich oder privat sein soll. Aber das zu erklären würde doch erheblich den Rahmen dieses lieblos dahin geklierten Blogbeitrages zu Apple's iCal und Google's Calendar sprengen.

PS: To whom it may concern, habe ich hier mal kurz aus der Wikipedia abgeschrieben was CalDAV eigentlich ist.

**Informationen:**
**- CalDAV** ist ein Vorhaben für ein Standard-Protokoll, das es ermöglicht, auf Kalenderdateien via WebDAV zuzugreifen. Die Aufgabe von CalDAV ist es, Ereignisse wie Treffen, Versammlungen sowie die Freizeit zu verwalten und über HTTP zu publizieren. Jedes Ereignis wird im iCalendar-Format dargestellt. Demzufolge kann jeder Webbrowser ein heruntergeladenes Ereignis darstellen. Die Daten werden als Dateien in einer WebDAV-Umgebung verwaltet und synchronisiert. Die drei großen unter den Kalender-Verwaltungssoftwaren unterstützen CalDAV. Das wären Mozilla Sunbird (Lightning), Novell Evolution und nun auch Apples iCal ab OS X 10.5

**- Google Kalender** ist ein von Google zur Verfügung gestellter Webkalender. Zur Anmeldung bei Google Kalender ist ein Google-Konto erforderlich, welches man automatisch mit der Einrichtung einer E-Mail-Adresse bei Google Mail bekommt. Alternativ kann man sich mit seiner bestehenden E-Mail-Adresse bei Google anmelden. Das Produkt steht nun auch in deutscher Sprache zur Verfügung.

**Ressource:**

- [Google Calendar CalDAV Support  (Link nicht mehr verfügbar)](http://www.google.com/support/calendar/bin/answer.py?hl=en&amp;answer=99358)
