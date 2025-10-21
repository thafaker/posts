---
title: "Apple bestätigt: Alle Mac- und iOS-Geräte sind von Meltdown und Spectre betroffen"
slug: apple-bestatigt-alle-mac-und-ios-gerate-sind-von-meltdown-und-spectre-betroffen
date_published: 2018-01-05T12:59:18.000Z
date_updated: 2018-08-22T09:37:41.000Z
tags: security, arm, x86, intel, amd, sicherheitslücke, hardware, software
---

Apple hat am Donnerstag ein Support-Dokument mit Informationen zum Stand der Meltdown- und Spectre-Sicherheitslücken in iOS- und Mac-Geräten veröffentlicht. In diesem wird klargestellt, dass alle Produkte des Unternehmens beeinträchtigt seien. Es bestehe jedoch kein Grund zur Panik, da es zum einen keinen bekannten Exploit gebe. Zum anderen habe das Unternehmen mit iOS 11.2, macOS 10.13.2 und tvOS 11.2 Patches veröffentlicht, die die Anfälligkeit für Meltdown reduzieren sollen. Die Apple-Watch sei nicht von den Lücken betroffen. 

[**Hintergrund**] Die Sicherheitslücken **Meltdown** und **Spectre** ermöglichen es Angreifern, sensible Daten aus Speicherbereichen auszulesen. Die Sicherheitslücken wurde erst Anfang Januar 2018 öffentlich bekannt, die Firma Intel wurde nach derzeitigem Kenntnisstand bereits im Juni 2017 darüber informiert. Die Lücke lässt sich nur durch aufwändige Sicherheits-Patches in allen verfügbaren Betriebssystemen schließen. Betroffen sind Intel-Prozessoren sowie ARM. AMD-Prozessoren sind nicht im gleichen Umfang betroffen.

Für die Spectre-Lücke beabsichtige Apple in den nächsten Tagen ein Safari-Update zu veröffentlichen, mit dem die Anfälligkeit reduziert werden soll. In den kommenden Wochen und Monaten entwickle und teste Apple weitere Optimierungen der Software-Patches für alle eigenen Plattformen. Nutzer von älteren Mac-Versionen wie El Capitan und Sierra können sich auch ein wenig entspannen – auch die älteren Desktop-Betriebssysteme wurden mit entsprechenden Patches versehen.

#### Apple: Meltdown- und Spectre-Patches reduzieren Performance nicht

Entgegen erster Meldungen zur Reduzierung der Systemperformance durch das Einspielen der Patches seien Apple zufolge keine messbaren Einbußen festzustellen. Lediglich der Safari-Patch zur Reduzierung der Spectre-Lücke könnte die Browser-Performance um vernachlässigbare 2,5 Prozent verlangsamen. Neben Apple bestätigen auch Microsoft, Google und Amazon entsprechende Erkenntnisse.

Während Apple, Microsoft, Google und Amazon bereits erste Schritte zur Eindämmung der massiven Sicherheitslücken veröffentlicht haben, ist es an der Zeit, dass Hersteller von Android-Smartphones und -Tablets nachziehen. Denn lediglich Googles Nexus- und Pixel-Geräte haben bislang den relevanten Januar-Sicherheitspatch erhalten, mit dem die Bedrohung durch Datendiebstahl ausgeschlossen wird. Zwar sei es Google zufolge bei Android-Geräten kompliziert die Sicherheitslücke auszunutzen, dennoch sollten eventuelle Anfälligkeiten per Update ausgeräumt werden.

([via](https://www.msn.com/de-de/nachrichten/digital/apple-best%C3%A4tigt-alle-mac-und-ios-ger%C3%A4te-sind-von-meltdown-und-spectre-betroffen/))

#### [**UPDATE**]

Betroffen sind unter anderem sämtliche Intel-Core-Prozessoren bis zurück zum Jahr 2008 sowie eine Vielzahl von ARM-Cortex-CPUs. Nvidia glaubt, dass die CUDA-GPUs nicht anfällig sind und analysiert noch seine Tegra-Prozessoren.

Intel hat eine Liste der von den Sicherheitslücken Spectre und Meltdown betroffenen Prozessoren veröffentlicht. Die umfangreiche Aufstellung umfasst dabei sämtliche Prozessoren der Intel-Core-Generation (seit 2008), die Serien Intel Atom C, E, A, x3 und Z sowie die Celeron- und Pentium-Serien J und N.

Dazu kommen sämtlich Server-Prozessoren der Generationen Xeon 3400, 3600, 5500, 5600, 6500 und 7500 sowie die Xeon-Familien E3 (v1 bis v6), E5 (v1 bis v4), E7 (v1 bis v4). Ebenfalls anfällig für die Sicherheitslücken sind Prozessoren der Serie Xeon Scalable und die Rechenkarten Xeon Phi 3200, 5200 und 7200.

Nicht aufgeführt sind ältere Atom-Prozessoren der Generationen Bonnell und Saltwell aus den ersten Netbooks sowie die Itanium-Familie, die offenbar aufgrund ihrer In-order- statt Out-of-Order-Architektur nicht über die Lücken angreifbar sind. Damit ist beispielsweise der Netttop-Mini-PC Asus EeeBox B202 mit einem Atom N270 sicherer als ein aktueller Coffee-Lake-Komplettrechner.

([via](https://m.heise.de/newsticker/meldung/Prozessor-Luecken-Meltdown-und-Spectre-Intel-und-ARM-fuehren-betroffene-Prozessoren-auf-Nvidia-3934667.html))
