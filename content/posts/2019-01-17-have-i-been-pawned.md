---
title: Have I been pawned?
slug: have-i-been-pawned
date_published: 2019-01-17T16:51:00.000Z
date_updated: 2019-04-06T15:52:21.000Z
tags: netzwelt, sicherheit, security, collection #1
---

**Neulich** erhielt ich eine Mail von meinem *Hoster*. Mein Email-Account musste gesperrt werden, weil sich Dritte Zugang verschafft haben. Aha. Shit! Und was macht man mit so einem Mailaccount? Genau, man versendet **Spam**. Klar, das gefiel meinem Hoster nicht. Also wurde kurzerhand gesperrt und ich als Besitzer informiert. Soweit so gut. Klar war mir nämlich nicht, wie das passieren konnte. Wie zur Hölle konnte jemand scheinbar mein Kennwort wissen? Das war gruselig. 

![Big Data](__GHOST_URL__/assets/2019/01/bigdata2.jpg)

Nachdem ich dieses dort benutzte Kennwort überall geändert hatte, überlegte ich, was ich jetzt noch tun könnte. Denn irgendwie wollte ich gern heraus finden, was da passiert war. Ich hatte noch nie einen *Trojaner*, über den ein Eindringling hätte mich ausspähen können. Dachte ich. Und war auch weiterhin in dem Glauben. Aber woher kam das dann? Woher wusste jemand, in diesem Fall ein Spammer, oder eine Spam-Machinery, wie sie meinen EMail-Account öffnen können?

Und dann fiel mir ein Projekt wieder ein: **Have i been pwned?**[[1]](#fn1) Dort kann man nämlich nachschauen, ob die eigene EMail-Adresse bereits schon mal in einem dieser großen Datenlecks, worüber ständig berichtet wird,

> Firma XYZ hat sich 3 Millionen Nutzerdaten samt Email und Kennwort stehlen lassen…

gesichtet (geleaked) worden ist. Und siehe da, genau das war geschehen. Scheinbar habe ich die Kombination aus Email und Kennwort die ich bei meinem EMail-Hoster genutzt habe, auch schon mal woanders benutzt. Und diesem anderen Dienst, dem wurden demnach die Daten geklaut. Oder er hat sie verkauft. Und nach ca. 4 Monaten hatten Sie erfolg. Denn meine Daten, das konnte ich auf der Website sehen, sind scheinbar irgendwann im Sommer öffentlich aufgetaucht.

Man kann die Website nicht nur zur Suche nach seiner Email-Adresse nutzen, man kann auch sein eigenes Kennwort eingeben und so prüfen, ob das im Datensatz auftaucht. Ich habe das alte, geleakte Passwort für einen Test eingetragen und siehe da, in zwei Datenhaufen tauchte es auf. Meine alte Email-Adresse ist sogar in 7 verschiedenen Datendiebstählen vorhanden. Erstaunlich…

### Collection #1

Aber warum ich nun gerade heute darüber schreibe? *Well…***über eine Milliarde** unterschiedliche Zugangsdaten aus verschiedenen Quellen enthält die Passwortsammlung "Collection #1". Insgesamt umfasst sie über **87 GByte**[[2]](#fn2). Der australische Sicherheitsforscher *Troy Hunt* hat die Sammlung auf seinem Blog analysiert und in den von mir soeben beschriebenen Dienst *Have I been pwned* (HIBP) integriert. Damit auch in diesem Fall die Nutzer überprüfen können, ob ihre E-Mail-Adresse oder ihr Passwort von dem Datenleck betroffen war. [[3]](#fn3)[[4]](#fn4)

Das ist die größte Sammlung dieser Art. Und es ist gruselig.

**Wenn ihr das lest, ändert bitte euer Standardpasswort. Nutzt nicht für jede Anmeldung das gleiche Kennwort. Nutzt unterschiedliche. Und macht es nicht zu einfach.**

Das Datenleck stammt von unendlich vielen von Websites, auch deutsche Domains sind dabei. Ob das jedoch stimmt, kann nicht genau gesagt werden. [Hier (archiviert)](http://web.archive.org/web/20190117213244/https://pastebin.com/UsxU4gXA) gibt es eine Liste.

*Es bleibt spannend…*

---

**Artikelbild**: Photo by [imgix](https://unsplash.com/photos/klWUhr-wPJ8?utm_source=unsplash&amp;utm_medium=referral&amp;utm_content=creditCopyText) on [Unsplash](https://unsplash.com/search/photos/music?utm_source=unsplash&amp;utm_medium=referral&amp;utm_content=creditCopyText).

**Artikelbild 2**: Photo by [Markus Spiske](https://unsplash.com/photos/Skf7HxARcoc?utm_source=unsplash&amp;utm_medium=referral&amp;utm_content=creditCopyText) on [Unsplash](https://unsplash.com/search/photos/music?utm_source=unsplash&amp;utm_medium=referral&amp;utm_content=creditCopyText).

---

1. 
Wurden meine Daten verkauft? [↩︎](#fnref1)

2. 
87 GB reiner Text. Unglaublich. Das ist unglaublich. [↩︎](#fnref2)

3. 
Golem.de [berichtet](https://www.golem.de/news/datenlecks-ueber-eine-milliarde-zugangsdaten-im-internet-1901-138796.html)[↩︎](#fnref3)

4. 
Heise.de [berichtet](https://www.heise.de/security/meldung/Passwort-Sammlung-mit-773-Millionen-Online-Konten-im-Netz-aufgetaucht-4279375.html) nun ebenfalls. [↩︎](#fnref4)
