---
title: [HOWTO] iOS 10.1 - 10.1.1 Jailbreak
slug: howto-ios-10-1-10-1-1-jailbreak
date_published: 2017-01-11T12:31:03.000Z
date_updated: 2018-08-22T09:37:37.000Z
tags: anleitung, how to, wie geht, jailbreak, iOS 10, 10.1.1, iphone, ipad, hwoto, 10.1, howto
---

HINWEIS: Dieser Jailbreak ist noch in der beta-Phase und sollte nur von erfahrenen Jailbreakern oder Entwicklern benutzt werden, da er diverse Bugs beinhaltet. Wen das nicht stört, der kann sich damit betuen.

Dieser jailbreak funktioniert nur mit iOS 10.1 bis 10.1.1. Dieser Jailbreak ist ein **semi-tethered Jailbreak**. Nach einem Neustart ist der Jailbreak zunächst inaktiv und muss jedes mal neu gestartet werden. Dazu ist es dann notwendig, die `mach_portal app` auf dem Homescreen zu starten. Wenn sie sich automatisch wieder schließt, ist das Gerät wieder Jailbroken. Funktioniert eben noch nicht automatisch, BETA.

#### Unterstützte Geräte

- iPad Pro
- iPhone 6s
- iPhone 6s Plus
- iPhone SE
- iPhone 7
- iPhone 7 Plus

(By default, for iPhone 6s, iPhone 6s Plus and iPhone SE, only Samsung processor chip is supported.

### Vorgehensweise Jailbreak

1. Ladet die `Yalu IPA` von [hier (archiviert)](http://web.archive.org/web/20161228040945/https://yalu.qwertyoruiop.com/) yalu.qwertyoruiop.com herunter. Aktuelle Version: *Beta 3*
2. Laden und startet den `Cydia Impactor` ([hier](http://www.cydiaimpactor.com/))
3. Verbindet euer Gerät mit dem Computer. Öffnet den Cydia Impactor und schiebt per Drag'n'Drop die Yalu IPA von Schritt 1 in den Cydia Impactor.
4. Geht auf Settings -> General -> Device Management -> wählt eure Apple ID und wählt Trust aus.
5. Öffnet die installierte mach_portal app wartet bis sie sich wieder schließt.
6. Jetzt solltet ihr Cydia auf eurem Gerät haben.
7. Das wars, bis zum nächsten Neustart seid ihr Jailbroken!

#### AppSync Causes Boot Loop

Das berühmte AppSync, mit dem man [cracked IPA installieren](__GHOST_URL__/howto-cracked-ipa-gecrackte-apps-unter-ios-9-2/) kann, lässt das Gerät in einen Boot-Loop verfallen. Es startet nicht mehr. Liegt am BETA. Nicht installieren, gibt keine Lösung.

#### ROOT-Passwort wechseln

The jailbreak installs an SSH daemon (dropbear) by default, so change your root password. See FAQ below to learn how.

### FAQ

Q: Should I use this jailbreak?

A: The choice is yours but unless you are fairly experienced, can run terminal commands and can expect and put up with the jailbreak not being stable, then you shouldn't use this. It is a beta and is aimed at developers. Substrate is disabled by default so you need to enable it after each reboot and use of mach_portal.

Q: Is it safe to use the "Erase All Content & Settings" function in Settings?

A: No. If you do this and try to use Cydia, you will get "Could not open file /var/lib/dpkg/status - open (2: no such file or directory)".

Q: Why are my Apple ID and password not accepted by the jailbreak tool?

A: Make sure you don't have a gmail extension address as the id ([myemail+apple@gmail.com](mailto:myemail+apple@gmail.com)). The tool does not understand emails containing the plus sign (use [myemail@gmail.com](mailto:myemail@gmail.com) instead).

Q: How do I fix cellular data, iMessage or Facetime not working?

A: You can run this command via SSH or in a terminal app such as MTerminal.

Q: I get this error message after entering my Apple ID and password: provision.cpp:150 Please Sign in with an app spesific password

A: Go to [https://appleid.apple.com](https://appleid.apple.com) and log in

Click "Edit" on the right side of the "Security" section

Find "APP-SPECIFIC PASSWORDS” and click "Generate Password…"

Enter a label for the password, "Impactor" or whatever you want, and click Create

Copy and paste the generated password into Impactor’s prompt for your account password

Q: Why do I get "failed in buffer_write(fd) (8, ret=-1)" error in Cydia?

A: This happens when there is no more space left in the system partition of your device. To fix this, add [https://coolstar.org/publicrepo](https://coolstar.org/publicrepo) to Cydia and install "Stashing for iOS 9.2 - 10.1.1". If you get the same error while trying to install "Stashing for iOS 9.2 - 10.1.1", remove a few tweaks, install it and then install the tweaks back again. For more information, see this post.

Q: Should I install YUCCA tweaks?

A: No. This could cause issues in the future and it is strongly recommended that you do not install them. See this tweet, this tweet and this comment from saurik, especially the last two paragraphs.

Q: How do I enable substrate?

A: Install Cydia Substrate from Cydia and download MTerminal from BigBoss. Open MTerminal, type 'su' then enter "alpine" as the password unless you changed it. Once done, run '/usr/libexec/substrate' then 'killall -9 SpringBoard' (all without the quote marks). The device will respring. You need to do this after every time you use mach_portal.

Q: Can I install OpenSSH?

A: No. There is already a working SSH that comes with the jailbreak. If you use OpenSSH, it will cause issues with the final jailbreak.

Q: When I use "Restart SpringBoard" in Cydia, I get stuck on a blue screen. What should I do?

A: This happens due to Cydia trying to relaunch backboardd when tapping this. This is broken with this jailbreak so you must use a terminal app (or ssh) and type 'killall -9 SpringBoard'. This does not work with every tweak but seems to be the best method at the moment.

Q: How long does this jailbreak last?

A: You need to reinstall mach_portal every 7 days (unless you have a paid developer account in which case it will last a year).

Q: Does Tweak X work with this jailbreak?

A: Check the compatibility spreadsheet

Q: How do I disable OTA so my device doesn't try to update?

A: Follow this. But the easier way to do this, is to install the tvOS configuration profile

Q: When tapping certain links in Cydia, why does it go grey and not load?

A: This is a bug in the version of Cydia bundled with the jailbreak. If you swipe slightly as you tap, the link will work. There is also a Cydia beta that fixes altogether.

Q: How do I change my root password?

A: In any terminal client, such as NewTerm or MTerminal, (or via ssh by running ssh root@xxx.xxx.x.xx, replacing the x's with your IP address and the password as follows). The default password is "alpine". Once logged in, run "passwd" and type in your new password twice. Then run "passwd mobile" and type in your new password twice.
