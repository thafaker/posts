---
title: T-Online und DNS Nameserveränderung? [Update]
slug: t-online-und-dns-nameserverefbfbdnderung-update
date_published: 2005-08-12T12:05:39.000Z
date_updated: 2019-05-11T14:14:22.000Z
tags: update, dns, t-online
---

Wahnsinn. Alles lief super. Bis ich wieder in mein Zimmer ging und das Internet tot war. Das ganze Internet? NEIN, nur das von meinem lokalen Rechner. Ich loggte mich sofort auf meinem kleinen Linux-Gateway ein, aber dort funktionierte alles gut.

Nach etlichen Versuchen mit Try&Error Charakter fand ich schließlich heraus, dass der alte DNS: 194.25.2.129 nicht mehr ging. Als ich nämlich in die Nameservereinstellungen sah stellte ich fest, dass diese wie von Zauberhand verändert worden sind. Die neuen DNS-Einträge lauten: 217.237.151.97

Nachdem ich nun die DNS-Einträge auf meiner eigenen Kiste aktualisiert hatte, ging auch wieder alles bestens. **grübel** Aktualisiert T-Offline einfach so die Nameserver und trägt das bei ihren Kunden ein?

Diese Vorstellung macht mir in der Tat angst! Aber vielleicht ist so was auch ganz normal und kommt so selten vor, als dass ich es noch nie erlebt habe, ich bin ja noch jung. **pffft**

[**Update**] Es ist normal dass sich die Router die DNS-Einträge ihres Router bei Verbindung holen, das ist so gewollt.

**[Nachtrag:]**
**DNS-Server**

# 1: 217.237.149.225

# 2: 217.237.151.97

Hier noch weitere die ich bei Recherchen im Netz fand:

194.25.0.69

194.25.0.70

194.25.0.61

194.25.0.62

194.25.0.53

194.25.0.54

217.237.151.225

217.237.149.161

217.237.150.225

217.237.150.97

217.237.149.225

217.237.151.97

217.237.151.161

217.237.150.141
