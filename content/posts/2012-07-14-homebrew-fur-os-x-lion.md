---
title: Homebrew für OS X Lion
slug: homebrew-fur-os-x-lion
date_published: 2012-07-14T21:24:26.000Z
date_updated: 2018-08-22T09:37:36.000Z
---

Ich habe ja vor langer Zeit schon mal [Rudix](__GHOST_URL__/unixlinux-tools-und-helferlein-unter-os-x/) empfohlen, wenn es darum geht, Unix-Software auf OS X laufen zu lassen. Rudix ist absolut simpel und einfach zu benutzen, ein Befehl lädt herunter und installiert fertige Packages. Allerdings stößt Rudix genau an der Stelle auch an seine Grenzen, nämlich da, wo Pakete nicht im Repository sind, da kann Rudix auch nix installieren

**Vorgehensweise**:

- [Command Line Tools für Xcode](https://developer.apple.com/downloads/index.action) downloaded (oder xCode komplett)
- Homebrew installieren

Nach dem Download installiert ihr die Xcode Command Line Tools und dann gebt ihr im Terminal folgenden Befehl ein:

    /usr/bin/ruby -e "$(/usr/bin/curl -fsSL https://raw.github.com/mxcl/homebrew/master/Library/Contributions/install_homebrew.rb)"

Das wars, Homebrew lädt sich runter und installiert. Danach gebt ihr `brew doctor` ein, damit checkt Homebrew, ob noch was fehlt, bei mir war es zum Beispiel Github support und ein veraltetes XCode 4.3, was ich allerdings nicht verstehe, weil ich ja die Command Line Tools installiert hatte.

Danach kann man Homebrew im Terminal mit `brew install $Programm` benutzen, also zum Beispiel `brew install wget`.

    [thafaker@iMac-SSD /Users/thafaker]$ brew install wget
    Warning: You have Xcode-4.3, which is outdated.
    Please install Xcode 4.3.3.
    ==> Downloading http://ftpmirror.gnu.org/wget/wget-1.13.4.tar.bz2
    ######################################################################## 100,0%
    ==> ./configure --disable-debug --prefix=/usr/local/Cellar/wget/1.13.4 --sysconfdir=/usr/local/etc --with-ssl=openssl --disab
    ==> make install
    /usr/local/Cellar/wget/1.13.4: 7 files, 576K, built in 31 seconds
    [thafaker@iMac-SSD /Users/thafaker]$ wget
    wget: missing URL
    Usage: wget [OPTION]... [URL]...
    
    Try `wget --help' for more options.
    [thafaker@iMac-SSD /Users/thafaker]$

### Uninstall Brew How To

Manchmal möchte man Brew vielleicht aber auch einfach wieder deinstallieren? Dann geht es so: jede Zeile einzeln im Terminal eingeben und Enter drücken.

    cd `brew --prefix`
    rm -rf Cellar
    brew prune
    rm `git ls-files`
    rm -r Library/Homebrew Library/Aliases Library/Formula Library/Contributions
    rm -rf .git
    rm -rf ~/Library/Caches/Homebrew
