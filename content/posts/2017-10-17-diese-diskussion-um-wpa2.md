---
title: Diese Diskussion um WPA2…
slug: diese-diskussion-um-wpa2
date_published: 2017-10-17T17:15:47.000Z
date_updated: 2018-08-22T09:37:42.000Z
tags: sicherheit, wpasupplicant, wpa2, lücke, 4-Wege-Handshake
---

Nun, selbst im Radio von MDR Aktuell, sogar auf einschlägigen Tratschseiten im Netz, überall wird mit dem angeblichen Hack von WPA2 der Untergang der aktuellen kabellosen Netzwerkkommunikation und damit der normalen Benutzung des Mobilfunkgerätes besungen. 

Aber das ist nicht richtig. Überhaupt gar nicht WPA2 ist nicht gebrochen. Keiner kann das Kennwort erraten. Niemand. Es ist ein ganz anderes Problem was sich hier stellt: nämlich die schlunzenhafte Implementierung der Standards von WPA2. Diese führe dazu, dass es unsicher wird. Das stimmt. Jedoch ist dies mit einem Patch behoben. Ein kurzes Softwareupdate genügt und die Schwachstelle ist verschwunden.

Linux, OpenBSD, NetBSD sowie FreeBSD haben das bereits vorgemacht und die Lücke schon wieder geschlossen. Windows und macOS werden bald nachziehen, iOS Geräte ebenfalls. [[1]](#fn1)

Anders sieht die Situation jedoch bei Android aus. Da *wpasupplicant*, so heißt die Software für WPA2 Wlan unter Linux, tief im System steckt, ist die Sache nur durch ein ordentliches Update zu beheben. Leider zeigt die Realität, dass viele günstigere Android-Telefone keine Updates mehr erfahren und meist mit einer alten Version von Android unterwegs sind. Das ist meist auch nicht schlimm, aber jetzt, im Zuge dieser Update-Notwendigkeit, da ist es ein Problem.

[...] Der Sicherheitsforscher Mathy Vanhoef hat unter dem Namen Krack (Key Re-Use Attack) eine Reihe von Angriffen auf mit WPA2 verschlüsselte WLAN-Netzwerke demonstriert. Dabei hat er nicht die Grundlagen des Protokolls gebrochen, die zentralen Sicherheitsbeweise gelten nach wie vor. **Auch wenn praktische Angriffe möglich sind, warnt der Autor selbst vor Panik**. Kein Nutzer sollte aufhören WPA2 zu nutzen, auch wenn das Gerät noch nicht gepatcht ist. [...]

Die Angriffe zeigen, dass WPA2 beschädigt ist, aber nicht grundlegend gebrochen. Eine sichere Implementierung des derzeitigen Standards ist also möglich. Auch können gegen die Sicherheitslücke gepatchte Geräte weiterhin mit ungepatchten Geräten kommunizieren. WPA3, so Vanhoef, brauche es also derzeit nicht.

*Beruhigt euch wieder.*

- [Download Paper (PDF)](https://papers.mathyvanhoef.com/ccs2017.pdf)

---

1. 
Neben Wlan-Geräten sind auch Access-Points betroffen. Fritz z.B. hat bereits ein Statement zur Problematik veröffentlicht und wird patchen. [↩︎](#fnref1)
