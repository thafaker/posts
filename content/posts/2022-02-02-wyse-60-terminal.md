---
title: WYSE 60 Terminal SIEMENS SME
slug: wyse-60-terminal
date_published: 2022-02-02T13:15:00.000Z
date_updated: 2022-02-22T18:33:55.000Z
tags: terminal, dumb terminal, rs232, wifi232, serial, linux, screen, wyse wy60, retrobattlestation, vintage, vintage computing
---

Mir ist ein **Terminal **zugeflogen, ein echtes Terminal. Im deutschsprachigen Raum früher auch *Datensichtgerät* genannt. So ein Teil, was man damals z.B. in Bibliotheken nutzte um sich im Katalog über Schriften zu informieren oder die an einem großen Zentralrechner angeschlossen in einer Bank standen. Ein Terminal selbst ist dabei wie ein Bildschirm, auch dumb-Terminal genannt, der über Kommunikations- und wahlweise weitere wie Druckeranschlüsse verfügt und ansonsten sein Gehirn aus einem Großrechner bezieht. Diese kann er per Modem anrufen oder mit ihm über eine serielle Verbindung kommunizieren. Recheneinheit und Terminal sind also meist räumlich getrennt.
![WYSE 60 Terminal](__GHOST_URL__/content/images/2022/02/s-l1600.jpg)WYSE 60 Terminal
Bekannte Terminals sind der **DEC VT100** ([Link](https://en.wikipedia.org/wiki/VT100#/media/File:DEC_VT100_terminal.jpg)) (dieser wurde auch gleich zum Standard) und weitere des Herstellers. Diese redeten z.B. mit PDP-11 (oder der legendären VAX) oder ähnlich großen Computer-Mainframes. Andere gab es von IBM und eben auch von WYSE.

Die ab etwa 1977 allmählich einsetzende Verbreitung der Personal Computer hat die Terminals mittlerweile aus den meisten Büros verdrängt. Viele Terminals sind durch Terminalemulationen ersetzt worden, die auf einem PC laufen. Bis heute sind Terminals aber in einigen Bereichen verbreitet.

![](__GHOST_URL__/content/images/2022/02/s-l1600-1.jpg)

![](__GHOST_URL__/content/images/2022/02/s-l1600-2.jpg)

![](__GHOST_URL__/content/images/2022/02/s-l1600-3.jpg)

![](__GHOST_URL__/content/images/2022/02/s-l1600-4.jpg)

![](__GHOST_URL__/content/images/2022/02/s-l1600-5.jpg)

![](__GHOST_URL__/content/images/2022/02/s-l1600-6.jpg)

![](__GHOST_URL__/content/images/2022/02/s-l1600-7.jpg)

![](__GHOST_URL__/content/images/2022/02/s-l1600-8.jpg)

![](__GHOST_URL__/content/images/2022/02/s-l1600-9.jpg)

SIEMENS SYSTEMS SME WYSE 60 Terminal
Wie man an der Rückseite gut erkennen kann, hat dieses Terminal zwei RS232 Anschlüsse die auch selbiges Protokoll sprechen. Man kann sie also per seriellem Kabel mit einem Modem und einem Drucker verbinden. Ich habe es mit meinem LINUX-Server getan, dieser spawnt ein echtes Terminal und hat eben so einen Anschluss. Das funktioniere problemlos. Allerdings wollte ich noch etwas mehr ausprobieren.

Er kommt mit einer großartigen Tastatur mit diesem sehr guten Klicksound, eine Tastatur für Schreiber. Die Tasten funktionieren immer noch problemlos, sie ist von guter Qualität. Mein WYSE 60 stammt von SIEMENS.

"Warum nun so ein altes Terminal", mag man sich fragen. Zurecht. Ich liebe diese Nostalgie. In der grauen Vorzeit des Internets, als Wählverbindungen Standard und sehr teuer waren, als es kein buntes Web gab, als man Buchstaben über dünne Leitungen schickte, da gab es die große Welt der BBS. Bulletin Boards. Schwarze Bretter die man anrufen und in die man sich einwählen konnte. Über diese konnte man Nachrichten versenden, mit anderen kommunizieren. Es wurde Software getauscht und Ideen ausgeheckt. Es war eine eigene Welt. In Deutschland gab es z.B. das **Mausnet**, ein Netzwerk aus *Mailboxen*. Ein Mailboxnetz ist eine Ansammlung von miteinander über Telefonleitungen verbundenen Mailboxen. Eine Mailbox (daher der Name, english bulletin board system (BBS)) ist ein privat betriebenes Rechnersystem. Es nutzt Datenfernübertragung zur Kommunikation und zum Datenaustausch. Berühmte Beispiele für ein Mailboxnetz waren das FidoNet, Z-Netz und das MausNet.

**Newsgroups** fanden in dieser Zeit auch schon statt. Alles über Text oder ASCII Art. Und genau diese Welt existiert in einer nostalgischen Form wieder und weiter. Alte Haudegen der 80er haben ihre BBS (oft mit selbst geschriebener Software) reaktiviert und sie ans Internet angeschlossen, sie sind nun per Telnet erreichbar und funktionieren wie damals. Es hat sich eine kleine Community gebildet und so kann man an wieder an dieser Welt teilnehmen. Auch kann man mit einem Terminal auf seinen eigenen Server zugreifen und ihn als Bildschirm für die Console nutzen. Kurzum, eine schöne Spielerei.
![Screenshot of an BBS (C) https://www.nightfallcrew.com/16/05/2008/hidden-power-bbs-screenshot/x](__GHOST_URL__/content/images/2022/02/bbs001.png)Screenshot of an BBS (C) https://www.nightfallcrew.com/16/05/2008/hidden-power-bbs-screenshot/
Und das folgt als nächstes, going online with WYSE 60.

## Wifi232 Serial-Wifi Adapter

Ich habe vor langer Zeit von [http://ittybitty.space (archiviert)](http://web.archive.org/web/20220106214430/https://ittybitty.space/) einen **RS232 Wifi** Adapter erworben, diesen wollte ich damals mit meinem Atari ST nutzen. Er verhält sich wie ein Modem was mit AT Befehlen bedient werden kann, verbindet sich aber mit dem heimischen WLan und stellt so eine Internetverbindung her. Man kann sich damit prima per Telnet in BBS einloggen oder auf seinen eigenen Telnet-Server zugreifen (Telnet ist unsicher, man sollte es nur mit Bedacht im Heimnetz laufen lassen) und sich so die weite Terminal-Netz-Textwelt erschließen. *Mega gut*.
![RS232 Wifi Modem IttyBitty Modulator](__GHOST_URL__/content/images/2022/02/IMG_4062-1.jpg)RS232 Wifi Modem IttyBitty Modulator
Und so lag der Wunsch nahe diesen Adapter am WYSE 60 zu versuchen. Und siehe da, es funktioniert. Nachdem ich die Defaults resettet und die Einstellungen des Terminal ein wenig durchgespielt hatte, konnte ich tatsächlich mit 300 Baud auf mein Wifi-Modem zugreifen. Kurz die Befehle gecheckt setzte ich es auf 9600 Baud und schwupps, war ich mit einem BBS verbunden. 

Mit einer Telnet-Verbindung zu meinem Linux-Server (Ubuntu 20.04) funktionierte die VT100 Emulation am besten. Das Terminal kann viele verschiedene Emulationen aber jedes Linux hat für Terminal quasi VT100 als Standard. Ein freundliches export TERM=VT100 brachte den erwünschten erfolg und fortan kann man über das Terminal genau so gut, nein schöner, arbeiten wie z.B. mit Putty oder iTerm2 unter MacOS.

Was für ein großartiges Retro-Feeling. :)
![Verbindung WYSE WY60 Terminal zu bbs.fozztexx.com](__GHOST_URL__/content/images/2022/02/IMG_4059.jpg)Verbindung WYSE WY60 Terminal zu bbs.fozztexx.com
Das RS232 Wifi Modem verhält sich dabei als Adapter wie ein Modem immer gleich. Es wird über klassische AT-Befehle gesteuert. Sobald man mit seinem Computer oder Terminal mit dem Modem (RS232 Adapter) kommunizieren kann, verbindet man sich mit seinem Wifi und kann sich dann via Telnet irgendwo einloggen als würde man früher mit einem Modem eine Verbindung aufbauen. Die Standard-Baud-Rate beträgt 300. Der IttyBitty kann seine Einstellungen im NVRAM speichern und so muss nicht jedes mal wieder die Grundkonfiguration vorgenommen werden. Auch 10 Schnellspeicherplätze für Verbindungen gibt es. *Grandios*.

![](__GHOST_URL__/content/images/2022/02/IMG_4057.jpg)

![](__GHOST_URL__/content/images/2022/02/IMG_4059-1.jpg)

![](__GHOST_URL__/content/images/2022/02/IMG_4061.jpg)

![](__GHOST_URL__/content/images/2022/02/IMG_4062.jpg)

Mein Terminal in Aktion:

## AT Befehle

- Ändern der BAUD Rate: AT$SB=N (N=300,1200,2400,4800,9600,19200,38400,57600,115200)
- WiFi SSID einstellen: AT$SSID=YourWiFiSSID
- WiFi Password einstellen: AT$PASS=YourWiFiPassword
- Zum WiFi verbinden: ATC1
- Aktuelle Einstellungen im NVRAM speichern: AT&W
- Via TCP einen Host anrufen: ATDTsome.bbs.com:23
- TELNET anschalten: ATNET1
- Wie ist meine IP: ATIP
- Per HTTP GET request etwas laden: ATGEThttp://host:80/path
- Disconnect: +++ (following a delay of a second)
- Schnellspeicher: ATDSN (N=0-9)
- Schnellspeicher wählen: AT&ZN=HOST:PORT (N=0-9)
- Alle Kommandos gibt es per AT? oder mit ATHELP

## Ressourcen

- [WYSE 60 Handbuch](http://thafaker.crabdance.com/files/Wyse_WY60_Users_Guide.pdf) (PDF)
- [IttyBitty Modulator (archiviert)](http://web.archive.org/web/20220203071349/https://ittybitty.space/modulator/)
- [Liste mit aktiven BBS (archiviert)](http://web.archive.org/web/20220118114427/https://www.pcmag.com/news/7-modern-bbses-worth-calling-today)
