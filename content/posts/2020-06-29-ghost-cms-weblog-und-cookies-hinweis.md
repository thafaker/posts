---
title: Ghost Weblog CMS und Cookies
slug: ghost-cms-weblog-und-cookies-hinweis
date_published: 2020-06-29T03:00:00.000Z
date_updated: 2020-06-30T01:57:26.000Z
tags: anleitung, ghost, cookies, DSGVO, howto
excerpt: Eine Kurzanleitung, wie ihr in euer Ghost CMS einen Hinweisbanner auf Cookies einfügen könnt. DSGVO lässt grüßen.
---

Neuerdings ist es ja *en vogue* auf die Cookies auf seiner Website hinzuweisen und den Besucher darüber zu informieren, dass es sie gibt. Hierbei gibt es verschiedene Möglichkeiten, manche setzen einen Hinweis, andere wiederum lassen eine persönliche Auswahl des Users zu, welche Cookies denn nun konkret aktiviert werden etc. pp., kurzum - ist das wichtig? 

Hier scheiden sich wie immer die Geister, eine kurze Recherche im Netz gibt jedoch folgende Auskunft:

> Das deutsche Recht kennt aktuell trotz der EU Cookie Richtline (sic!) also keine direkte Pflicht, die Nutzer in die Verwendung von Cookies einwilligen zu lassen.

Eine Auskunft **sollte aber** stattfinden, jedoch muss nicht explizit zugestimmt werden. Der Benutzer aber eben unterrichtet. Vollständig Nachzulesen unter folgendem [Link](https://www.e-recht24.de/artikel/datenschutz/8451-hinweispflicht-fuer-cookies.html#:~:text=Das%20deutsche%20Recht%20kennt%20aktuell,von%20Cookies%20einwilligen%20zu%20lassen.&amp;text=Es%20bleibt%20also%20ein%20gewisses,Hinweis%20auf%20Ihrer%20Webseite%20anbieten.). 
Da wir bereits sehr schlechte Erfahrungen im Internet und vor allem mit Anwälten gemacht haben, werden wir also einen entsprechenden Hinweis auf Cookies in unsere Website einbauen, ohne jedoch rechtlich zu wissen, ob das ausreichend ist. Benutzung auf eigene Gefahr. 

### Cookie Hinweis mit Ghost CMS

Für einen Standard-Hinweis als Banner, den der Besucher mit einem "Got It" bestätigen kann, reicht folgender Code-Schnipsel, der in die Ghost-Codeinjection eingefügt werden muss:

    <link rel="stylesheet" type="text/css" href="//cdnjs.cloudflare.com/ajax/libs/cookieconsent2/3.0.3/cookieconsent.min.css" />
    <script src="//cdnjs.cloudflare.com/ajax/libs/cookieconsent2/3.0.3/cookieconsent.min.js"></script>
    <script>
    window.addEventListener("load", function(){
    window.cookieconsent.initialise({
      "palette": {
        "popup": {
          "background": "#000"
        },
        "button": {
          "background": "#f1d600"
        }
      }
    })});
    </script>
    

Kopiert diesen Code, wechselt im Ghost-Backend auf "Code injection" und fügt den Code im Bereich `Site Header` ein. Speichert ab. 
![Ghost CMS Code injection](__GHOST_URL__/content/images/2020/06/Bildschirmfoto-2020-06-29-um-14.26.03.png)Ghost CMS Code injection
Wenn ihr nun eure Startseite neu ladet, müsste am unteren Seitenrand ein Banner mit dem Hinweis auf Cookies erscheinen. Nicht schön, aber schnell.
![Cooke Banner thahipster.de Google Chrome macOS](__GHOST_URL__/content/images/2020/06/Bildschirmfoto-2020-06-29-um-19.55.33.png)Cooke Banner thahipster.de Google Chrome macOS![Cookie Hinweis in der mobilen Ansicht der Website thahipster.de](__GHOST_URL__/content/images/2020/06/cookie_thahipster.de.PNG)Cookie Hinweis in der mobilen Ansicht der Website thahipster.de
Das wars auch schon wieder. Bis bald.
