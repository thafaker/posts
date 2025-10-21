---
title: Zweite Passwortlücke in macOS
slug: zweite-passwortlucke-in-macos
date_published: 2018-01-11T09:30:00.000Z
date_updated: 2018-08-22T09:37:41.000Z
tags: security, macOS 10.13, sicherheitslücke, high sierra, mac app store
---

Tja, was sollen wir denn sagen? Nichts! Denn nur kurze Zeit nachdem eine [eklatante Sicherheitslücke](__GHOST_URL__/apple-bestatigt-alle-mac-und-ios-gerate-sind-von-meltdown-und-spectre-betroffen/) in macOS, welche vollen *root*-Zugriff erlaubte, sich umtrieb, steht nun erneut eine Passwortlücke auf der Agenda. 

Diesmal geht es jedoch nicht um Vollzugriff aufs System, sondern um Zugriff auf den Mac App Store. Die Einstellungen des Mac App Store lassen sich nämlich mit jeder beliebigen Zeichenkette öffnen.

![](https://images.unsplash.com/photo-1506729623306-b5a934d88b53?ixlib=rb-0.3.5&amp;q=80&amp;fm=jpg&amp;crop=entropy&amp;cs=tinysrgb&amp;w=1080&amp;fit=max&amp;s=2733f25b5892177c34a97dac46694bb4)
Photo by [Harpal Singh](https://unsplash.com/@aquatium?utm_source=ghost&amp;utm_medium=referral&amp;utm_campaign=api-credit) / [Unsplash](https://unsplash.com/?utm_source=ghost&amp;utm_medium=referral&amp;utm_campaign=api-credit)

Der Fehler betrifft die Anwendung Systemeinstellungen und dort den Karteireiter für den Mac App Store. Eigentlich sollte dieser nur gegen Eingabe eines Administratorpassworts für Veränderungen zugänglich sein. Es ist aber möglich, hier den Nutzernamen eines Administrators einzugeben und anschließend als Passwort jede beliebige Zeichenkette – das richtige muss es nicht sein. Nachvollziehbar scheint der Bug unter macOS 10.13, 10.13.1 sowie 10.13.2 zu sein.

Zur Ausnutzung des Bugs müssen einige Voraussetzungen erfüllt sein. So muss der eingeloggte Account, der die Sicherung umgeht, selbst ein Administrator sein, entsprechend muss der Angreifer auf den betreffenden Mac Zugriff haben und dieser wiederum offen sein, um die Systemeinstellungen aufzurufen.

Die ganze Geschichte gibt es bei [Mac&I](https://www.heise.de/mac-and-i/meldung/Zweite-Passwort-Luecke-in-macOS-High-Sierra-3938468.html).
