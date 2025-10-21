---
title: Status Notifier zum Anzeigen neuer SMS oder Mail in der Taskbar des iPhone
slug: status-notifier-zum-anzeigen-neuer-sms-oder-mail-in-der-taskbar-des-iphone-2
date_published: 2009-07-14T16:40:26.000Z
date_updated: 2018-08-22T09:39:22.000Z
---

Als ich neulich mal eine (leider etwas ältere) Top 10 der nützlichsten Cydia-Apps durchklickte, las ich vom [**Taskbar-Notifier** (archiviert)](http://web.archive.org/web/20080714043144/http://code.google.com:80/p/taskbar-notifier/). Neben verpassten Anrufen kann der Taskbar Notifier unter anderem auf ungelesen SMS-Nachrichten sowie neu eingegangene eMails aufmerksam machen, ohne das iPhone *Entriegel* zu müssen.

[![status-notifier](//picdump.thafaker.de/2009/07/status-notifier.PNG)](http://picdump.thafaker.de/2009/07/status-notifier.PNG)

Als ich das Ding nun installieren wollte, stellte sich heraus, dass eben jener Taskbar-Notifier seit *iPhone OS Version 1.1.3* nicht mehr weiter entwickelt wird, was mich ziemlich sehr annervte, soweit, und irgendwie fand ich auch keine richtige Alternative. Bis ich dann heute plötzlich in einem Forum las, das man doch einfach mal den [**Status-Notifier** (archiviert)](http://web.archive.org/web/20090306173440/http://code.google.com:80/p/statusnotifier/) ausprobieren sollte. Und siehe da, die Sache läuft mehr als rund. *Jawoll*.

Selbiger ist via Cydia  (über die Suche "Notifier") in der ModMyi.com Quelle zu finden.

**Folgende Informationen werden angezeigt**:

- Unread Email
- Missed call/voicemail
- Calendar alerts
-  SMS: MobileSMS / iRealSMS / biteSMS
- MMS: SwirlyMMS
- IM: BeejiveIM / Fring / Palringo / AOL AIM
- RSS: NetNewsWire, Byline
- Reminder (vibration/sound)
- Customizable options
- Silent mode (ringer off)

[**Update**] Allerdings wird für den Status-Notifier nur eine Kompativilität für iPhone OS 2.X angegeben, sodas ich den "Notifier" genannten Dienst (Version 3.0) von BigBoss probierte, der meiner Meinung nach genau das selbe kann wie der Status-Notifier. Er braucht ebenso keinen extra/aktiven Daemon (Dienst) im Hintergrund und schont somit den Akku.

> This adds taskbar notifications to your statusbar for things like missed calls, voicemail, and mail. Implemented as a light weight mobile substrate plugin, this can be done without any extra daemon process running and draining your battery.

**Repository:**
BigBoss: `http://apt.bigboss.us.com/repofiles/cydia/`
STE Packaging: `http://repo.smxy.org/iphone-apps/`
