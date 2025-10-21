---
title: Was tun? Sprach Zeus
slug: was-tun-sprach-zeus
date_published: 2011-09-20T13:01:13.000Z
date_updated: 2018-08-22T09:38:31.000Z
---

Ich weiß auch nicht mehr, was ich noch so tun könnte. Ich habe mich mittlerweile *tot-optimiert*. Gemeint ist die Ladezeit meiner Website. Seit zwei Wochen sitze ich so rum, und beschwöre den Loadspeed-Gott, er möge doch meine Website schneller machen. Aber nichts passiert.

Zwar weist mir Google [Page Speed Online (archiviert)](http://web.archive.org/web/20150617220250/http://pagespeed.googlelabs.com:80/pagespeed/) mittlerweile einen recht okayen Wert von 92 Punkten aus, aber gefühlt ist das immer noch alles viel zu wenig. Der fette Test von [Webpagetestorg](http://www.webpagetest.org/result/111001_HF_1RYPT/1/pagespeed/) nennt mir einen Page Speed "1.12 Score: **93/100***" Punkten. Laut dem [Content Breakdown](http://picdump.thafaker.de/2011/10/pagebreak.png) ist es eindeutig Javascript, was meine Seite langsam macht und was am längsten lädt.
![pagespeed_92](//picdump.thafaker.de/2011/09/pagespeed_92-580x92.png)

Ich habe mittlerweile meine Datenbank optimiert, das `WP Super Cache` Plugin installiert, [Caching-Variablen](http://mainboarder.de/artikel/3247/rollout-neuer-funktionen-bei-begrenztem-traffic.html) in die `.htaccess` Datei meines Webservers eingetragen und viele Plugins entfernt sowie die Sidebar entschlackt: doch nichts! Ebenfalls habe ich mich mit CDNs beschäftigt und bin auf das kostenlose [Google App Engine CDN (archiviert)](http://web.archive.org/web/20120615220218/http://mainboarder.de:80/artikel/3119/erfahrungsbericht-google-appspot-als-cdn.html) aufgesprungen, dort lagern einige meiner statischen Dateien. Doch all diese Maßnahmen haben irgendwie nicht wirklich viel gebracht und ich frage mich nun, was ich noch tun könnte?
