---
title: [SECURITY] Aktuelle iOS-Version anfällig für PIN-Code-Knacker
slug: security-aktuelle-ios-version-anfallig-fur-pin-code-knacker
date_published: 2017-08-21T14:31:28.000Z
date_updated: 2018-08-22T09:37:42.000Z
tags: ios, apple, security, sicherheit, iphone, 10.3.3
---

In China essen Sie Hunde! Spaß beiseite. Aber in China kann ein Gerät erworben werden, mit dem sich der PIN-Code von bestimmten iOS-Geräten mit aktueller Software ermitteln lässt. Die Hardware, die laut Angaben des YouTubers EverythingApplePro derzeit 500 US-Dollar kostet und auch nach Amerika verschickt wird, kommt mit iPhone 7 und 7 Plus sowie der jüngsten iOS-Version 10.3.3 zurecht. Zudem sollen iOS-11-Beta-Versionen bis iOS 11 Beta 3 betroffen sein.

![](https://images.unsplash.com/photo-1501144922461-cf33b67e3457?ixlib=rb-0.3.5&amp;q=80&amp;fm=jpg&amp;crop=entropy&amp;cs=tinysrgb&amp;w=1080&amp;fit=max&amp;s=f3a05957ddb3083fa178955021b5c993)
Photo by [+Simple](https://unsplash.com/@andsimpleco?utm_source=ghost&amp;utm_medium=referral&amp;utm_campaign=api-credit) / [Unsplash](https://unsplash.com/?utm_source=ghost&amp;utm_medium=referral&amp;utm_campaign=api-credit)

Als Geschäftsfeld haben die Entwickler der Hardware wohl *Ermittlungsbehörden* oder andere staatlichen Stellen ins Auge gefasst, denn je nach Länge des Codes kann das Knacken des Passworts nämlich mehrere Tage bis Wochen dauern[[1]](#fn1). Es ist klassisches *Bruteforcing*, es wird also jede mögliche Kombination getestet.

Dabei wird die ausgenutzt, dass iOS in der aktuellen Version im Rahmen der Gerätewiederherstellung einen PIN-Code-Dialog enthält, der über keine Begrenzung der Anzahl der Eingaben verfügt – in allen anderen Codesperre-Dialogen existiert dieser, was ein Brute-Forcing unmöglich macht. Um diesen Modus zu erreichen, muss eine Windows-Software verwendet werden, die ein Starten des Wiederherstellungszustandes ohne PIN-Code-Eingabe erlaubt.

([via](https://www.heise.de/mac-and-i/meldung/Aktuelle-iOS-Version-anfaellig-fuer-PIN-Code-Knacker-3808240.html))

---

1. 
Jedoch haben Behörden bekanntlich viel Zeit, sodass dies kein Problem darstellen sollte. *scnr*[↩︎](#fnref1)
