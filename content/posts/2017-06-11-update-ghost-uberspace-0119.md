---
title: [HOW TO] Update Ghost 0.11.X Uberspace
slug: update-ghost-uberspace-0119
date_published: 2017-06-11T16:57:25.000Z
date_updated: 2018-08-22T09:37:36.000Z
tags: ghost, uberspace, howto, how to, anleitung, update
---

Da das kleine Script auf der Uberspace-Website zum Updaten der eigenen Installation nicht funktioniert, habe ich einfach mal die einzelnen Schritte aufgeschrieben, um es per Hand zu machen. Das Script funktioniert nicht, da Ghost sein Download-Directory und die Groß/Kleinschreibung geändert hat. Das ging noch bis Ghost 0.11.3, seitdem nicht mehr. 

Ich habe das Script nicht aktualisiert, sondern vorhin nur kurz per Hand die einzelnen Schritte aufgeschrieben. Die Anleitung funktioniert, wenn ihr damals euer Ghost strikt nach Anleitung von Uberspace installiert habt.

1. 
Ghost stoppen:
`svc -d ~/service/ghost/`

2. 
Backup (das dauert je nach Ghost-Größe richtig lange)
`cp -r ghost ghost-update`

3. 
aktuelle Version von Ghost herunter laden
`wget https://github.com/TryGhost/Ghost/releases/download/0.11.9/Ghost-0.11.9.zip`

4. 
Ghost in ein Verzeichnis entpacken
`unzip Ghost-0.11.9.zip -d ghost-0.11.9`

5. 
alten Ghost-Kern löschen
`rm -rf ghost/core`

6. 
neuen Kern kopieren
`mv ~/ghost-0.11.9/core ghost/core`

7. 
altes Theme Casper löschen
`rm -rf ghost/content/themes/casper/`

8. 
neues Theme kopieren
`mv ~/ghost-0.11.9/content/themes/casper ghost/content/themes/`

9. 
in das heruntergeladene und entpackte Ghost wechseln
`cd ~/ghost-0.11.9/`

10. 
Lizenz und so kopieren
`cp *.js *.json *.md LICENSE ~/ghost`

11. 
ins allgemeine Ghost-Verzeichnis wechseln
`cd ~/ghost`

12. 
neues Ghost installieren
`npm install --production`

13. 
Nun startet ihr Ghost wieder
`svc -u ~/service/ghost/`

14. 
Damit ihr seht was geht, führt ihr folgendes aus
`tail -F ~/service/ghost/log/main/current`

Hier sollte dann irgendwas mit Start stehen:

`@40000000593e7b9518325024 Ghost has shut down @40000000593e7b95183ff454 @40000000593e7b95183ff83c Your blog is now offline @40000000593e7bd61cdae8d4 Help and documentation can be found at http://support.ghost.org/mail. @40000000593e7bd61cdaecbc @40000000593e7be436ee4b44 Ghost is running in production... @40000000593e7be436ee5314 Your blog is now available on http://thafaker.de @40000000593e7be436ee56fc Ctrl+C to shut down`

15. 
Das könnt ihr mit `CTRL + C` wieder beenden.

16. 
Das entpackte ZIP Verzeichnis, den Download, löschen
`rm -rf ~/ghost-0.11.9`

Fertig :-) ✅
