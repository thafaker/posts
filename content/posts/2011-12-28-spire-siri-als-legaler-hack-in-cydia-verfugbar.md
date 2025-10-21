---
title: "SPIRE: SIRI ALS LEGALER HACK IN CYDIA VERFÜGBAR [UPDATE: PROXY LISTE]"
slug: spire-siri-als-legaler-hack-in-cydia-verfugbar
date_published: 2011-12-28T11:44:33.000Z
date_updated: 2018-08-22T09:38:25.000Z
---

---

[**UPDATE**] Ich habe mich mal auf die Suche nach einer Siri-Proxy-Liste gemacht... und diese hier gefunden.

---

WERBUNG
!function(d, s, id) {
    var js, pjs = d.getElementsByTagName(s)[0];
    if (d.getElementById(id)) return;
    js = d.createElement(s);
    js.id = id;
    js.src = "http://player-services.goviral-content.com/embed-code/index/find?placementVersionId=169349451334851202369755";
    pjs.parentNode.insertBefore(js, pjs);
}(document, 'script', 'gv_script_169349451334851202369755');
---

Spire Proxy Host-Liste (wird regelmäßig aktualisiert)

    http://iPhone-MY.com  (funktioniert noch nicht richtig)
    https://siri.cd-team.org (Free – leider überfüllt)
    sirikeys.com vermietet Plätze für 5 Euro im Monat [vorerst Finger von lassen!]
    http://lowkey.net.my/ (Free – leider überfüllt)
    https://97.188.76.85:443 (Free – voll o. funkt. nicht)
    http://siri.schiefen.ws (Free – voll o. funkt. nicht)
    http://bloominggamers.com/siri/ (Free – voll o. funkt. nicht)
    https://205.185.119.17:2000 (Free – voll o. funkt. nicht)
    http://6fa5932a.miniurls.co (Free – voll o. funkt. nicht)
    http://iJailbreak.com (Free – voll o. funkt. nicht)
    https://188.120.232.184:443 (Free – voll o. funkt. nicht)
    https://192.453.201:3544 (Free – voll o. funkt. nicht)
    http://www.spireproxy.co.uk/ (Free – voll o. funkt. nicht)
    

WICHTIG: Beachtet das viele solcher Angebote schon bald im Netz anzufinden sein werden, der Großteil davon ist nicht zu empfehlen und wollen euch nur das Geld aus der Tasche ziehen!

---

[**ORIGINAL**] Mit [Spire (archiviert)](http://web.archive.org/web/20120108031801/http://blog.chpwn.com:80/post/14689740472?)[![Siri Logo](//picdump.thafaker.de/2011/12/Bildschirmfoto-2011-12-28-um-12.38.12.png)](http://picdump.thafaker.de/2011/12/Bildschirmfoto-2011-12-28-um-12.38.12.png) ist die erste legale Siri-Portierung in Cydia kostenlos verfügbar. In der am 15. Dezember veröffentlichten “zweiten Version” von iOS 5.0.1 (hier hat Apple stillschweigend Dinge verändert und es nicht öffentlich bekannt gegeben) sind die für Siri benötigten Systemdateien (wohlmöglich absichtlich) nicht mehr verschlüsselt, was eine legale Extrahierung und folgende Portierung des intelligenten Assistenten erst möglich macht.

Wie jedoch schon zuvor kann auch der portierte Siri nur mit einem echten iPhone-4S-Identifier mit Apples Servern kommunizieren. Die Verwendung mit einem Siri-Proxy-Server ist aber durchaus möglich, wenn auch datenschutzrechtlich bedenklich (deine Daten werden über fremde Computer geleitet und könnten dort ausgelesen werden).

> However, Spire is not a complete solution. Apple still requires authorization to use Siri, so information from an iPhone 4S is still required. To insert this information, Spire allows you to enter your own proxy server address. By using this (ancient) SiriProxy fork, you can setup a proxy using your own iPhone 4S to insert the needed information reasonably easily. Other solutions for proxying Siri will be listed here as they are developed — perhaps that sort of proxy might be included in the main SiriProxy repository.

Spire setzt iOS 5 voraus und ist nur etwas mehr als einen Megabyte groß. Im Zuge der Installation von Spire werden die knapp 100 Megabyte an Siri-Dateien legal und direkt von den Apple-Servern nachgeladen. Man sollte sein iPhone also mit dem WLan verbunden haben, damit die 100 MB nicht zu sehr auf die mobile Datenrate schlagen.

Die einzig sinnvolle Möglichkeit für Siri auf einem iPhone 4 oder iPod touch ist also, einen eigenen Proxy-Server zu betreiben, der die Daten vom eigenen iPhone entgegen nimmt und weiter an Apple sendet. Dann hat man die Gewissheit der Datensicherheit und niemand Fremdes kann in die Daten eingreifen, außer man selbst. Leider benötigt man dafür diesen iPhone 4S Identifier, den nur Besitzer eines iPhone 4S haben - diesen dann aber teilen können :-) Wenn ihr also jemanden mit einem *echten* iPhone 4S kennt, kann euch dieser seine iPhone 4S Identifier mitteilen und fertig ist die Laube. Leider kenne ich niemanden mit einem iPhone 4S sodass ich auch keinen Proxy testen und kein HowTo darüber schreiben kann.

**ACHTUNG**: Wenn ihr Spire via Cydia installiert habt und euch wundert, warum sich noch immer die normale Sprachsteuerung öffnet: ihr müsst Siri erst aktivieren, so wie auf einem iPhone 4s auch. Ihr geht also auf EINSTELLUNGEN --> ALLGEMEIN --> SIRI und aktiviert dort Siri und nehmt eure gewünschten Einstellungen vor.
[![siri_setting](//picdump.thafaker.de/2011/12/siri_setting-386x580.png)](http://picdump.thafaker.de/2011/12/siri_setting.png)[![proxy_down](//picdump.thafaker.de/2011/12/proxy_down-386x580.png)](http://picdump.thafaker.de/2011/12/proxy_down.png)

---

---

Weiter im Klartext-Karton
[![spire_2](//picdump.thafaker.de/2011/12/spire_2-386x580.png)](http://picdump.thafaker.de/2011/12/spire_2.png)[![spire_1](//picdump.thafaker.de/2011/12/spire_1-386x580.png)](http://picdump.thafaker.de/2011/12/spire_1.png)
Wie man nun einen [eigenen Proxy](https://github.com/plamoni/SiriProxy) aufsetzt, erzählen wir euch in einem weiteren How To.**SIRI 4 ALL** ;-)

Übrigens ist es mit diesem oben verlinken Proxy möglich, eigene Plugins zu programmieren und Siri dadurch völlig neue Fertigkeiten beizubringen. Als Beispiel sei hier die [Fernsteuerung der eigenen Heizung](http://www.youtube.com/watch?v=AN6wy0keQqo) gezeigt, oder, die Möglichkeit den eigene Mac zu steuern.

Siri beizubringen wie man Tweets via Twitter verschickt, ist auch [schon](http://www.youtube.com/watch?v=kM7Th-zcCSc) geschehen :-)

[Warning about h1siri and "public" SiriProxy servers
](http://www.youtube.com/watch?v=Y_Q6PfxBSbA&amp;feature=youtu.be)

---

*Um auf dem Laufenden zu bleiben, könnt ihr uns auf [Twitter (archiviert)](http://web.archive.org/web/20250905043545/https://twitter.com/) folgen oder die [Facebook-Seite](http://de-de.facebook.com/pages/thafaker-auf-Beton/154600141278763) besuchen.*

---
