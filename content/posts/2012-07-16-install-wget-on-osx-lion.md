---
title: How to Install wget on OSX Lion
slug: install-wget-on-osx-lion
date_published: 2012-07-16T19:02:32.000Z
date_updated: 2018-08-22T09:37:36.000Z
---

Da ich ja nun schon sehr häufig gemeckert habe, dass mir wget als nützliches Tool zum Download unter OS X fehlt, habe ich auch gleich verschiedenen Lösungsmöglichkeiten vorgeschlagen, wie man generell Unix/Linux-Tools unter OS X zum Laufen und nachinstallieren kann, namentlich [Homebrew](__GHOST_URL__/homebrew-fur-os-x-lion/) oder [Rudix](__GHOST_URL__/unixlinux-tools-und-helferlein-unter-os-x/). 

Allerdings ist jetzt die Zeit reif, endlich mal zu beschreiben, wie man wget direkt und nativ unter Lion ohne weiteres Brimborium nachinstalliert, sodass es im Terminal zur Verfügung steht. Leider braucht man allerdings noch immer XCode, welches es kostenlos [hier zum Download](https://developer.apple.com/downloads/index.action) gibt.

Jede Zeile einzeln im Terminal eingeben und Enter drücken. Die erste lädt herunter, die zweite entpackt, die dritte geht ins neue Verzeichnis, die vierte konfiguriert das Makescript, die fünfte lässt make laufen und kompiliert das Programm und die sechste, dazu braucht sie auch das Root-Passwort, installiert schließlich wget. Die siebste Zeile prüft, ob und wo wget nun auf dem Mac ist. Viel Spaß.

    curl -O http://ftp.gnu.org/gnu/wget/wget-1.13.4.tar.gz
    tar -xzvf wget-1.13.4.tar.gz
    cd wget-1.13.4
    ./configure --with-ssl=openssl
    make
    sudo make install
    which wget ((Should output: /usr/local/bin/wget))

[Hier auf thahipsters Octopress](__GHOST_URL__/octopress/blog/2012/11/17/wget-unter-os-x/) gefunden.
