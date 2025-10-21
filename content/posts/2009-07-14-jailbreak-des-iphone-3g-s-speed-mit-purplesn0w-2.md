---
title: Jailbreak des iPhone 3G S (Speed) mit purplesn0w
slug: jailbreak-des-iphone-3g-s-speed-mit-purplesn0w-2
date_published: 2009-07-14T21:45:28.000Z
date_updated: 2018-08-22T09:39:22.000Z
---

[**Update**] Benm.at haben nun auch den [**Unlock mit purplesn0w** (archiviert)](http://web.archive.org/web/20090716173757/http://www.benm.at:80/2009/07/14/howto-iphone-3gs-unlock-mit-purplesn0w/) für das iPhone 3G S.

[...] Die Schneelage wird zusehends unübersichtlicher: Auf **redsn0w** und **ultrasn0w** antwortet [geohot mit seiner eigenen Entsperrlösung](http://iphonejtag.blogspot.com/2009/07/make-it-ra1n-im-makin-it-sn0w.html) für das iPhone 3GS, die auf den Namen purplesn0w hört. purplesn0w möchte dabei eine [effektivere und problemfreiere Entsperrung](http://iphonejtag.blogspot.com/2009/07/purplesn0w-technicals.html) des iPhone 3GS bieten als ultrasn0w, ist derzeit aber noch in einem sehr jungen Stadium und setzt vorerst ein legitim aktiviertes iPhone 3GS voraus - die Hacktivierungs-Möglichkeit soll aber schon bald ergänzt werden. com.geohot.purplesn0w findet sich zur Installation in Cydia, wenn `apt.gehohot.com` als Quelle hinzugefügt worden ist. [...]

**Achtung: Noch befindet sich purplesnow in der Betaphase, somit kann es noch zu Problemen kommen.

Bei unseren ersten Tests, konnte wir den Unlock nicht erfolgreich durchführen.**

***Aktuell sollte man lieber noch etwas warten, bis GeoHot die ersten Kinderkrankheiten gefixt hat.*
**

GeoHots purplensn0w nutzt das iPhone eigene Unlock-Ticketsystem und soll so einige Vorteile mit bringen, wie:

- keine WLAN Probleme
- kein Daemon (Hintergrundprozess), somit weniger Batterieverbrauch

> No new iPhones are really unlocked, activation creates a ticket allowing the baseband to be used with that sim. The lockstate of the phone really lies on apples servers. Unlocked is auth all sims. Locked is auth AT&T sims only. Fortunately this ticket system provides an easy way to deliver the payload and reexecute the patched code all in one. And since the ticket is already delivered on baseband resets, theres no need to write another daemon to hog battery. I use the daemon already designed for this, lockdownd. A patch to commcenter gets it to run the payload on ticket delivery. And a patch to your activation record contains the payload. So using existing apple machinery, I unlock when needed.
> In retrospect, I should’ve just patched commcenter to send the payload. Then hacktivation would work no problem. Oh well, tomorrow is another day. I’ll add hacktivation support then.

Diese Anleitung zeigt, wie ihr euer iPhone 3GS mittels purplesn0w, vom SIM Lock befreit werden kann.

### ****Voraussetzungen****

- iPhone 3GS mit SIM Lock;)
- installierte 3.0er Firmware inkl. offizieller Aktivierung

![Weiterlesen...](//picdump.thafaker.de/benm.at/wp-includes/js/tinymce/plugins/wordpress/img/trans.gif)
********Anleitung********

********1.Aktivierung********

Aktiviert euer iPhone wie üblich mit iTunes und der orginal SIM Karte z.B. von T-Mobile********
********

**1. Jailbreak mit purplera1n
**

Nun müsst ihr falls noch nicht geschehen, den Jailbreak mit purplera1n durchführen.

Da es das für Windows und OS X gibt, hier die passenden Anleitungen:

[purplera1n Anleitung (Mac OS X) (archiviert)](http://web.archive.org/web/20090709024853/http://www.iphone-notes.de:80/2009/07/05/anleitung-howto-3gs-jailbreak-mit-purplera1n-mac/)
[purplera1n Anleitung (Windows) (archiviert)](http://web.archive.org/web/20090705194053/http://www.iphone-notes.de:80/2009/07/03/anleitung-howto-3gs-jailbreak-mit-purplera1n-win/)

**3. Unlock**

3.1 Nach erfolgreichen Jailbreak, und Cydia Installation (mit Freeze), startet ihr Cydia.
![bild-2](//picdump.thafaker.de/benm.at/wp-content/uploads/2009/01/bild-2.png)
3.2 Nun auf den Menüpunkt “Verwalten”, dort auf “Quellen” und dann oben auf “Bearbeiten” & Hinzufügen “klicken”.

[![IMG_0003](//picdump.thafaker.de/benm.at/wp-content/uploads/2009/06/img_0003-200x300.PNG)](http://www.iphone-notes.de/wp-content/uploads/2009/06/IMG_0003.PNG)[![IMG_0004](//picdump.thafaker.de/benm.at/wp-content/uploads/2009/06/img_0004-200x300.PNG)](http://www.iphone-notes.de/wp-content/uploads/2009/06/IMG_0004.PNG)[![img_0046](//picdump.thafaker.de/2009/07/img_0046-200x300.PNG)](http://picdump.thafaker.de/2009/07/img_0046.PNG)

Dort **apt.geohot.com **eintragen und mit “Quelle hinz…” bestätigen. Nun läd Cydia die aktuellen Sourceinformationen,

danach, unter Änderungen das Paket “com.geohot.purplesn0w” auswählen und installieren.

[![img_0045](//picdump.thafaker.de/2009/07/img_0045-200x300.PNG)](http://picdump.thafaker.de/2009/07/img_0045.PNG)[![img_0047](//picdump.thafaker.de/2009/07/img_0047-200x300.PNG)](http://picdump.thafaker.de/2009/07/img_0047.PNG)

3.3

Nach der Installation, landet ihr mit “Zu Cydia zurückkehren” wieder in Cydia, nun das iPhone einmal ausschalten und mit eurer SIM Karte neustarten.

[[![img_0050](//picdump.thafaker.de/2009/07/img_0050-200x300.PNG)](http://picdump.thafaker.de/2009/07/img_0050.PNG)](http://www.iphone-notes.de/wp-content/uploads/2009/07/img_0050.PNG)[![IMG_0013](//picdump.thafaker.de/benm.at/wp-content/uploads/2009/06/img_0013-200x300.PNG)](http://www.iphone-notes.de/wp-content/uploads/2009/06/img_0013.PNG)

**Nach diesem Vorgang habt ihr ein komplett entsperrtes / geunlocktes iPhone 3GS.**

([via (archiviert)](http://web.archive.org/web/20090715235019/http://www.fscklog.com:80/2009/07/purplesn0w-geohots-software-unlock-f%C3%BCr-das-iphone-3gs.html)) ([via (archiviert)](http://web.archive.org/web/20090715223307/http://www.iphone-notes.de:80/2009/07/14/anleitung-howto-3gs-unlock-per-purplesn0w/))
