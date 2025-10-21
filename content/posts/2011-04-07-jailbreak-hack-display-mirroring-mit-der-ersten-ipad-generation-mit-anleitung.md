---
title: "Jailbreak-Hack: Display-Mirroring mit der ersten iPad-Generation (mit Anleitung)"
slug: jailbreak-hack-display-mirroring-mit-der-ersten-ipad-generation-mit-anleitung
date_published: 2011-04-07T09:21:00.000Z
date_updated: 2018-08-22T09:38:38.000Z
---

[![ipad-jailbreak](//picdump.thafaker.de/2011/04/ipad-jailbreak.jpg)](http://picdump.thafaker.de/2011/04/ipad-jailbreak.jpg) Da es sich nicht um eine Software handelt die extra installiert werden muss, sondern nur um die Änderung einer *.plist-Datei ((*.plist-Dateien muss man häufig mal ändern, damals bereits beim [64-Bit-Modus von Snow Leopard](__GHOST_URL__/snow-leopard-64-bit-und-so/))), will ich jetzt auch mal eben über die Möglichkeit berichten, dass man das exklusiv mit und nur für das iPad 2 beworbene und eingeführte [Display-Mirroring](http://www.apple.com/de/ipad/features/mirroring.html) auch auf einem iPad Classic (ich nenne es jetzt einfach mal so) benutzen kann. Dieser *Präsentationsmodus* über den ‘Digital AV Adapter’, bei dem Spiele, Anwendungen und der komplette Homescreen übertragen werden, war bislang ausschließlich und wie oben schon erwähnt, exklusiv dem iPad 2 vorbehalten.

Das iPhone-Blog hat den *Hack* durchgeführt und per Video dokumentiert, für die nur 256MB Speicher des iPad Classic funktioniert das ganze wohl sehr zufriedenstellend und ist laut Video einer der wenigen Gründe für einen Jailbreak.

Wie man ein [iPad jailbreaken](__GHOST_URL__/jailbreak-untethered-jailbreak-fuer-ios-4-3-1-verfuegbar-pwnagetool/) kann, haben wir [hier](__GHOST_URL__/jailbreak-untethered-jailbreak-fuer-ios-4-3-1-verfuegbar-pwnagetool/) ausführlich und schön bebildert beschrieben, übrigens.

## Anleitung

Die kurze Anleitung, auf [Nature’s Eye Studios](http://www.natureseyestudios.be/blog/enable-display-mirroring-on-first-gen-ipad/) dokumentiert, könnte nicht einfacher ausfallen. In der Datei `K48AP.plist`, die in `system/library/coreservices/springboard.app/` liegt, fügt man einen neuen Eintrag (`“display-mirroring” boolean YES`) hinzu und startet das Gerät neu. Wer zum Bearbeiten der Datei kein Xcode installiert hat, kann beispielsweise [PlistEdit Pro](http://www.apple.com/downloads/macosx/development_tools/plisteditpro.html) verwenden oder sich mit einem ganz normalen Texteditor behelfen.
