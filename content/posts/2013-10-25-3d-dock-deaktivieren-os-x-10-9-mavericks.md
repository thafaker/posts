---
title: 3D Dock deaktivieren OS X 10.9 Mavericks
slug: 3d-dock-deaktivieren-os-x-10-9-mavericks
date_published: 2013-10-25T19:39:16.000Z
date_updated: 2018-08-22T09:38:43.000Z
---

Mavericks schön und gut, vor allem auch [kostenlos](__GHOST_URL__/download-os-x-10-9-mavericks-kostenlos-4-free/), aber: leider funktioniert der alte [Terminal Befehl aus 10.5](__GHOST_URL__/to-remind-mac-os-x-105-leopard-3d-dock-abschalten/) nicht mehr, um das 3D-Dock zu deaktivieren und auf 2D von Tiger zu schalten. Was bisher immer ging. "Rückschritt" schreien die einen, "Dock an die Seite schieben" die anderen. 

Denn das ist, was funktioniert: an eine der beiden Seitenränder verschoben, wird das Dock 2D, nur unten eben nicht. Und unten nutzen es viele. Seltsam.

    thafaker$ defaults write com.apple.dock no-glass -boolean YES; killall Dock

Ansonsten wird auch schon im Apple-Forum drüber diskutiert...
[https://discussions.apple.com/thread/5467442?tstart=0 (Link nicht mehr verfügbar)](https://daw.apple.com/cgi-bin/WebObjects/DSAuthWeb.woa/wa/login?appIdKey=529eb2b096d5a3d54162171f0f29ba797e602812660013123243e58bc7bedf56&amp;path=%2F%2Fthread%2F5467442%3Ftstart%3D0&amp;instanceId=US&amp;baseURL=https://discussions.apple.com&amp;language=US-EN)

Der Terminal-Befehl funktionierte schon in den letzten Beta-Releases nicht...
[http://www.tekrevue.com/2013/10/10/p...s-x-mavericks/](http://www.tekrevue.com/2013/10/10/popular-2d-dock-terminal-command-wont-work-os-x-mavericks/)

Ein Jammer, es scheint das Ende von Apple als cooler Firma zu sein.

Es ist leider Zeit für eine neue Kategorie namens: [**Mavericks Sucks** (archiviert)](http://web.archive.org/web/20131030054837/http://thafaker.de/tag/mavericks-sucks/)!
