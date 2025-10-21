---
title: Ghost Backend lädt nicht
slug: ghost-backend-ladt-nicht
date_published: 2017-08-05T17:27:44.000Z
date_updated: 2018-08-22T09:37:42.000Z
tags: ghost, uberspace, fix.it, ghost1.x, ghost1.5, cloudflare, backend, rocketloader, anleitung, howto, how to
excerpt: Es ist unglaublich, wie lange mich diese Sache jetzt Zeit und Nerven gekostet hat. Doch endlich bin ich dahinter gekommen. Eigentlich, und dass laste ich mir schwer an, hätte ich es früher heraus finden können… aber wie das eben so ist.
---

Für die Lösung scrollen Sie bitte ganz nach unten

Es ist **unglaublich**, wie lange mich diese Sache jetzt Zeit und Nerven gekostet hat. Doch endlich bin ich dahinter gekommen. Eigentlich, und das laste ich *mir* schwer an, hätte ich es früher heraus finden können… aber wie das eben so ist. 

Ich habe mein Ghost-Weblog auf Version 1.0 aktualisiert, testweise. Das ging. Ich kehrte aber zur Sicherheit zu meiner alten Version 0.11.11 zurück. Als ich dann ganz in Ruhe migrieren wollte, das Update ist nämlich nicht so trivial wie bisher, gab es bereits Ghost Version 1.2 (aktuell ist bereits 1.5 veröffentlicht). Ich ging vor wie bisher, alles funktionierte, die Seite lud… doch es gab kein Backend. Ich konnte mich nicht mehr in mein Admin-Interface einloggen, weil es nicht erschien.

![Cloudflare](__GHOST_URL__/content/images/2017/08/Bildschirmfoto-2017-08-05-um-19.08.36.png)

Alles was ich sah war der Ladekreis bevor das Backend startet, also der Login ins Admin-Interface statt findet... doch nichts geschah. Ich konnte auch in sämtlichen Logfiles nicht finden, keine Fehlermeldungen.

Schnell wieder auf meine alte Version zurück gestellt - funktionierte alles.

- Version 1.5 installiert - Problem bestand
- Version 1.3 installiert - Problem bestand
- Version 1.0 installiert - Problem verschwunden, Backend funktioniert[[1]](#fn1)

Also dachte ich, es läge an meinem kaputtkonfigurierten Uberspace. Also mal auf Node 6 LTS[[2]](#fn2) umgestellt und wieder versucht:

- Version 1.5 installiert - Problem bestand
- Python gewechselt - Problem bestand
- Mir fiel an der Stelle nichts mehr ein

Also dachte ich, es könne nur noch an meinem Uberspace liegen (ich habe andere Domains auf anderen Uberspace-Servern wo die Umstellung auf 1.5 problemlos funktionierte…) und klickte mir testweise einen neuen Account, der erwatungsgemäß auf einem anderen Uberspace-Host lag.

### Ghost backend wont load - Cloudflare rocketloader

Auf dem neuen Uberspace funktionierte alles und ich konnte mich problemlos ins Backend einloggen. Super, Problem gefunden (dachte ich). Ich migrierte nun also sämtliche Daten der Website vom alten Account hin zum neuen wie die Datenbank, die Bilder etc. pp. und war letztlich bereit, die Domain umzuschalten. Gesagt - getan.

...

**UND DAS BACKEND LUD NICHT MEHR**

> Es lag nämlich an Cloudflare[[3]](#fn3)

Ich nutze **Cloudflare**[[4]](#fn4) für thafaker.de, um es zu beschleunigen. Scheinbar cached und minified Cloudflare aber so sehr, dass das Backend dadurch kaputt geht. Als ich dann endlich diesen Übeltäter in Verdacht hatte, konnte ich auch endlich nach etwas googlen - und siehe da, [jemand hatte bei Ghost 0.5 in Verbindung mit Cloudflare](https://github.com/TryGhost/Ghost/issues/3782) das gleiche Problem wie ich - das Backend lud nicht mehr.

#### Lösung

1. Cloudflare deaktivieren.
2. ODER
3. Eine Ausnahmeregel erstellen, die dafür Sorge trägt, dass Cloudflare für das Backend `/ghost` nicht mehr benutzt wird und man sich folglich wieder einloggen kann.
![Bildschirmfoto-2017-08-05-um-19.44.53](__GHOST_URL__/content/images/2017/08/Bildschirmfoto-2017-08-05-um-19.44.53.png)
4. Dann auf **Create Rule**
![Bildschirmfoto-2017-08-05-um-19.46.36](__GHOST_URL__/content/images/2017/08/Bildschirmfoto-2017-08-05-um-19.46.36.png)
5. Passt eure Domain an, klickt auf Save and Deploy
6. *Fertig*.
7. Dauert vielleicht etwas, bis die Regel bei euch greift, aber jetzt müsstet ihr euch wieder einloggen können.
8. Ich habe keine Ahnung, warum es mit Ghost 1.0 noch funktioniert, ab 1.2 jedoch nicht mehr.

---

1. 
Dies ist bis heute ungeklärt, ich habe keine Ahnung WARUM in Gottes Namen Version 1.0 funktioniert, ab da aber nicht mehr, ehrlich. [↩︎](#fnref1)

2. 
Wird in der Installationsanleitung von Uberspace jetzt ohnehin empfohlen, damals aber nich nicht [↩︎](#fnref2)

3. 
was anderes konnte es jetzt nicht mehr sein, da vor der Domainmigration auf den neuen Uberspace alles geklappt hat, mein alter Account also auch gar nicht kaputt war, es war immer nur Cloudflare. [↩︎](#fnref3)

4. 
Cloudflare ist ein dezentral aufgestelltes Content Delivery Network mit anhängigem DNS. Es werden Server in 102 Rechenzentren in mehr als 49 Ländern verteilt betrieben. [↩︎](#fnref4)
