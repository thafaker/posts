---
title: Windows Pagefile auf andere Festplatte auslagern
slug: windows-pagefile-auf-andere-festplatte-auslagern
date_published: 2019-03-27T20:53:00.000Z
date_updated: 2019-04-06T19:56:55.000Z
tags: windows 10, bigmac, anleitung, how to, howto
---

**Ich** weiß, dies hier ist ein Apple-Affines Weblog und ich berichte liebend gern nur über iMac respektive MacPro betreffende Themen. Aber da auf meinem [BigMac](__GHOST_URL__/tag/bigmac/) auch ein Windows 10 läuft, ist Windows 10 in diesem Zusammenhang sozusagen auch ein Apple Thema. Klingt schizophren, macht aber Sinn :-) 

Auf jeden Fall hatte ich das Phänomen, dass mein Windows 10 nach dem Start, quasi ab dem Login-Fenster, unwahrscheinlich träge war und sich kaum bedienen ließ. Das dauerte eine ganze Zeit und irgendwann war das urplötzlich verschwunden. Ich bin dieser Sache dann mit dem Task-Manager und dem **Ressourcenmonitor** nachgegangen und der Sache alsbald auf die Schlichte gekommen. Ich betreibe Windows 10 auf einer SSD, sodass es fein schnell ist. Weiterhin betreibe ich eine drehende 640 GB HDD in diesem MacPro, einzig und allein für Spiele die ich unter Windows 10 spielen möchte. Wofür sonst sollte ich Windows auch sonst nutzen? [[1]](#fn1)

Es ist die Auslagerungsdatei **Pagefile.sys**, welche meine HDD zu 100% auslastete, indem sie geschrieben oder gelesen wurde - und dieses Verhalten natürlich mein restliches System in Bedrängnis brachte. Ich betreibe meinen BigMac mit 32 GB Ram, wenn Windows also eine Auslagerungsdatei dieser Größe jedes mal beim Start auf meine sehr langsame HDD schreibt, dann habe ich ein Problem.

Da ich aber doch eine pfeilschnelle SSD betreibe, wollte ich nun gern, dass Windows nicht auf meine HDD sondern auf meine SSD cached, wie das jedes normale Betriebssystem eben so macht. Nur muss ich ihm das händisch beibringen. Aber genug der vielen Worte, lassen wir Taten folgen.

### Anleitung Windows Pagefile auf andere Festplatte auslagern

1. Rechtsklick auf "Dieser PC" auf dem Desktop und "Eigenschaften" auswählen.

![worscht0](__GHOST_URL__/content/images/2019/04/worscht0.jpg)

1. Unter System klickt ihr links auf "Erweiterte Systemeinstellungen"

![worscht](__GHOST_URL__/content/images/2019/04/worscht.PNG)

1. Klickt auf den Reiter "Erweitert" und klickt dann bei Leistung auf "Einstellung"

![worscht2](__GHOST_URL__/content/images/2019/04/worscht2.PNG)

1. Klickt abermals auf "Erweitert" und dann auf "Ändern".

![worscht3](__GHOST_URL__/content/images/2019/04/worscht3.PNG)

1. Nehmt oben das Häkchen bei "Auslagerungsdateigröße für alle Laufwerke automatisch verwalten" raus. Nun könnt ihr für jedes Laufwerk bestimmen a) ob es eine Auslagerungsdatei geben soll und wie groß diese sein sollte.

![worscht4](__GHOST_URL__/content/images/2019/04/worscht4.PNG)

1. Ich habe hier zum Beispiel bei Laufwerk D: und G: (meine langsamen HDDs) "keine Auslagerungsdatei" angeklickt und danach auf "Festlegen". Bei C: möchte ich eine Auslagerungsdatei haben [[2]](#fn2), denn das ist meine SSD. Nach einem Klick auf OK startet das System neu.
2. Der Geschwindigkeitsgewinn war enorm, ich bin sehr zufrieden.

*Das wars auch schon wieder, bis bald*.

---

1. 
Kleiner Scherz, Windows 10 ist wieder super, wie mein Windows 2000 damals, mit dem habe ich aber aufgehört Windows zu nutzen und stieg auf PowerPC und OS X um. [↩︎](#fnref1)

2. 
Ich bin mir nicht sicher ob es auch ohne geht, heuzutage. Ich weiß nicht wie viel Windows 10 so swappt? [↩︎](#fnref2)
