---
title: Wo befindet sich "FinderSyncAPIExtension"? [UPDATE]
slug: wo-befindet-sich-findersyncapiextension
date_published: 2015-04-19T06:19:10.000Z
date_updated: 2018-08-22T09:39:22.000Z
tags: update, osx, os x, yosemite, apple, 10.3.3, FinderSyncAPIExtension, updated
---

Als ich heute meinen Mac startete, erhielt ich unter OS X folgende Fehlermeldung.

[![error FinderSyncAPIerror FinderSyncAPIExtension](/content/images/2015/04/findersyncapiextension.png)

Aktive Programme waren zu dieser Zeit nur die Mai.app, sonst nichts. Hat jemand diese Fehlermeldung erhalten? Hängt sie mit 10.3.3 oder deren Zusatz-Update zusammen? Auf der japanischen *Apple-Support-Seite* findet sich [folgender Eintrag](https://discussionsjapan.apple.com/thread/10160520), der auf gestern datiert, also ebenfalls brandneu ist.

Fragen über Fragen. Wer kann helfen?

Nach einem Neustart erschien diese Fehlermeldung nicht erneut.

---

[**UPDATE**] Dies ist eine *Extension* von [Google Drive](https://discussions.apple.com/thread/6890881). Wenn man diese Meldung erhält, kann man die fehlende Extension hier finden:

`/Applications/Google Drive.app/Contents/PlugIns/FinderSyncAPIExtension.appex/ Contents/MacOS/FinderSyncAPIExtension`

und ihm das mitteilen. Es hat also nichts mit den neuerlichen Updates zu tun, scheint aber dennoch nur unter Yosemite aufzutauchen. Hier ist eher Google in der Pflicht.
