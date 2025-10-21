---
title: Xcode 5.0.2 Homebrew Compiler Error Mavericks 10.9 OSX
slug: xcode-5-0-2-homebrew-compiler-error
date_published: 2013-11-23T12:28:47.000Z
date_updated: 2018-08-22T09:38:43.000Z
---

Mit dem neuerlichen **XCode**-Update auf Version **5.0.2** geht [Homebrew (archiviert)](http://web.archive.org/web/20130411055521/http://brew.sh:80/index_de.html), allen bekannt als das Tool der Wahl wenn es um Terminal und dessen Apps und allem geht, was Apple nicht (mehr) mitliefert, nicht mehr. Homebrew braucht ein ordentliches XCode um korrekt arbeiten zu können, dies liegt am benötigten Compiler und so. Bisher ging das bei mir problemlos. Jetzt kam eben jenes XCode Update rein und schwupps - Homebrew Error. Dieser Fehler tritt nicht nur bei mir auf. 

Die Fehlermeldung sieht wie folgt aus:

    
    thafakers Uber-Mac:~ yay$ brew doctor
    Error: Homebrew doesn't know what compiler versions ship with your version
    of Xcode (5.0.2). Please `brew update` and if that doesn't help, file
    an issue with the output of `brew --config`:
      https://github.com/mxcl/homebrew/issues
    
    Thanks!
    

Ein empfohlenes "Brew-Update" bringt folgendes Zutage:

    
    thafakers Uber-Mac:~ yay$ brew update
    error: Your local changes to the following files would be overwritten by merge:
    	Library/Formula/assimp.rb
    	Library/Formula/stunnel.rb
    Please, commit your changes or stash them before you can merge.
    Aborting
    Error: Failure while executing: git pull -q origin refs/heads/master:refs/remotes/origin/master
    

Homebrew läuft also in dieser Config auf Mavericks 10.9 nicht mehr - und es gibt momentan auch noch keine Abhilfe.

Wir melden uns wieder.
