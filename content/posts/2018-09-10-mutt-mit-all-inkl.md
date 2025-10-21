---
title: mutt mit all-inkl
slug: mutt-mit-all-inkl
date_published: 2018-09-10T11:52:34.000Z
date_updated: 2018-10-20T12:13:50.000Z
tags: mutt, mutt-ng, all-inkl.com, mutt.rc, settings, imap, terminal, console, ssh, how to, how-to, anleitung, howto
excerpt: In diesem Artikel erklären die Jungs von thafaker.de, wie ihr den Kommandozeilen-EMail-Client mutt dazu nutzen könnt, euer IMAP Konto von All-Inkl.com abzurufen.
---

*Well*… ihr kennt mich. Ich tue oft Dinge. Diesmal konfiguriere ich Mutt, um damit auf mein EMail-Postfach bei All-Inkl.com zugreifen zu können. Via IMAP. Was gar nicht so einfach ist. Und deshalb schreibe ich es auf. Für alle, die irgendwann mal auf die gleiche Idee kommen sollten… Oder schlussendlich auch für mich selbst, der es bis dato wieder vergessen haben dürfte. 

### Mein Setup

Ich habe bei all-inkl.com früher alle meine Domains betrieben. Das ist heute nicht mehr so, heute liegt thafaker.de beispielsweise bei uberspace.com. Denn uberspace bietet SSH-Zugang[[1]](#fn1), läuft auf CentOS und ist irgendwie… *cool*. Weil ich aber damals eben bei all-inkl.com angefangen habe, liegen meine EMail-Konten noch dort. Genau genommen habe ich dort ein zentrales Email-Konto, welches all meine bestehenden Email-Konten anderer Anbieter, sei es nun Googlemail, GMX oder *weißdergeier*, einsammelt. Damit ich meine EMails an einer zentralen Stelle einsammeln kann. Und diese rufe ich ab. Per IMAP. Meine Mails verbleiben also auf meinem Server, und ich rufe sie mit dem Telefon, dem einen Computer, dem anderen Computer oder gar per Webinterface, ab. Das ist cool. Sie sind dadurch gesynct. Die Ordner. Die Mails. Gelesen/Ungelesen. Auf allen Geräten gleich. Aber ich muss euch sicher nichts über die Vorzüge von IMAP erzählen. Also zurück zum Eigentlichen.

### Was ist eigentlich mutt?

Mutt ist ein schlanker, textbasierter E-Mail-Client für Unix oder Linux. Mutt arbeitet im Textmodus und ist damit in Textfenstern, auf Rechnerkonsolen und mit ssh oder telnet in vielen Umgebungen einsetzbar. Ich nutze mutt auf der Konsole, im Terminal, via SSH. Ich finde das gut.

![mutt email client](__GHOST_URL__/content/images/2018/09/maxresdefault-1.jpg)Mutt EMail Client in Action

### mutt.rc all-inkl.com IMAP settings

Wie ihr Mutt grundsätzlich installiert, darauf möchte ich hier nicht eingehen. Dazu gibt es manigfaltige Anleitungen im Netz. Für jedes OS. Für jede Art Linux. Ich nutze *Ubuntu 16.04. LTS*[[2]](#fn2). Ich will nur eben die URL-Settings für den IMAP-Account aufzeigen, damit sich Mutt via imapS in euren Account verbinden kann.

So sieht meine **~/.muttrc** Datei aus.

    ### IMAP Email Login mit all-inkl.com 
    # Automatically log in to this mailbox at startup setspoolfile="imaps://BENUTZERNAME:KENNWORT@SERVER.kasserver.com/" 
    set folder="imaps://SERVER.kasserver.com/" 
    set record="=Sent" 
    set postponed="=Drafts" 
    

**Benutzer**: Klar, euer Login (z.B. der vom Webmailer)
**Kennowrt**: Klar, euer Login (z.B. der vom Webmailer)
**Server**: bei mir heißt er *wXXXXeb9*.kasserver.com

Das wars. Mit diesen Settings sollte sich mutt automatisch beim Start bei eurem IMAP Konto von All-Inkl.com einloggen und die Mails im Posteingang anzeigen.

*Work in Progress*, mehr habe ich derzeit noch nicht versucht. Es fehl noch Ordner und SMTP Settings.

#### SMTP mit Mutt und All-Inkl.com

Hier geht es bald weiter.

---

1. 
Ich weiß, auch bei All-Inkl.com gibt es Hostingpakete mit SSH-Zugang. [↩︎](#fnref1)

2. 
Dies ist die *Long Term Suppport* Version, das heißt dieses Ubuntu wird länger als andere Ubuntu-Versionen mit Sicherheitsupdates versorgt - und man muss nicht upgraden. [↩︎](#fnref2)
