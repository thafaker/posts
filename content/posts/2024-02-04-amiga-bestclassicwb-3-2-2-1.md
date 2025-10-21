---
title: Amiga BestClassicWB 3.2.2.1
slug: amiga-bestclassicwb-3-2-2-1
date_published: 2024-02-04T13:04:37.000Z
date_updated: 2024-05-10T17:05:09.000Z
tags: bestclassicWB, amiga os 3.2, vintage computing, whdload, update
---

Wir haben ja [neulich erst darüber berichtet](__GHOST_URL__/installiere-whdload-unter-amiga-os-3-1-4-fur-amiga-1200/), wie man sich automatisiert mit der HSTWB ein CF-Image mit vollem Amiga OS bauen kann, dann will ich in diesem kurzen Artikel darauf eingehen, dass es eine Alternative gibt. Die sogenannte **BestClassicWB** ist eine Neukreation eines Enthusiasten (User samplist im [[Abime](https://eab.abime.net/showthread.php?t=107410)](https://eab.abime.net/showthread.php?t=107410&amp;page=9) Forum), welche konkret für ein frisch installiertes Amiga OS 3.2.2 gedacht ist. 
![Update Amiga OS 3.2.1 auf 3.2.2.1](__GHOST_URL__/content/images/2024/02/Bildschirmfoto-2024-02-04-um-13.36.51.png)Update Amiga OS 3.2.1 auf 3.2.2.1
Es gibt hier keine Einstellungsmöglichkeit oder ähnliches, deshalb bietet es sich auch tatsächlich nur für eine Neuinstallation an. Es werden neben schönen Icons und coolen Erweiterungen sehr viele Tools, von Packern bis WHDLoad automatisch installiert und in Funktion gebracht. 

Ich habe das soeben mal ausprobiert und was soll ich sagen, es funktioniert ziemlich gut Out-Of-The-Box. So sieht das Ergebnis auf meine Amiga 1200 aus:
![BestClassicWB nach der Installation auf Amiga 1200](__GHOST_URL__/content/images/2024/02/Bildschirmfoto-2024-02-04-um-13.56.10.png)BestClassicWB nach der Installation auf Amiga 1200
Zunächst als Release-Files *irgendwo* veröffentlicht, ist das Projekt nun auf [Github](https://github.com/kouts/best-classic-wb/releases) zu Hause und kann in der neuen Version, die explizit für Amiga OS 3.2.2.1 erstellt wurde, herunter geladen werden. Diese ZIP-Datei wird entpackt und der Installer gestartet. Dieser kopiert sämtliche Tools auf die Festplatte, benennt die Workbench HD in OS3.2 um und nach einem Neustart solltet ihr obiges Ergebnis sehen. Ich betreibe es auf einem echten Amiga 1200 mit ACA 1233N Turbokarte, aber es funktioniert natürlich auch in einem Emulator wie WinUAE.

[**UPDATE**] Mittlerweile ist Version 2.1.12 ([Download](https://github.com/kouts/best-classic-wb/releases/download/v2.1.12/BestClassicWB.zip)) erschienen, der Autor hat u.a. die CPU-Anzeige gegen eine weniger ressourcenintensive Variante ausgetauscht und viele andere Pakete aktualisiert.
![Amiga OS 3.2.2.1 mit BestClassicWB 2.1.8](__GHOST_URL__/content/images/2024/02/Bildschirmfoto-2024-02-07-um-09.26.14.png)Mein Amiga OS 3.2.2.1 mit BestClassicWB 2.1.8
## Features

- Based on the original ClassicWB distribution
- GlowIcons included in the original ClassicWB, plus DefIcons icons
- Extra datatypes
- Extra libraries including PeterK icon.library
- Additional commodities/utilities in WBStartup
- FBlit, FText
- MUI
- Miami
- Other useful programs such as DOpus, WHDLoad + iGame, Eagleplayer, Delitracker, PPaint, WBDock
- More...

## Voraussetzung

- AGA Amiga, also 1200 oder 4000
- Beschleunigerkarte mit extra-RAM

## Vorgehen 

1. Installiert ein neues Amiga OS 3.2 und installiert alle von [Hyperion zur Verfügung](https://www.hyperion-entertainment.com/index.php/downloads?view=download&amp;layout=form&amp;file=129) gestellten Updates, sodass ihr euer Amiga OS auf Version 3.2.2.1 bringt. (Aktueller Stand 02/2024)
2. Ladet euch die [BestClassicWB](https://github.com/kouts/best-classic-wb/releases/download/v2.1.7/BestClassicWB.zip) herunter (V.2.1.7)
3. entpackt die ZIP-Datei unter eurem Amiga
4. startet den Installer im entpackten Verzeichnis
5. Lasst den Installer durchlaufen
6. Es gibt eine Erfolgsmeldung
7. Startet den Amiga neu
8. *Das wars*

Es gibt keine Einstellungsmöglichkeiten im Installer, wenn ihr schon Sachen auf eurer Workbench habt, kann es gut passieren, dass er Dinge überschreibt und sie danach nicht mehr funktionieren. Also wirklich nur auf einem frischen Amiga OS ausprobieren.

### Ressources

-  Download 2.1.12: [https://github.com/kouts/best-classic-wb/releases/download/v2.1.12/BestClassicWB.zip](https://github.com/kouts/best-classic-wb/releases/download/v2.1.12/BestClassicWB.zip)

[

Releases · kouts/best-classic-wb

Contribute to kouts/best-classic-wb development by creating an account on GitHub.

![](https://github.githubassets.com/assets/pinned-octocat-093da3e6fa40.svg)GitHubkouts

![](https://opengraph.githubassets.com/b13575c618f699d35e2831bc8d23c731685eb867ac45bfc37d2b33c5249aab2c/kouts/best-classic-wb)
](https://github.com/kouts/best-classic-wb/releases)
