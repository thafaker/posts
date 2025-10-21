---
title: Snow Leopard 64 Bit und so
slug: snow-leopard-64-bit-und-so
date_published: 2009-08-26T16:28:34.000Z
date_updated: 2018-08-22T09:39:01.000Z
---

![Bildschirmfoto 2009-08-26 um 17.54.06](//picdump.thafaker.de/2009/08/Bildschirmfoto-2009-08-26-um-17.54.06.jpg)
Mein Schnee-Leopard **Build 10A432** rennt praktisch problemlos. Es bootet sogar im 64-Bit-Modus, aber auf meinem iMac nur, wenn man die Zahlen 6 und 4 beim Einschalten gedrückt hält. Verrückt, wah? Yo, Apple hat das eingebaut weil sie ihren eigenen Geräten auch generell verbieten, von einem 32-Bit-EFI eine 64-Bit SchneeLeo zu starten. Obwohl es technisch gar kein Problem darstellt. Dies ist nun quasi der Grund, warum OS X 10.6 auf allen Macs, außer den XServe-Modellen im 32-Bit-Modus starten wird. Weiterhin ein dicker Hund ist wohl, dass sich heraus gestellt hat, das selbst auf aktuellen Macbooks mit 64-Bit-EFI der SL ausschließlich im 32-Bit Modus starten lässt. Obwohl die CPU darin 64-Bit fähig ist. Ein dicker Hund in meinen Augen.

Ein weiteres Riesenproblem für die jeweiligen User wird wohl sein, das der Ur Mac-Pro, nämlich **MacPro1,1** ebenfalls kein 64-Bit Snow Leopard fahren kann darf.

**Hier eine Liste wie es welches Gerät betrifft**:
![Bildschirmfoto 2009-08-26 um 17.57.41](//picdump.thafaker.de/2009/08/Bildschirmfoto-2009-08-26-um-17.57.41.jpg)
Nur dort, wo ***Capable*** steht, wird 10.6 über die Tastenkombination in 64-Bit starten, kein anderes Gerät sonst kann es ausführen. Ich selbst besitze einen iMac8,1 mit 3,06 GHz und 24" der zum Glück *Capable* ist. Keine Macbooks, kein MacPro1,1

Ob man nun ein 32-Bit oder 64-Bit EFI hat, kann man mit der folgenden Eingabe im Terminal heraus finden:

`ioreg -l -p IODeviceTree | grep firmware-abi`

Als Antwort sollte Terminal.app folgendes sagen:

` | |   "firmware-abi" = <"EFI64">`

Das `<"EFI64">` sagt bei mir aus, dass mein iMac ein 64-Bit EFI hat, es ist natürlich auch `<"EFI32">` als Antwort möglich.

[**Netkas** (archiviert)](http://web.archive.org/web/20090831000223/http://netkas.org:80/?p=127) hat aufgezeigt, wie man diese 6 und 4 Blödheit übergehen kann. Um diese Restriktion mit dem dauerhaften Tastendrücken auszuschalten, sollte man also folgendermaßen vorgehen:

Diese Datei bearbeiten:

`/Library/Preferences/SystemConfiguration/com.apple.Boot.plist`

Und folgendes von

`<key>Kernel Flags</key>

<string></string>`

in folgendes:

`<key>Kernel Flags</key>

<string>arch=x86_64</string>`

ändern. Das wars soweit, nun sollte bei jedem Boot automatisch der 64-Bit-Kernel geladen werden. Nachprüfen, ob der Mac auch tatsächlich in 64-Bit läuft, kann man mit dem **System-Profiler**:
[![system-profiler](//picdump.thafaker.de/2009/08/system-profiler1-300x249.jpg)](http://picdump.thafaker.de/2009/08/system-profiler1.jpg)

Ansonsten fallen die Änderungen nicht so sehr groß ins Auge, aber das ist wie beim Umstieg von Windows Vista auf Windows Sieben: die Änderungen fanden unter der Haube statt. Doch, ein Detail finde ich gar sehr schrecklich: Quicktime X, zumindest das neue Logo sieht schrecklich aus:
![quicktime_10.6](//picdump.thafaker.de/2009/08/quicktime_10.6.jpg)

Immerhin ist er wirklich sehr viel schneller und nicht mehr so schwerfällig wie früher und rockt jetzt, wie einst der VLC unter Windows.

**Über diesen Mac**:
![schnee-henri](//picdump.thafaker.de/2009/08/schnee-henri.jpg)
