---
title: Der feine Squid against Werbung ;-)
slug: der-feine-squid-against-werbung
date_published: 2005-07-11T17:23:32.000Z
date_updated: 2018-08-22T09:37:52.000Z
---

Da ich mir aus diversen Gründen einen Squid-Proxy unter Linux installiert habe kam ich auf die glorreiche Idee mit diesem gleich mal Werbung auszufiltern bzw. die Domains zu sperren von welchen sich der Rest der Familie immer irgendwelche Spyware einsammelt (IE) oder komische Tools wie Personal ID Card installiert.

Gesagt, getan!
Nach etwas googlen bin ich dann auf ein Board gestoßen welches eine Liste mit Spy-Domains im Allgemeinen sammelt/verwaltet/erweitert/entlarvt. Diese liste habe ich in eine Datei "domain.deny" in /etc/squid/ kopiert und noch ein paar meiner eigenen "bekannten" URL's hinzugefügt. 
Nun noch schnell die "squid.conf" folgendermaßen konfiguriert: 
Schnell die Access Control List Einstellung:
("acl" ist jeweils nur eine Zeile bis zum nächsten "acl", mein Blog stellt das irgendwie scheiße dar und ich bin zu Unfähig!) 

> `acl domains.deny urlpath_regex -i "/etc/squid/domains.deny"
> ``acl domains dstdom_regex -i "/etc/squid/domains.deny"`

Und das es auch ausgeführt wird: 

> `http_access deny domains.deny 
> http_access deny domains `

Und fertig war die "Verbietenliste" ;-) Hier nun meine Access_Control_Listen_Wörter aus der domain.deny: 
AdProtector 
AdwareHunter
AdWareRemoverGold
.bulletproofsoft.com
internetantispy.com
noadware.net
netpalnow.com
Online PC-Fix SpyFerret 
purityscan.com
puritysweep.com
adwareremovergold.com
sg08.biz
spybouncer.com
spyassault.com
spyban.net
spyblast.com
advertising.com
eBlocs.com
spydeleter.com
209.50.251.182
securetactics.com
onlinepcfix.com
spygone.com
enigmasoftwaregroup.com
spywareremove.com
spybot-spyware.com
spy-killer.com
maxionsoftware.com
spykiller.com
spykillerdownload.com/ 
spykillerpro.com 
solidlabs.com 
spywarebegone.com
freespywarescan.org
www.checkforspyware.com
www.spw2a.com/sc/
spywarecrusher.com
SpywareInfoooo.com 
spywarekilla.com
spywarenuker.com
trekblue.com
trekdata.com
spyware-killer.com
spy-ware-remover.com
spywareremover.com
spywarethis.com
mailwiper.com
ssppyy.com
trackzapper.com
spywarelabs.com
virtualbouncer.com
warnet.com
download-spybot.com
paretologic.com
downloadspybot.com
no-spybot.com
zerospyware.com
zeroads.com
Spyware X Terminator
Bei Kritik/Fragen/Ergänzungen bitte ich um einen Kommentar!
