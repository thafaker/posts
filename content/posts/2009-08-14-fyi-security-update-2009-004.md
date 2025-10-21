---
title: [FYI] Security Update 2009-004
slug: fyi-security-update-2009-004
date_published: 2009-08-14T19:33:48.000Z
date_updated: 2018-08-22T09:39:01.000Z
---

![image](//picdump.thafaker.de/2009/08/image.png) [...] Apple veröffentlichte soeben das [**Security Update 2009-004**](http://support.apple.com/kb/HT3776?viewlocale=de_DE&amp;locale=de_DE) für Mac OS X 10.5.8 und 10.4.11 (Intel, PPC). Es schließt eine Sicherheitslücke in der DNS-Software BIND, die (auch) in Mac OS X steckt: "A logic issue in the handling of dynamic DNS update messages may cause an assertion to be triggered. By sending a maliciously crafted update message to the BIND DNS server, a remote attacker may be able to interrupt the BIND service. The issue affects servers which are masters for one or more zones, regardless of whether they accept updates. BIND is included with Mac OS X and Mac OS X Server but it is not enabled by default. This update addresses the issue by properly rejecting messages with a record of type 'ANY' where an assertion would previously have been raised." Das Update ist 10,1 MB groß und erfordert einen anschließenden Neustart. [...]

(**[via (archiviert)](http://web.archive.org/web/20090909102852/http://www.fscklog.com/)**)

**Ressourcen**:     
- [2**009-004**](http://support.apple.com/downloads/DL882/en_US/SecUpd2009-004Intel.dmg) (*Intel*)     
- **[2009-004](http://support.apple.com/downloads/DL881/en_US/SecUpd2009-004PPC.dmg)** (*PPC*)     
