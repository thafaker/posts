---
title: [iOS] Downgrade auf 9.2.1 nicht länger möglich
slug: ios-downgrade-nicht-langer-moglich
date_published: 2016-04-07T07:20:04.000Z
date_updated: 2018-08-22T09:39:28.000Z
tags: ios, jailbreak, downgrade, tinyumbrella, shsh blobs
---

Apple signiert die vorausgehende Version des Betriebssystem nicht länger, der Weg zurück von iOS 9.3 wird damit versperrt. Dies gilt auch für tvOS. 

Ein Downgrade von iOS 9.3 zurück auf iOS 9.2.1 lässt sich nun nicht mehr durchführen: Apple hat das Signieren der älteren iOS-Version in der Nacht auf Mittwoch eingestellt – gut zwei Wochen nach der Veröffentlichung von iOS 9.3. Die Freigabe von iOS 9.3.1 liegt eine knappe Woche zurück.

Dies ist vor allem für **Jailbreaker** immer eine *wichtige* Information, denn meist kann eine ältere Version von iOS noch gejailbreakt werden (hier allerdings auch nicht, der letzte [Jailbreak funktionierte unter iOS 9.1](__GHOST_URL__/jailbreak-breaking-ios-9-1-jailbreak-ist-da/)), eine neue allerdings nicht. Deshalb versuchen viele, nach kurzer Zeit wieder zurück zu kehren - was nun eben nicht mehr möglich ist.

Sobald man eine Firmware aufspielen möchte, fragt iTunes den Apple-Server, ob das okay ist und erhält eine Bestätigung, Signierung. Diese Bestätigung startet dann die Möglichkeit, die Firmware (also iOS) aufzuspielen. Wird dies vom Apple-Server abgelehnt, schlägt das fehl. Auch wenn man keine Verbindung ins Internet zulässt, funktioniert das Aufspielen einer anderen iOS-Version nicht, man kann diese Sperre also nicht umgehen.

Früher gab es eine Software Namens **TinyUmbrella**, mit der man diese Signierung vorgaukeln konnte. Die kleine Software holte sich vorher vom eigenen iPhone die Signatur, lies einene eigenen Server im Hintergrund laufen und wenn man nun downgraden wollte, kommunizierte iTunes mit dem kleinen Server auf dem eigenen Rechner und wurde verarscht - das Downgrade auf JEDE BELIEBIGE IOS VERSION war dadurch möglich - wenn man vorher seine SHSH Blobs gesichert hatte.

![](http://picdump.thafaker.de/2012/10/wiederherstellung_ios6-580x266.png)

Das Signieren älterer Versionen stellt Apple gewöhnlich innerhalb weniger Wochen nach der Veröffentlichung einer neuen iOS-Version ein. Den Rückschritt auf die ältere Version versperrt der Konzern auch aus Sicherheitsgründen: Im Rahmen des Updates werden oft zusätzliche Details zu den damit beseitigten Schwachstellen bekannt, die sich zum Angriff auf nicht aktualisierte Modelle nutzen lassen.

([via](http://www.heise.de/mac-and-i/meldung/Downgrade-auf-iOS-9-2-1-nicht-laenger-moeglich-3163785.html))
