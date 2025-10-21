---
title: "E-Mail mit (Free/MS-)DOS im Jahr 2025: Pegasus Mail"
slug: howto-e-mail-mit-free-ms-dos-im-jahr-2025-pegasus-mail
date_published: 2025-09-06T19:27:56.000Z
date_updated: 2025-09-23T19:00:37.000Z
tags: vintage computing, ms-dos, anleitung, howto
excerpt: Ich habe gestern schon auf meinem kleinen .microblog JanMontag.de ein Schnipsel geteilt, nämlich einen Screenshot und dann auch ein Foto meines Röhrenmonitors, der mir gerade im Jahr 2025 eine Email von MS-DOS 6.22 geschickt hat - und später auch empfangen. 
---

Und deshalb möchte ich hier eine Anleitung teilen. Dies ist also ein HowTo wie man MS-Dos und Derivate so konfiguriert, dass man in der Kommandozeile ohne Windows 3.11/95 Emails senden und empfangen kann. *Just for the fun of it*.

## Eine detaillierte Anleitung zur Nutzung von Pegasus Mail mit modernen E-Mail-Diensten

In den 1990er Jahren, als E-Mails erstmals für die breite Masse zugänglich wurden, war Pegasus Mail für viele von uns in der nicht-UNIX-Welt das erste E-Mail-Programm, das wir benutzten. Wenn man in der UNIX-Welt unterwegs war, waren es pine, elm und mutt, und wenn man MS-DOS oder Windows bis Windows 98 nutzte, war es ziemlich wahrscheinlich **Pegasus Mail**.
![Pegasus Logo von Version 4 - ein Pferd mit Flügeln.](__GHOST_URL__/content/images/2025/09/d4a8b89f18c5c978ff3bb80768950c19994da55b1a3699633f0b4fa3451b526d-600.webp)Pegasus Logo von Version 4
Letztgenanntes existiert immer noch und wird weiterentwickelt ([https://www.pmail.com/](https://www.pmail.com/)). Die aktuelle Version für Windows (einschließlich 10 und 11) ist *Pegasus Mail v4.91 for Windows* [Current offical version] und ist unter [hier](https://pmail.com/downloads.htm) erhältlich. Seit der öffentlichen BETA v4.81 wird dort OAUTH2 für Gmail unterstützt. [[1]](#fn1)

Die letzte bekannte DOS-Version von Pegasus Mail ist 3.50. Die pmail-Architektur (wie wir sie nennen werden) kann man sich als 3 Programme vorstellen (ich hab das als [Dreiklang](https://janmontag.de/friday-05-09-25-20-49) beschrieben):

1. Ein Agent, der die E-Mails vom Server abholt.
2. Ein Programm zum Verwalten und Bearbeiten von E-Mails – liest die Ergebnisse des Abholvorgangs, schreibt neue E-Mails, die versendet werden sollen, verwaltet sie in Ordnern, handhabt Anhänge usw.
3. Ein Agent, der die E-Mails sendet.

Wenn man also die beiden zusätzlichen Hilfspgrogramme hat, kann man mit PMail 3.50 für DOS immer noch gewinnbringend Schritt 2 ausführen. In MS-Dos! *How cool would be that?* Genau!

Hacker **Fred Macall**[[2]](#fn2) hat genau das getan und die beiden "Hilfspgramme" in einem tapferen und sehr erfolgreichen Bestreben gepflegt ([http://macall.net/](http://macall.net/)). Ich gehe davon aus, dass wir bereits einen funktionierenden Packet-Treiber fpr die Netzwerkkarte unter DOS und die wattcp/mtcp-Infrastruktur installiert haben; FreeDOS, standardmäßig z.B. in VirtualBox installiert, erfüllt dies, obwohl ich das auf meinem Vintage PC direkt ausprobiert habe und dort der ganze Kram auch funktioniert. Ich will auf echter Hardware Emails senden und empfangen.

### Installation und Einrichtung

1. Suchen und laden Sie `pmail350.zip` herunter. Vielleicht hier: [https://archive.org/details/pmail-350](https://archive.org/details/pmail-350).
2. Gehen Sie zu [http://macall.net/](http://macall.net/) und holen Sie sich die neuesten Versionen von `PMPULL` und `PMSMTP32`. Das sind Punkt 1 und 3 vom oben beschriebenen Dreiklang.
3. Ich schlage vor, alle 3 Archive zunächst in nebeneinanderliegenden Verzeichnissen zu entpacken. Meine Struktur ist: `c:\freedos\pmail`, `c:\freedos\pmail\pull` und `c:\freedos\pmail\push`. Letztendlich kann man aber später auch alles in das gemeinsame `pmail`-Verzeichnis kopieren.

### Den Pull-Agenten zum Laufen bringen

Zuerst muss der Pull-Agent zum Laufen gebracht werden; sobald er funktioniert, können wir `pmpull.exe` und `pmpull.cfg` in den `pmail`-Ordner kopieren.

1. 
Wechseln Sie (cd) in den `pull`-Ordner und entpacken Sie das Archiv.

2. 
Schauen Sie sich die Dokumentation an und bearbeiten Sie dann die Datei `pmpull.cfg`. Sie enthält viele wirklich nützliche Kommentare und Beispiele. Darin sehen Sie viele Zeilen, die mit `#` beginnen – dies sind Kommentare. Ich lasse sie in dem, was ich Ihnen zeige, weg; sie sind alle in der Zip-Datei vorhanden.

3. 
Die aktiven Zeilen in meiner `pmpull.cfg` sind folgende, wobei ich einen lokalen Server im LAN nutze, der EMails vereit stellt. Ich muss nicht nach außen gehen, aber beispielhaft hier die Konfiguration für GMX, mit einer #Raute auskommentiert:

    my_ip = dhcp
    bootpto=30
    mss=576
    maildir=c:\freedos\pmail\inbox\
    rettime=365
    pop3host=192.168.178.171
    #pop3host=pop.gmx.com:995
    #pop3sec=LegacySSL
    

- Bei Verwendung einer statischen IP müssen Sie Gateway, Nameserver und all das angeben.
- `maildir` ist der Ort, an dem die neuen E-Mails abgelegt werden (erstellen Sie ihn, damit er mit dem Eintrag in der Datei übereinstimmt).
- `pop3host` ist der POP3-Server und seine Portnummer (holen Sie sich dies usually von der Website des Providers).
- `pop3sec` ist das Sicherheitsprotokoll. Der Port ändert sich mit dem Protokoll.
- Wenn Ihr Provider Zwei-Faktor-Authentifizierung verwendet, benötigen Sie ein App-Passwort. Einige Provider bieten diese nicht an, und dann wird dieser Ansatz nicht funktionieren.

4. 
Nun holen Sie die E-Mails ab, indem Sie ausführen:

    c:\freedos\pmail\pull\>pmpull meineemail@server.com meinPasswort
    

- Beachten Sie, dass das Passwort im Klartext vorliegt. Sie sollten es also nicht in eine Batch-Datei schreiben! Es ist am besten, es manuell zu Beginn der Sitzung auszuführen. Da ich das im LAN an meinem Vintage PC nutze, ist mir das aber Schnuppe.
- Kopieren Sie am einfachsten `pmpull.exe` und `pmpull.cfg` in Ihren `pmail`-Ordner und nehmen Sie diesen Ordner in den $PATH der Autoexec.bat auf. Oder wechseln Sie einfach zu Beginn jeder Sitzung in Ihren `pmail`-Ordner.

5. 
Sobald der Pull funktioniert hat, sehen Sie Dateien in `maildir`; sie werden obskure kodierte Namen mit CNM-Erweiterungen haben. Die CNM-Dateien sind die neuen EMails als E-Mail-Dateien.

### Pegasus Mail konfigurieren

1. Führen Sie im `pmail`-Ordner `pconfig.exe` aus.
2. Wählen Sie zunächst "standalone config" und geben Sie dort Ihren Mail-Ordner an. Mindestens Ihr neuer Mail-Ordner muss mit dem in `pmpull.cfg` übereinstimmen, da dies pmail mitteilt, wo es nach neuen E-Mails suchen soll.
3. Verwalten Sie als Nächstes benutzerdefinierte Gateways und erstellen Sie ein neues. Geben Sie hier den korrekten neuen Mail-Ordner ein (wir haben bereits gesehen, dass neue E-Mails `*.cnm` sind, also ist das die Suchmaske für neue E-Mails). Legen Sie Ihren ausgehenden Mail-Ordner fest – dies könnte ein neuer Ordner sein, den Sie erstellen. Ich habe `c:\freedos\pmail\outbox` verwendet.

- **Hinweis**: In `pmsmtp.cfg` und `pmpull.cfg` müssen diese Mail-Pfade einen nachgestellten Backslash haben!!!!
- Das Dateinamenformat muss angegeben werden als: `~d~d.MSG` (dies ist eine pmail-Sprache, aber das Entscheidende ist, dass der sendende Agent MSG-Erweiterungen erwartet, was nicht der Standard von PMAIL ist. Das `~d~d` ist Code für 'denk dir einen eindeutigen Vornamen aus' – denken Sie daran, dass DOS-Dateinamen nur 8 Zeichen haben!)

4. Dann setzen wir das Antwortadressenformat auf: `"~p" <~n>` (Auch dies muss exakt sein; es konstruiert nämlich den Mail-Header, den der sendende Agent erwartet. Dies steht auch alles in der sehr guten Dokumentation.)
5. `Accept SMTP address = Y`
6. Einfache Nachrichtenheader müssen 'Glue' sein (Auch dies ist Teil der Konstruktion der ausgehenden E-Mail, damit der sending Agent findet, was er erwartet, wenn er danach sucht.) Email ist wirklich eine Welt für sich, seit ca 1978. Unfassbar komplex.
7. Wenn Sie all das speichern und pmail ausführen, sollten Sie sich bei pmail mit der eingerichteten E-Mail-Adresse anmelden (Sie können sie als Befehlszeilenargument an pmail übergeben, wenn Sie diesen Schritt routinemäßig sparen möchten – siehe Batch-Datei-Auszug unten) und dann nach neuen E-Mails suchen, falls Sie welche abgerufen haben.
8. Sie können einige Konfigurationen vornehmen (Einstellungen > Allgemeine Einstellungen ist nützlich für Arbeitsverzeichnis, Antwortnamen und Signaturen).
9. Dann könnten Sie eine neue E-Mail schreiben und mit `Strg+Eingabe` "senden". Beenden Sie pmail.
10. In Ihrem `mailout`-Ordner sollten Sie nun eine MSG-Datei haben, die darauf wartet, gesendet zu werden.

### Fußnoten

---

1. 
Generell gilt: *David Harris* ([Wer](https://de.wikipedia.org/wiki/David_Harris_(Programmierer))?) ist der größte! [↩︎](#fnref1)

2. 
Ich nenne ihn einfach Hacker, absolut wohlwollend konotiert, weil ich es großartig finde, dass jemand DOS-Software programmiert und pflegt sodass sie im Jahr 2025 verschlüsselten Transport von EMail z.B. mit GMX ermöglicht. [↩︎](#fnref2)

---
![PMail 3.5 DOS Main Windows](__GHOST_URL__/content/images/2025/09/pmail.png)PMail 3.5 DOS Main Windows
Die originale [Release Website](https://www.pmail.com/whatsnew/new_dos.htm) zu **Pegasus Mail 3.5 for Dos** ist sogar noch verfügbar, ich finde das absolut großartig.

### Den Send-Agent (pmsmtp32) konfigurieren

Jetzt müssen wir `pmsmtp32` konfigurieren. Auch hier gibt es eine recht nützliche Dokumentation.

1. Die Hauptkonfigurationsdatei ist `pmsmtp.cfg` (im `push`-Ordner); meine sieht so aus, ich hab das wieder auf mein LAN gemünzt, in der Konfig auskommentiert steht es für GMX:
    my_ip=dhcp
    bootpto=30
    mss=576
    #b64usrid="***redacted***"
    #b64passw="***redacted***"
    maildir=c:\freedos\pmail\outbox\
    smtphost=192.168.178.171
    #smtphost=mail.gmx.com:587
    #smtpsec=STARTTLS
    

2. Der Hauptkniff für Authentifizierung besteht darin, die Felder `b64userid` und `b64passw` zu erhalten. Dazu können wir pmail selbst verwenden (laut Dokumentation). Dies sind die Anmeldedaten (meist E-Mail-Adresse als Login, b64usrid) und das Passwort, mime-kodiert, und wir können pmail die Kodierung durchführen lassen.
3. Geben Sie in DOS ein:
    copy con pass
    IHRPASSWORT^Z<Eingabe>
    

Das heißt, wir kopieren von der Konsole (Bildschirm) in eine Datei namens `pass`. `<Eingabe>` bedeutet Enter-Taste drücken und `^Z` bedeutet `Strg+Z`. Sie tippen also Ihr Passwort ein, drücken aber NICHT auf Enter (wir wollen kein Enter-Zeichen in der Datei! Es würde kodiert werden und es falsch machen). Stattdessen tippen Sie `Strg+Z`, um DOS das Ende der Eingabe zu signalisieren, und drücken dann Enter.
4. Machen Sie dasselbe für Ihre E-Mail-Adresse. Ungefähr so:
    copy con email
    meineemail@server.com^Z<Eingabe>
    

5. Führen Sie pmail aus.
6. Erstellen Sie eine neue Nachricht und wählen Sie: "'Send a mail message'"; hängen Sie diese beiden Dateien (`pass` und `email`) an und wählen Sie die Kodierung als `Basic Mime`.
7. `Strg+Eingabe`, um den Anhangedialog zu verlassen, und noch einmal, um zu "senden".
8. Beenden Sie pmail.
9. Wechseln Sie in Ihren `mailout`-Ordner und Sie finden 3 neue Dateien. Das ist unsere Nachricht mit den beiden Anhängen. Die Anhänge wurden MIME-Kodiert. Ganz am Ende jeder der Anhangsdateien sollten Sie eine Zeile sehen wie:
    aBfhd5gdhej==
    

Dies ist das mime-kodierte Passwort oder die E-Mail. Kopieren Sie diesen String in die cfg-Datei, wie oben, wo ich '***redacted***' eingefügt habe. Beachten Sie die Verwendung von doppelten Anführungszeichen. Easy, oder?
10. Beachten Sie, dass `pmsmtp.cfg` den ausgehenden Mail-Ordner als `maildir`-Variable hat.
11. Wir können `pmsmtp32.exe` und `pmsmtp.cfg` in den `pmail`-Ordner legen und dort eingeben:
    pmsmtp32
    

Und wenn alles gut geht, wird es Ihre queued Nachrichten finden und senden.

### Automatisierung mit Batch-Dateien

Nun sollte es möglich sein, das Abrufen und Senden aus pmail heraus zu trigger. In der `pconfig` und der Gateway-Konfiguration können Sie einen Sendebefehl einfügen, der basically `\pfad\zu\pmsmtp32` sein könnte, wenn Sie zulassen, dass die Konfigurationsdatei Ihr Passwort enthält, oder `\pfad\zu\meinsend.bat`, wenn Sie eine benutzerdefinierte Batch-Datei zum Senden verwenden (oder eine COM-Datei, wenn Sie den bat2exe-Weg verwenden; siehe unten).

Da das Abrufen der E-Mails ein Klartext-Passwort erfordert, wollen Sie das  nicht innerhalb Ihrer pmail-Sitzung tun, da dies das Speichern des Passworts im Klartext irgendwo erfordern würde. *Aber Sie können, wenn Sie wollen* ...

Eine Sitzung könnte also sein:

1. `pmpull`, um die E-Mails zu holen
2. `pmail`, um zu lesen und zu erstellen
3. `pmsmtp32` zum Senden, ausgeführt aus pmail heraus, wenn das Base64-Passwort in der cfg-Datei ist, oder ohne, wenn Sie es auf der Befehlszeile eingeben.

Nun, offensichtlich ist es möglich, Batch-Dateien zum Ausführen der Pull- und Send-Befehle zu schreiben, aber wie erwähnt werden sie Passwörter enthalten – im einen Fall im Klartext und im anderen Fall sehr schwach kodiert (in Base64 kodierte Zeichenfolgen werden für Leute mit ein wenig Wissen über die Kodierung einfach erkennbar sein). Wenn Sie sich die Mühe machen möchten, könnten Sie Dinge zumindest vor weniger erfahrenen Augen schützen. Es gibt z.B. Programme zum Konvertieren von Batch-Dateien in binäre COM-Dateien (obwohl der Text manchmal im Klartext darin ist); es gibt ausführbare Packer (UPX), die Ihre binary Batch-Datei nehmen und alle menschenlesbaren Komponenten entfernen könnten. Wenn Sie gerne code schreiben, könnten Sie ein C-Programm schreiben, das den Push- oder Pull-Programm ausführt; dann, wenn die C-Quelle nicht auf dem Computer aufbewahrt wird und die Binärdatei mit UPX oder so etwas gepackt ist ... etc. Es ist mühselig und es ist msdos und das nutzt man nicht mehr produktiv und man sollte auch mit email nur herum spielen aber ja.

Heutzutage verlassen wir uns oft auf unser Login-Passwort – oft sind unsere Passwörter im Browser gespeichert, bereit für jeden, der unseren Login-Code knacken kann. Diese Methode ist also nicht so schlecht für die Sicherheit, wie es scheinen mag; aber weil DOS keinen Login-Manager hat, sollten Sie, wenn Sicherheit ein Problem ist, wenn möglich, ein Boot-Passwort im BIOS setzen. :-) Ich weiß ja, niemand nutzt MS-DOS tatsächlich kritisch. Sollte man nicht. Man sollte damit nur spielen und spielen.

Natürlich, wenn jemand Ihren Computer von einer Live-CD/USb bootet, wird er in der Lage sein, alle nicht verschlüsselten Passwörter auf dem DOS-Laufwerk (oder auf einem nicht verschlüsselten Linux-Laufwerk) zu lesen, was bedeutet, dass, wenn der Rechner nicht physisch gesichert ist, ein BIOS-Passwort und Boot-Einstellungen, die kein Booten von externen Medien erlauben. :-)

Wenn wir eine obfuscated Binary zum Abrufen der E-Mails haben (nennen wir sie `mailpull.com`) und eine ähnliche zum Senden (aber von pmail aufgerufen), könnten wir eine `pmail.bat` erstellen und in unseren Pfad legen (`c:\freedos\pmail` in FreeDOS):

    @echo off
    set startdir=%cd%
    cd \freedos\pmail
    mailpull.com
    pmail -u meineemail@server.com
    cd %startdir%
    set startdir=
    

Dies speichert das aktuelle Verzeichnis, wechselt in das pmail-Verzeichnis, holt neue E-Mails, führt pmail aus (was den sendenden Agenten intern aufruft), beendet sich und bringt uns zurück zum Verzeichnis, in dem wir started.

Dies alles setzt voraus, dass Sie nur eine einzige E-Mail-Adresse verwenden möchten. Sie können mehrere Gateways innerhalb von pmail einrichten, aber wenn ich mehr als ein Konto verwenden wollte, würde ich (ich weiß, das ist cheating) probably einfach parallele Installationen von pmail haben, mit einer Reihe von Batch-Dateien – anstatt `pmail.bat` hätte ich `gmx.bat`, `gmail.bat` usw. und würde sie separat ausführen; aber das ist jedem selbst überlassen.

Viel Spaß am Gerät :-)
![](__GHOST_URL__/content/images/2025/09/pmail_dos.png)This article is from 2023 from great Darren in english, here you can find the [origin](https://darrengoossens.wordpress.com/2023/07/01/email-on-freedos-in-2023-pegasus-mail/).
### **Update**: Leave message on Server. 

Ich habe ja ein kleines Setup im Heimnetzwerk laufen, sodass mein Mail-Server via POP3 und IMAP erreichbar ist, je nach Vintage Computing Ability des Clients. Wenn PMail unter MS-DOS nun alle Mails abholt und löscht, wäre das grundsätzlich problematisch. Allerdings ist da etwas in pmpull eingebaut, was dem entgegen wirkt: rettime.
`
# rettime Optional. 

#

# rettime is used to specify how many days PMPULL waits before

# DELE(ting) previously pulled mail items from the POP3

# server. Any value from 0 to 32767 may be specified.

# Mail items won’t be DELE(ted) in the session in which

# they are first received. But, if rettime=0 is

# configured, they may be DELE(ted) in another session

# the same day. Configuring rettime=32767 is as close as

# you can come to getting your mail left on the POP3 server

# forever. 32767 days is close to ninety years.

# A value of twice the rettime= configuration may also be used to

# determine when to prune very old records from PMPULL.MRL,

# PMPULL’s control file. If twice the rettime= value is

# less than 23 days, 23 days will be used for this pruning

# age, instead.

# Any value from 0 to 32767 (days) may be specified.

# By default, rettime=90 (days).

###rettime=32767
`
Setzen wir also 

    rettime=32767

in unserer pmpull.cfg, dann lassen wir gelesene Nachrichten für 99 Jahre auf dem Server - ein Wert der in unserem Leben ausreichen sollte.
