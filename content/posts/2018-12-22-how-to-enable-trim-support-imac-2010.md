---
title: How To Enable TRIM Support iMac 2010
slug: how-to-enable-trim-support-imac-2010
date_published: 2018-12-22T13:34:00.000Z
date_updated: 2019-04-06T15:41:23.000Z
tags: enable trim, trim support osx, macos trim support, ssd, apple, thirdparty
---

Neulich habe ich meinen [iMac um eine interne SSD erweitert](__GHOST_URL__/2018/12/22/Time-to-upgrade-the-iMac/) und dafür das DVD-Laufwerk raus geworfen. Allerdings ergibt sich beim Upgrade ein Problem, auf das ich in diesem Artikel kurz eingehen möchte. Apple deaktiviert nämlich den **TRIM-Support** für alle fremden, *nicht apple-eigenen* SSDs, die man sich im Zubehörmarkt nachträglich in seine Kiste baut. So wie ich. Ein kurzer Blick in den Systemprofiler offenbart das Vermutete, für meine neue SSD ist TRIM nicht aktiviert. 

![](__GHOST_URL__/assets/2018/12/imac/trim1.png)

### Warum aber ist TRIM so wichtig?

Der TRIM Befehl teilt dem Controller mit, dass in Blöcken die gelöscht wurden (als ungültig markiert), nun keine Daten mehr sind. Das ist wichtig, damit der Controller die Daten nicht noch vorhält, die es schon gar nicht mehr gibt. Bei HDDs ist das unwichtig, bei SSDs hingegegen werden die Imhalte nicht mehr weiter mitgeschrieben, wodurch die Schreibzugriffe auf das Laufwerk beschleunigt und zudem die Abnutzungseffekte verringert werden. Die ungültig markierten Blöcke werden dann beim nächsten Löschen ihres Erasable Blocks frei und wieder mitbenutzt. Sonst würde immer nur an einer speziellen Stelle geschrieben und die SSD dadurch schneller *verschleißen*. Ihr seht also, wir brauchen Trim.

### aktiviere TRIM für SSD unter macOS

Seit OS X 10.10.4 kann man TRIM ohne zusätzlich Fremdsoftware und ohne Deaktivierung von Sicherheitsfeatures per Console aktivieren. Folgender Befehl im **Terminal.app** aktiviert TRIM.

`sudo trimforce enable`

Wenn dieser Befehl durchgelaufen ist, rebootet der iMac. Sichert also eure Daten und beendet laufende Programme, bevor ihr den Befehl ausführt. Da dies ein Super-User-Befehl ist, ist das Admin-Kennwort notwendig.

    Jans-iMac:~ apfelhammer$ sudo trimforce enable
    Password:
    IMPORTANT NOTICE:  This tool force-enables TRIM for all relevant attached
    devices, even though such devices may not have been validated for data
    integrity while using TRIM.  Use of this tool to enable TRIM may result in
    unintended data loss or data corruption.  It should not be used in a commercial
    operating environment or with important data. Before using this tool, you
    should back up all of your data and regularly back up data while TRIM is
    enabled.  This tool is provided on an “as is” basis. APPLE MAKES NO WARRANTIES,
    EXPRESS OR IMPLIED, INCLUDING WITHOUT LIMITATION THE IMPLIED WARRANTIES OF
    NON-INFRINGEMENT, MERCHANTABILITY AND FITNESS FOR A PARTICULAR PURPOSE,
    REGARDING THIS TOOL OR ITS USE ALONE OR IN COMBINATION WITH YOUR DEVICES,
    SYSTEMS, OR SERVICES. BY USING THIS TOOL TO ENABLE TRIM, YOU AGREE THAT, TO THE
    EXTENT PERMITTED BY APPLICABLE LAW, USE OF THE TOOL IS AT YOUR SOLE RISK AND
    THAT THE ENTIRE RISK AS TO SATISFACTORY QUALITY, PERFORMANCE, ACCURACY AND
    EFFORT IS WITH YOU.
    Are you sure you wish to proceed (y/N)? y
    
    Your system will immediately reboot when this is complete.
    Is this OK (y/N)?
    

Ganz wichtig, jetzt wird TRIM aktiviert

    Enabling TRIM...
    .
    .
    Operation succeeded. Your system will reboot momentarily, please wait...
    

Ein Blick in den System-Profiler offenbart nun, dass TRIM aktiv ist. Super. :-)

![macOS System Profiler SSD: TRIM aktiv](__GHOST_URL__/assets/2018/12/imac/trim2.png)

Das wars auch schon wieder, bis bald.

---

**Artikelbild**: Photo by [Patrick Lindenberg](https://unsplash.com/photos/1iVKwElWrPA?utm_source=unsplash&amp;utm_medium=referral&amp;utm_content=creditCopyText) on [Unsplash](https://unsplash.com/search/photos/harddrive?utm_source=unsplash&amp;utm_medium=referral&amp;utm_content=creditCopyText).
