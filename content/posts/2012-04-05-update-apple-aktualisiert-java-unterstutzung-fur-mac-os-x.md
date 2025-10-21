---
title: [Update] Apple aktualisiert Java-Unterstützung für Mac OS X [NACHTRAG]
slug: update-apple-aktualisiert-java-unterstutzung-fur-mac-os-x
date_published: 2012-04-05T08:54:24.000Z
date_updated: 2018-08-22T09:38:11.000Z
---

Apple hat zwei Updates für die Java-Unterstützung in Lion (Mac OS X 10.7) und Snow Leopard (Mac OS X 10.6) nachgereicht. Sowohl das ["Java for Mac OS X 10.6 Update 7"](http://support.apple.com/kb/DL1516) (knapp 80 MByte) als auch die ["Java for OS X Lion 2012-001"](http://support.apple.com/kb/DL1515)-Aktualisierung (rund 67 MByte) beheben Sicherheitslücken in Java 1.6.0_29, **die seit Längerem bekannt sind und unter Windows bereits geschlossen waren**. ((Oh man, das nimmt kein gutes Ende mehr mit Apple))

Die Updates dürften eine Reaktion auf eine seit einigen Tagen kursierende neue Mac-Malware sein, die einen Fehler in Java ausnutzten, den Apple bislang nicht gepatcht hatte. Die Java-Unterstützung für Mac OS X erreicht mit den beiden Aktualisierungen nun [Version 1.6.0_31](http://www.oracle.com/technetwork/java/javase/releasenotes-136954.html). Zu den geschlossenen Lücken gehören ein ["Arbitrary Code Execution"-Bug](https://en.wikipedia.org/wiki/Arbitrary_code_execution) und ein Fehler, der es erlaubte, Programme außerhalb der Java-Sandbox auszuführen.

Das Java für OS X 2012-001-Update 1 erhöht die Kompatibilität, Sicherheit und Verlässlichkeit durch die Aktualisierung von Java SE 6 auf 1.6.0_31.

Schließen Sie vor der Installation dieses Updates alle Webbrowser und Java-Programme.

- Weitere Informationen zum Sicherheitsinhalt dieses Updates erhalten Sie [unter](http://support.apple.com/kb/HT5055?viewlocale=de_DE.)
- Weitere Informationen zum Sicherheitsinhalt dieses Updates erhalten Sie [unter](http://support.apple.com/kb/HT1222?viewlocale=de_DE)

---

* **NACHTRAG** *

---

F-Secure nennt in seinem Advisory Schritte, mit denen sich eine potenzielle Infektion im Mac-OSX-Terminal feststellen lässt. Wenn die Befehle

    defaults read /Applications/Safari.app/Contents/Info LSEnvironment

und

    defaults read ~/.MacOSX/environment DYLD_INSERT_LIBRARIES

jeweils die Fehlermeldung "The domain/default pair of (...) does not exist" ausgeben, soll man sich die Malware nicht eingefangen haben.

Meine Ausgabe sieht folgendermaßen aus:
`Last login: Thu Apr  5 14:06:26 on ttys001

jans-imac:~ jan$ defaults read /Applications/Safari.app/Contents/Info LSEnvironment

2012-04-05 15:36:46.776 defaults[586:707]

The domain/default pair of (/Applications/Safari.app/Contents/Info, LSEnvironment) does not exist`

([via](http://www.heise.de/mac-and-i/meldung/Apple-aktualisiert-Java-Unterstuetzung-fuer-Mac-OS-X-1500692.html))
