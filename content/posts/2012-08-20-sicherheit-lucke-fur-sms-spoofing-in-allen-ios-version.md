---
title: [SICHERHEIT] Lücke für SMS-Spoofing in allen iOS Version
slug: sicherheit-lucke-fur-sms-spoofing-in-allen-ios-version
date_published: 2012-08-20T10:17:47.000Z
date_updated: 2018-08-22T09:39:11.000Z
---

![ios_messages_icon-150x150](//picdump.thafaker.de/2012/08/ios_messages_icon-150x150-100x100.jpg)Der Jailbreaker und Hacker **pod2g** hat eine neu entdeckte Sicherheitslücke vorgestellt, die alle Versionen von iOS betrifft. Mit dieser Lücke ist es für weniger freundlich gesonnene Personen / Cracker / Scammer möglich, SMS Nachrichten im Namen der betroffenen Person zu versenden, ohne dass diese weiß, dass jenes geschieht und der Empfänger das erkennen könnte. 

Das Problem stammt aus dem *User Data Header* (UDH) und dem Umgang damit durch iOS.

> In the text payload, a section called UDH (User Data Header) is optional but defines lot of advanced features not all mobiles are compatible with. One of these options enables the user to change the reply address of the text. If the destination mobile is compatible with it, and if the receiver tries to answer to the text, he will not respond to the original number, but to the specified one. 
> 
> Most carriers don't check this part of the message, which means one can write whatever he wants in this section : a special number like 911, or the number of somebody else.
> 
> In a good implementation of this feature, the receiver would see the original phone number and the reply-to one. On iPhone, when you see the message, it seems to come from the reply-to number, and you [lose] track of the origin.

pod2g beschreibt viele Möglichkeiten, wie bösartige Dritte (TM) diese Sicherheitslücke ausnutzen könnten und welcher Schaden dabei möglich wäre. Dabei sind Dinge wie Phishing durch URLS in der SMS oder eben einfach nur allgemeiner Schaden und Vertrauensverlust für den Sender.

Meistens benötigt der bösartige Dritte allerdings Kenntnisse über den Namen und die Nummer der Person an die sie senden möchte - allerdings können auch einfach Massennachrichten an eine möglichst große Zahl ((wie bei Spam-Mails)) von Empfängern geschickt werden, sodass der eine oder andere vielleicht in die Falle tappt und der Scammer dadurch schon gewonnen hat.

([via](http://www.macrumors.com/2012/08/17/iphone-security-issue-opens-door-to-sms-spoofing/))
