---
title: Neues Jahr - neuer Server
slug: neues-jahr-neuer-server
date_published: 2024-01-21T14:52:57.000Z
date_updated: 2024-01-26T11:08:06.000Z
tags: ghost, ghost 5.76.0, uberspace, cloud, free tier, oracle cloud
---

Hallo Freunde, wie ich in [folgendem Artikel](__GHOST_URL__/ghost-5-fly-io-kostenlos-free/) bereits angerissen habe, suche ich nach einer Alternative für thahipster.de, weil Uberspace den Support für Ghost, mein CMS, beendet hat. Dies hat verschiedene Gründe, der größte ist wohl der Drop von **MariaDB** seitens Ghost. Ghost unterstützt ausschließlich **MySQL8**. 

Versteht mich nicht falsch, ich liebe den Uberspace, aber ich liebe auch Ghost. Ghost lief auch noch, allerdings in einer alten Version die bekannte Sicherheitslöcher beinhaltet. Nach etlichen Tagen und viele Versuchen Ghost doch irgendwie zu aktualisieren habe ich dort aufgegeben… und mich nach Alternativen umgeschaut.

Und nun habe ich sie gefunden. thahipster.de läuft auf **Oracle Cloud** mit zwei Instanzen in einem virtuellen Netz: eine für Ghost und eine für die Datenbank. Thahipster beherbergt knapp 4900 Artikel und mit den zugehörigen Bild- und weiteren Daten ist das nicht gerade wenig.
![thahipster.de 4081 online Article](__GHOST_URL__/content/images/2024/01/Bildschirmfoto-2024-01-21-um-15.53.04.png)thahipster.de 4081 Article online
**[UPDATE**] Wie das alles geht und was man tun muss, damit man eine kostenlose Oracle Always Free Instanz mit vollem Ubuntu 22.04 und Ghost bekommt, das erkläre ich in folgendem Artikel:
[

Teil 1 - Wie man sich kostenlos eine virtuelle Server-Instanz mit Ubuntu 22.04. klickt und damit GHOST betreibt

Teil 1 - Ich werde in dieser Blogreihe darüber berichten, wie man sich bei Oracle Cloud registriert, eine kostenlose Instanz klickt, die Virtuelle Maschine startet, diese Maschine als Webserver konfiguriert und letztendlich Ghost nebst Datenbank installiert.

![](__GHOST_URL__/content/images/size/w256h256/2019/06/logo.png)thahipster.deHerr Montag

![](__GHOST_URL__/content/images/2024/01/oracle_cloud-1.PNG)
](__GHOST_URL__/wie-man-sich-kostenlos-zwei-virtuelle-server-instanzen-mit-ubuntu-22-04-klickt-und-betreibt/)
---

Ich migriere gerade noch ein wenig, aber thahipster.de, seine Subdomains, das Commenting-System ([ISSO](https://isso-comments.de)) sowie die freie Trackingsoftware [fathom](https://usefathom.com/lite) laufen bereits wieder.

Ich werde das alles in eine Anleitung verpacken und entspannt niederschreiben - damit auch ihr in den Genuss von einem always free **Oracle Free Tier** kommt und dort kostenlos Ghost betreiben könnt.

### Was funktioniert?

- Kommentar-System: yes
- fathom: yes
- thahipster.de: yes

**Die Migration ist erfolgreich abgeschlossen.**

[**UPDATE**] Okay, die Kommentar-Migration ist also noch nicht ganz geglückt. Sie werden zwar mittlerweile unter den Artikeln korrekt angezeigt, jedoch ist es nicht möglich, neue Kommentare zu verfassen. Die SQLite3 Datenbank scheint nicht zu speichern, immerhin funktioniert der Kontakt der Website zum Commenting-Server allerdings schon mal.

*Herzlichst, thahipster*
