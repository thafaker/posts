---
title: Ghost Blog Unplash Integration
slug: unplash-integration
date_published: 2017-08-20T08:30:59.000Z
date_updated: 2018-08-22T09:37:42.000Z
tags: ghost, how to, howto, anleitung, app, unplash integration, ghost blog, application
excerpt: Ghost bietet seit Version 1.6 ein neues Plugin, bei Ghost *App* genannt, welches sich der Integration von *Unplash* widmet. Unsplash ist eine der größten Communities für kostenlose Stock-Fotografien weltweit.
---

Ghost bietet seit Version 1.6 ein neues Plugin, bei Ghost *App* genannt, welches sich der Integration von *Unplash* widmet. Unsplash ist eine der größten Communities für kostenlose Stock-Fotografien weltweit. Mit der Integration in Ghost hat man somit Zugriff auf diese Fotos und embedded die Bilder auch gleich korrekt mit den richtigen Credits. 

![](https://images.unsplash.com/photo-1503088414719-16a89b27b122?ixlib=rb-0.3.5&amp;q=80&amp;fm=jpg&amp;crop=entropy&amp;cs=tinysrgb&amp;w=1080&amp;fit=max&amp;s=57bf59b1b8760c57b7ea7c5af4ed86d8)
Photo by [Conner Murphy](https://unsplash.com/@conner3400?utm_source=ghost&amp;utm_medium=referral&amp;utm_campaign=api-credit) / [Unsplash](https://unsplash.com/?utm_source=ghost&amp;utm_medium=referral&amp;utm_campaign=api-credit)

### Setting up

1. Geht auf die Website [Unplash.com](https://unsplash.com) und registriert euch dort. Dies könnt ihr via Facebook oder normal per Mail etc. tun.
2. Nach erfolgreicher Registrierung als Benutzer müsst ihr euch als *Developer* registrieren. Dazu nutzt ihr bitte [folgenden Link](https://unsplash.com/developers) und klickt auf "Register as a developer".
![Unplash Register Developer Ghost Blog](__GHOST_URL__/content/images/2017/08/Bildschirmfoto-2017-08-20-um-10.17.00.png)
3. Nach diesem Schritt legt ihr eine neue *Application* an, mit der kommuniziert werden soll. In diesem Fall ist das euer Ghost-Blog. Das geht über [folgenden Link](https://unsplash.com/oauth/applications). Füllt die benötigten Felder aus.
![Unplash register application ghost weblog](__GHOST_URL__/content/images/2017/08/Bildschirmfoto-2017-08-20-um-10.23.44.png)
4. Das Feld *redirect uri* lasst ihr frei, die Permissions lasst ihr auf *Public Access*.
5. Im nächsten Schritt nach *Save* erhaltet ihr die Application ID. Diese kopiert ihr und loggt euch in euer Ghost-Backend ein. Dort klickt ihr auf *Apps*, und dort auf *Unplash*.
![Unplash in Ghost aktivieren](__GHOST_URL__/content/images/2017/08/Bildschirmfoto-2017-08-20-um-10.14.10.png)
6. Jetzt fügt ihr die kopierte ID ein.
7. Testet die Verbindung. Setzt einen Haken bei *Enable Unplash* und speichert.
8. **Thats all**. Fortan findet ihr in eurem Editor und auch in den Settings eines Artikels die Möglichkeit, Unplash Bilder zu integrieren.
![Bildschirmfoto-2017-08-20-um-10.29.11](__GHOST_URL__/content/images/2017/08/Bildschirmfoto-2017-08-20-um-10.29.11.png)
