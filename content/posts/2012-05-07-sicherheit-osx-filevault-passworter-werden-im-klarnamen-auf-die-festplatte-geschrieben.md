---
title: [SICHERHEIT] OSX Filevault Passwörter werden im Klarnamen auf die Festplatte geschrieben
slug: sicherheit-osx-filevault-passworter-werden-im-klarnamen-auf-die-festplatte-geschrieben
date_published: 2012-05-07T13:34:21.000Z
date_updated: 2018-08-22T09:38:10.000Z
---

Filevault, die Festplattenverschlüsselung von Mac OSX, ist eigentlich dazu gedacht, die Festplatte vor unbefugtem Zugriff zu schützen. Bei Version 1 von Filevault ist nun allerdings eine grobe [Sicherheitslücke](http://www.zdnet.com/blog/security/apple-security-blunder-exposes-lion-login-passwords-in-clear-text/11963?tag=mncol;txt) bekannt geworden. Die Passwörter für die Verschlüsselung werden im Klartext auf einem nicht verschlüsselten Teil der Festplatte abgelegt, wie der Sicherheitsforscher David Emery berichtet. In der aktuellen Version Mac OS X 10.7.3, welche am 1. Februar 2012 veröffentlicht wurde, hat man einen Debug-Schalter (DEBUGLOG) aktiviert gelassen, was dazu führt, dass ein systemweites Logfile im Klartext geschrieben wird, das für jeden Nutzer mit Root- oder Adminzugriff lesbar ist. Es enthält auch das Login-Passwort eines Nutzers eines verschlüsselten Verzeichnisbaums, wie ihn das alte Filevault nutzt. Dieses Logfile bleibt standardmässig mehrere Wochen erhalten. Man kann es ebenfalls auslesen, wenn der Mac über eine externe Firefire Festplatte gebootet wird, ein Passwort wird nicht abgefragt.

Seit Mac OSX 10.7 ist Filevault in der Version 2 mit an Bord. Dieses verschlüsselt die komplette Festplatte und nicht, wie in der Vorversion,  nur Teile davon. Die alte Filevault Variante wird jedoch weiterhin mitgeliefert. Sollte man diese bereits einsetzen wechselt diese nicht automatisch auf die Version 2.

Die einzige sichere Abhilfe derzeit ist, Filevault 2 zu nutzen und damit die komplette Festplatte zu verschlüsseln. Die zweite Möglichkeit wäre, ein Firmwarepasswort zu setzen, um zu verhindern, das der Mac von einer externen Festplatte gebootet werden kann. Jedoch gibt es auch hier leider eine Umgehungsmethode, welche von Apple Supportmitarbeitern genutzt wird.

Ein weiterer dramatischer Fakt ist, das [ein User in Apples Supportforen](https://discussions.apple.com/thread/3715366) bereits am 6. Februar diesen Jahres auf die Lücke aufmerksam machte. Hier muss Apple zukünftig wesentlich schneller reagieren, um das Vertrauen in die Sicherheit von Mac OSX nicht weiter zu gefährden.

Bild Logo (c) Apple
