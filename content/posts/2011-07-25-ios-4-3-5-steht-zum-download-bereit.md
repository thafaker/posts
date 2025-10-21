---
title: iOS 4.3.5 steht zum Download bereit
slug: ios-4-3-5-steht-zum-download-bereit
date_published: 2011-07-25T18:20:23.000Z
date_updated: 2018-08-22T09:38:35.000Z
---

Bereits zehn Tage nach dem letzten iOS Update auf [Version 4.3.4](__GHOST_URL__/ios-4-3-4-jailbreaker-finger-weg/) steht seit eben Version 4.3.5 zum Download bereit. Dies beseitigt eine Sicherheitslücke im Zertifikat-System: Fixes a security vulnerability with certificate validation.

> Impact: An attacker with a privileged network position may capture or modify data in sessions protected by SSL/TLS

Ein Angreifer kann den verschlüsselten Datenverkehr mit einem manipulierten Zertifikat belauschen und modifizieren, da iOS 4.3.4 nicht überprüft, ob der Aussteller eines Zertifikats tatsächlich zur Ausstellung von Zertifikaten berechtigt ist, also das CA-Bit in den sogenannten Basic Contraints gesetzt ist. Jedermann kann mit einem gültigen Zertifikat also beliebige weitere Zertifikate, etwa für paypal.com oder die Domain der Hausbank, erstellen, die iOS dann klaglos als gültig anerkennt.

Die Version kommt als Build 8L1 und ist für das GSM iPhone 4, iPhone 3GS, alle iPads, sowie die dritte und vierte iPod touch Generation. Eine separate Version iOS 4.2.10 (Build 8E600) ist für das CDMA iPhone verfügbar.
[![Bildschirmfoto 2011-07-25 um 20.11.54](//picdump.thafaker.de/2011/07/Bildschirmfoto-2011-07-25-um-20.11.54-580x422.png)](http://picdump.thafaker.de/2011/07/Bildschirmfoto-2011-07-25-um-20.11.54.png)

Jailbreakern wird geraten, weder iOS 4.3.4 noch 4.3.5 zu installieren.

PS: Übrigens ist dies eine [neun Jahre alte Sicherheitslücke](http://www.heise.de/mac-and-i/meldung/Apples-iOS-anfaellig-fuer-neun-Jahre-alte-SSL-Schwachstelle-1285472.html), langsam wird es peinlich.

**Direkt-Download**:

- [iPhone 4 GSM](http://appldnld.apple.com/iPhone4/041-1966.20110721.V3Ufe/iPhone3,1_4.3.5_8L1_Restore.ipsw)
- [iPhone 4 CDMA](http://appldnld.apple.com/iPhone4/041-1959.20110721.jvP29/iPhone3,3_4.2.10_8E600_Restore.ipsw) (iOS 4.2.10)
- [iPhone 3GS](http://appldnld.apple.com/iPhone4/041-1965.20110721.gxUB5/iPhone2,1_4.3.5_8L1_Restore.ipsw)
- [iPad 2 Wi-Fi](http://appldnld.apple.com/iPhone4/041-1960.20110721.UsAO4/iPad2,1_4.3.5_8L1_Restore.ipsw)
- [iPad 2 GSM](http://appldnld.apple.com/iPhone4/041-1961.20110721.zigyd/iPad2,2_4.3.5_8L1_Restore.ipsw)
- [iPad 2 CDMA](http://appldnld.apple.com/iPhone4/041-1962.20110721.rWxrf/iPad2,3_4.3.5_8L1_Restore.ipsw)
- [Original iPad](http://appldnld.apple.com/iPhone4/041-1957.20110721.6UHaN/iPad1,1_4.3.5_8L1_Restore.ipsw)
- [iPod touch (fourth-generation)](http://appldnld.apple.com/iPhone4/041-1963.20110721.Huant/iPod4,1_4.3.5_8L1_Restore.ipsw)
- [iPod touch (third-generation)](http://appldnld.apple.com/iPhone4/041-1964.20110721.P9Cg3/iPod3,1_4.3.5_8L1_Restore.ipsw)
