---
title: Ist da noch jemand mit GMail Problemen?
slug: ist-da-noch-jemand-mit-gmail-problemen
date_published: 2005-06-07T14:51:42.000Z
date_updated: 2018-08-22T09:37:52.000Z
---

Gestern schon wars 3 Stunden lang nicht möglich Emails über *[GMail](http://www.gmail.com/)* (Google Mail) zu empfangen oder zu versenden! Nachdem ich das dann mal mitbekommen habe las ich in meiner Fetchmail.log das hier:

**fetchmail: POP3> USER **[**xxxxxxxxx@gmail.com**](mailto:xxxxxxxxx@gmail.com)
**fetchmail: POP3< +OK send PASS

fetchmail: POP3> PASS *

fetchmail: POP3< +OK [SYS/TEMP] Due to a temporary system problem, this mailbox will seem empty.

fetchmail: POP3> STAT

fetchmail: POP3< +OK 0 0
****fetchmail: Keine Post für **[**xxxxxxxxx@gmail.com**](mailto:xxxxxxxxx@gmail.com)** bei **[**xxxxxxxxx@gmail.com**](mailto:xxxxxxxxx@gmail.com)
**fetchmail: POP3> QUIT

fetchmail: POP3< +OK Farewell.**

Sehr freundlich! Vorallem weil in ner log kurz vorher was stand: You are talking to an empty mailbox…

Aber was mich am meisten nervt: Alle meine Freunde die ich zu einer GMailadresse einlud -die zugegeben viel später als ich meine, ihre registrierten– können Senden/Empfangen. Ich kann mich nichtmal auf der Website einloggen… Warum ist immer nur mein Backend down?
[**Update**]

Auf jedenfall habe ich deshalb nun auf meinem kleinen Rumspielserver *Postfix* installiert. Der sendet nun ohne Probleme alle EMails aus dem Netzwerk, und nur von dort ;-)

Ein obergeiles Howto “[*Postfix in 5 minutes*](http://www.fedoraforum.org/forum/showthread.php?t=53204)” gibts dort im Fedora-Forum!
