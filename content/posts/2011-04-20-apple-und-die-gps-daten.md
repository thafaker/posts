---
title: Apple und die GPS-Daten [Update]
slug: apple-und-die-gps-daten
date_published: 2011-04-20T16:01:33.000Z
date_updated: 2018-08-22T09:38:38.000Z
---

[**Update #2**] Apple hat heute ein Statement zu den Vorwürfen veröffentlicht, [hier](__GHOST_URL__/apples-pressemitteilung-zum-location-data-problem/) berichten wir darüber.

[**Update #1**] [Hier](__GHOST_URL__/apple-und-die-gps-daten-update/) gibt es neuere Aspekte und Informationen zu diesen Vorwürfen.

[**Original**] Es ist ja nun [seit einiger Zeit bekannt](__GHOST_URL__/apple-sammelt-standortdaten-heimlich/), das Apple auf all seinen sich im Umlauf befindlichen iPhones (und dem 3G-iPad) die lokalisierten GPS-Daten speichert, das iPhone also heimlich spionieren lässt, wo es sich gerade befindet und in welcher "Qualität". Auf all den vielen millionen Geräten weltweit. Dies hat den Hintergrund, dass Apple anhand dieser Daten eine eigene Lokalisierungsdatenbank betreibt und aktualisiert, um beispielsweise auch bei per Wlan verbuchten Geräten den Standort bestimmen zu können sowie um infrastrukturelle Informationen wie die Qualität des Funk- oder GPS-Signals sowie die Kompassdaten in der jeweiligen Gegend zu erfahren.
[![southofengland](//picdump.thafaker.de/2011/04/southofengland.png)](http://picdump.thafaker.de/2011/04/southofengland.png)

Nun aber geht ein Aufschreih durch das Internet, weil O'Reilly eine Datei auf dem iPhone (oder vielmehr in der iTunes Datensicherung) entdeckt hat, welche man ganz simple mit einer Software auslesen kann. Es ist eine unverschlüsselte Datenbankdatei mit dem Namen `consolidated.db`. Diese Datei wird seit iOS 4.X erstellt und aufgezeichnet.

Hat man Zugang zu dem Computer mit dem das Gerät gesynct wird, hat man auch Zugang zu dieser Datei.

Jedoch sei gesagt, dass diese Daten allein nicht verraten wer das jeweilige Gerät verwendet hat, noch was mit dem Gerät getan wurde. Sie zeigen “nur”, wo das Gerät wann war und welche Bedingungen dort vorherrschten. Beispielsweise wie gut das Funksignal oder wie stark das Magnetfeld war bzw. ob der Kompass funktioniert hat (= nur wenn eine App mit GPS verwendet wurde).

Jeder Mobilfunkanbieter sammelt solche Daten, aber jene haben sie in  ihrer Firma hinter Firewalls und vor dem Endbenutzer sicher verwahrt  (unterstelle ich einfach mal). Apple aber öffnet jedem, der Zugang zu  deinem iPhone oder Mac hat, Tür und Tor um ein recht lückenloses  Bewegungsbild zu erstellen, was sonst niemals möglich ist - ohne unsere  Einwilligung. Dies ist ein großes Problem und im Gegensatz zu anderen  Firmen schon grob fahrlässig und in vielen Augen sehr frech, wenn nicht  strafbar.

Mit einer kleinen kostenlosen App für OS X namens [**iPhoneTracker** (archiviert)](http://web.archive.org/web/20220529090803/https://web.archive.org/web/20110422095931/http://petewarden.github.com/iPhoneTracker/), die **O`Reilly** bereitgestellt hat, lässt sich diese Datenbank aus einem in iTunes gespeicherten iOS-Backup auslesen.

Auf meinem iMac mit verschlüsseltem iPhone Backup konnte das Programm die Daten nicht auslesen und darstellen, die Software blieb beim Ladezeichen und der Landkarte stehen. Nach einem Entschlüsseln des iPhone-Backups jedoch, konnte die Software in kürzester Zeit meine Datei auslesen und darstellen. Verschlüsselt also eure Backups.

**Download**

- [iPhoneTracker (archiviert)](http://web.archive.org/web/20110501055748/http://static.openheatmap.com.s3.amazonaws.com/iPhoneTracker.app.zip)
