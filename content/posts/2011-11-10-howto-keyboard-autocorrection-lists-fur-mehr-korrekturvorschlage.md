---
title: [HowTo] "Keyboard Autocorrection Lists" für mehr Korrekturvorschläge
slug: howto-keyboard-autocorrection-lists-fur-mehr-korrekturvorschlage
date_published: 2011-11-10T15:57:18.000Z
date_updated: 2018-08-22T09:38:27.000Z
---

Bitte beachtet folgenden [Kommentar](__GHOST_URL__/howto-keyboard-autocorrection-lists-fur-mehr-korrekturvorschlage/#comment-40841). Schon wieder ein Erweiterungs-iOS 5 Hack. Diesmal geht es um die Verbesserung der Autokorrektur. Die einzeln vorgeschlagene Wortkorrektur ist meist nicht die richtig: mit dem Hack kann man das wie auf Android bekannt erweitern, sodass man mehrere Worte als Vorschlag erhält und diese durch Antippen auswählen kann.
[![ios5_tastatur](//picdump.thafaker.de/2011/11/ios5_tastatur-580x435.jpg)](http://picdump.thafaker.de/2011/11/ios5_tastatur.jpg)
[Sonny Dickson (archiviert)](http://web.archive.org/web/20250905043545/https://twitter.com/) hat nach Angaben von [9to5Mac](http://9to5mac.com/2011/11/09/ios-5-hides-an-android-like-autocorrect-keyboard-bar-heres-how-to-enable-it/) in den Untiefen von iOS 5 eine Möglichkeit entdeckt, die Rechtschreibkorrektur zu verbessern. Apple hat sie in sein neues mobiles Betriebssystem integriert, jedoch nicht freigeschaltet. Die Manipulation scheint auch mit dem iPad zu funktionieren, da Dickson einen passenden Screenshot veröffentlicht hat.

Wer die Autokorrekturliste aktivieren will, sollte nach Dicksons Anleitung zunächst ein iTunes-Backup seines Geräts machen und dieses mit der kostenlosen Software [iBackupbot](http://www.icopybot.com/itunes-backup-manager.htm) (Mac und Windows) bei eingestecktem iPhone öffnen.

Nach Angaben von Dickson sollte in der Datei "`com.apple.keyboard.plist`" der Eintrag "`<key>KeyboardAutocorrectionLists</key><string>YES</string>`"

eingefügt werden.

Diverse Anwender berichten von einem Manko der modifizierten Textkorrektur. So muss jedes eingetippte Wort bestätigt werden, bevor es auf dem Bildschirm erscheint.

**Kurzanleitung**

Die Kollegen von [9to5Mac](http://9to5mac.com/2011/11/09/ios-5-hides-an-android-like-autocorrect-keyboard-bar-heres-how-to-enable-it/) haben direkt einen Tipp parat, wie sich diese Zusatzfunktion ganz ohne [Jailbreak (archiviert)](http://web.archive.org/web/20111102144114/http://www.macerkopf.de:80/tag/jailbreak.html) aktivieren lässt.

- Zunächst müsst ihr die Software [iBackupBot](http://www.icopybot.com/download.htm) herunterladen und installieren
- Dann legt ihr über iTunes ein aktuelles Backup eures iPhone, iPad oder iPod touch an
- iBackupBot starten, die zuvor angelegte Backup-Datei finden und in iBackupBot laden
- Im Backup findet ihr die Datei com.apple.keyboard.plist im Verzeichnis /Library/Preferences/
- Diese öffnet ihr und fügt den Code "<key>KeyboardAutocorrectionLists</key><string>YES</string>" (ohne die "") hinzu
- Abspeichern und das modifizierte Backup für euer iOS Gerät wiederherstellen

An dieser Stelle sei gesagt, dass sämtliche Veränderungen am iOS 5 Programmcode auf eigene Verantwortung geschehen. Ersten Rückmeldungen zufolge, soll die Zusatzfunktion für die Autokorrektur noch instabil laufen.

*Um auf dem Laufenden zu bleiben, könnt ihr uns auf [Twitter](http://twitter.com/#%21/thafakerde) folgen oder die [Facebook-Seite](http://de-de.facebook.com/pages/thafaker-auf-Beton/154600141278763) besuchen.*
