---
title: Firefox 9 als Download verfügbar
slug: firefox-9-als-download-verfugbar
date_published: 2011-12-20T10:30:46.000Z
date_updated: 2018-08-22T09:38:25.000Z
---

Und wieder ein Versionssprung weiter, langsam verliert man ja doch etwas den Überblick. Im Laufe dieses Dienstags will Mozilla den Firefox 9 offiziell freigeben. Dieser kann jedoch bereits schon jetzt auf deren(™) Servern heruntergeladen werden.

Die wichtigste Neuerung im neuen Firefox heißt Type Inference (TI) und soll dafür sorgen, dass Javascript schneller ausgeführt werden kann. Javascript arbeitet mit dynamischen Typen, so dass ein JIT-Compiler Code für alle möglichen Typen erzeugen muss. Das macht zwar  die Entwicklung von Javascript-Programmen recht einfach, verlangsamt jedoch die Ausführung von Javascript verglichen mit Sprachen, die mit statischen Typen arbeiten ungemein. Mit der neuen Funktion Type Inference generiert die Javascript-Engine Spidermonkey Typinformationen für Variablen, die in Javascript-Programmen genutzt werden. Dazu wird zum einen eine Code-Analyse vorgenommen, zum anderem werden die Werte der Variablen während der Programmausführung überwacht. Die so gesammelten Informationen kann Jaegermonkey, der JIT-Compiler in Firefox 9, nutzen, um effizienteren Code zu erstellen. Type Inference wird von Firefox 9 standardmäßig genutzt und soll in Javascript-Benchmarks wie Kraken und V8 rund 30 Prozent mehr Leistung bringen. Laut Mozilla laufen Webseiten mit umfangreicheren Javascript-Code um ca. 50 Prozent schneller als vorher.

[![](//picdump.thafaker.de/2011/12/Firefox9screen-580x431.png)](__GHOST_URL__/firefox-9-als-download-verfugbar/firefox9screen/)

Weitere Neuheiten sind außerdem:

### Vollbildmodus

Firefox 9 bietet eine experimentelle Unterstützung für das Vollbild-API des W3C. Damit können auf Nutzerwunsch per Javascript einzelne HTML-Elemente im Vollbild dargestellt werden. Das ist vor allem bei Wiedergabe von Videos oder für Spiele sehr praktisch.Der Vollbildmodus in Firefox 9 ist jedoch noch nicht standardmäßig aktiviert. Das soll erst mit Version 10 der Fall sein, welche für Anfang 2012 geplant ist.

### Neue CSS-Funktionen

Firefox 9 unterstützt die CSS-Eigenschaft [font-stretch](https://developer.mozilla.org/en/CSS/font-stretch), um normale, gestauchte oder gestreckte Versionen einer Schrift zu verwenden. Zudem wurde die Unterstützung für [text-overflow](https://developer.mozilla.org/en/CSS/text-overflow) verbessert, so dass für die linke und rechte Kante ein unterschiedliches Verhalten festgelegt werden kann.

### Angepasst für Mac OS X Lion

Firefox 9 wurde ebenfalls besser an Mac OS X 10.7 alias Lion angepasst. Das betrifft nicht nur für die Optik: Es werden ebenfalls die neuen Zwei-Finger-Gesten zur Navigation per Wisch unterstützt. Beim Einsatz auf Mehrmonitorplätzen soll der Einsatz besser sein

### JS-Interface für Do Not Track

Der Einsatz des mit Firefox 7 eingeführten Do-Not-Track-Headers kann nun auch per Javascript abgefragt werden. Entwickler können so feststellen, wenn sich ein Nutzer gegen die Profilerstellung für verhaltensbezogene Werbung ausspricht.

### XmlHttpRequests verbessert

Für XHR (XmlHttpRequests) unterstützt Firefox 9 Chunking. So können große Datenmengen, die per Ajax angefragt werden, in kleinen Portionen verarbeitet werden, was Webseiten schneller machen soll. Zudem kann mit "moz-json" ein neuer Antwortyp angegeben werden. Damit kann das XMLHttpRequest-Objekt JSON-Strings automatisch parsen, so dass XMLHttpRequest ein fertiges Javascript-Objekt zurückgibt.

[![](//picdump.thafaker.de/2011/12/Screen-Shot-2011-11-11-at-12.10.44-AM-580x346.jpg)](__GHOST_URL__/firefox-9-als-download-verfugbar/screen-shot-2011-11-11-at-12-10-44-am/)Firefox 9 ist für [Windows](http://www.mozilla.org/en-US/products/download.html?product=firefox-9.0&amp;os=win&amp;lang=en-US), [Linux](http://www.mozilla.org/en-US/products/download.html?product=firefox-9.0&amp;os=linux&amp;lang=en-US) und [Mac OS X](http://www.mozilla.org/en-US/products/download.html?product=firefox-9.0&amp;os=osx&amp;lang=en-US) verfügbar und kann ab sofort heruntergeladen werden.

**Quelle**: [golem.de](http://www.golem.de/1112/88552.html)

---

*Um auf dem Laufenden zu bleiben, könnt ihr uns auf [Twitter (archiviert)](http://web.archive.org/web/20250905043545/https://twitter.com/) folgen oder die [Facebook-Seite](http://de-de.facebook.com/pages/thafaker-auf-Beton/154600141278763) besuchen.*

---
