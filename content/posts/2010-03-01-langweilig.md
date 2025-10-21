---
title: Langweilig... [Update]
slug: langweilig
date_published: 2010-02-28T23:03:29.000Z
date_updated: 2018-08-22T09:38:25.000Z
---

[**Update**] Ich habe meine Wlan-Probleme mittlerweile überwunden, aber nicht, weil es mir gelungen ist, den Linksys unter CentOS zum Laufen zu bewegen, sondern weil ich ein neues Board habe. Der Server rennt jetzt in einer 2-Prozessor-Konfiguration mit 2 x Pentium III 1000 MHz auf einem `Gigabyte GA-6VXDC7 ATX,Dual Socket 370` Mainboard mit 768 MB-SD-Ram 133 MHz :-) Er ist zwar nicht wirklich schneller geworden, fühlt sich nun aber mehr nach einem kleinen low-cost-Server an, als vorher.

[![Gigabyte GA-6VXDC7 ATX,Dual Socket 370](//picdump.thafaker.de/2010/03/Gigabyte-GA-6VXDC7-ATXDual-Socket-370.png)](http://picdump.thafaker.de/2010/03/Gigabyte-GA-6VXDC7-ATXDual-Socket-370.png)

Er hat nunmehr 700GB HDD via LVM, basierend auf 4 Festplatten die an 2 CMD0649 HDD-Kontrollern hängen.

Er kann nun richtiges `AVAHI` und spricht darüber `ATALK`, um als vollwertiger TimeMachine Backup Server für die 4 Mac-Clients zu Hause zu fungieren. Das ist zwar alles völlig unnötig, lehrt mich aber doch einiges an generellem Begriffsvermögen und hält mich bei Laune, *kwasi* ^^

> Integer Score:                 846 |||
> Floating Point Score:         1174 ||||
> Memory Score:                  396 |
> Stream Score:                  209 
> 
> Overall Geekbench Score:       807 |||

[**Ursprünglicher Beitrag**]

Was macht der Herr Faker eigentlich, wenn ihm langweilig ist? Richtig, er reaktiviert seinen uralten Linux Server und versucht zwei Wochen lang, WLan gangbar zu machen damit kein Kabel durch den Flur gelegt werden muss. Aber Pustekuchen. Ich habe langsam den Verdacht, dass irgendwelche Hardware in den Ding dafür sorgt, dass er einfriert wenn Wlan aktiviert wird. Das seltsame daran ist nur, dass es bei ner eingebauten PCI Wlan Karte die direkt unterstützt wird, sowie bei nem billigen USB-Wlan-Stick gleichermaßen geschieht.
[![centos_server](//picdump.thafaker.de/2010/02/centos_server-580x457.png)](http://picdump.thafaker.de/2010/02/centos_server.png)

Als OS dient übrigens **CentOS** (**C**ommunity **ENT**erprise **O**perating **S**ystem), das  ist eine Linux-Distribution, die auf der Distribution Red Hat Enterprise Linux (RHEL) aufbaut, und zu dieser binärkompatibel ist. Die Distribution  wird von einer offenen Gruppe von freiwilligen Entwicklern betreut,  gepflegt und weiterentwickelt.

**Server-Specs**:

- Pentium III mit 1GHz
- 512 MB-Ram
- Raid 0 (2 x 40GB UDMA 100)
- diverse alte HDDs zur Weiterverwendung (400 GB)
- ein altes DVD-Rom LW aus nem Powermac G5
- OS: [Centos 5.4](http://centos.org/)

Ich habe nun 2 USB-Wlan Teile (via Ndiswrapper) und eine PCI-Karte die vom Kernel direkt unterstützt wird, versucht. Doch nichts. Entweder kann ich mit `iwconfig` oder ähnlichem die korrekt installierten Ndiswrapper Treiber (`ndiswrapper -l` meldet alles cool und device present) nicht ansprechen, oder das System friert bei Aktivierung sofort ein. Ich werde noch wahnsinnig, denn solch ein Projekt kann ich dann auch immer nicht mehr einfach so ruhen lassen, bis es läuft.

Manchmal findet er mein Wlan, doch meistens nicht, zumindest mit dem **Allnet ALL0263RP** Billigstick. Wenn er eben mal nicht eingefroren ist.

Aktuell versuche ich nun, einen **Linksys WUSB54GSv2** USB Adapter zum Laufen zu bewegen. Unter CentOS wird er aber leider nicht direkt unterstützt, bei Ubuntu lief das. Doch mit **Ndiswrapper** kann ich ihn nicht zum Reden bringen. *Argh*

Ausgabe von `lsusb -v`:

    Bus 001 Device 002: ID 13b1:0014 Linksys
    Device Descriptor:
      bLength                18
      bDescriptorType         1
      bcdUSB               2.00
      bDeviceClass            2 Communications
      bDeviceSubClass         0
      bDeviceProtocol         0
      bMaxPacketSize0        64
      idVendor           0x13b1 Linksys
      idProduct          0x0014
      bcdDevice            0.06
      iManufacturer           1 Broadcom
      iProduct                2 Linksys Wireless-G USB Network Adapter with SpeedBooster
      iSerial                 3 8057
      bNumConfigurations      1
      Configuration Descriptor:
        bLength                 9
        bDescriptorType         2
        wTotalLength           48
        bNumInterfaces          2
        bConfigurationValue     1
        iConfiguration          0
        bmAttributes         0x80
        MaxPower              500mA
        Interface Descriptor:
          bLength                 9
          bDescriptorType         4
          bInterfaceNumber        0
          bAlternateSetting       0
          bNumEndpoints           1
          bInterfaceClass         2 Communications
          bInterfaceSubClass      2 Abstract (modem)
          bInterfaceProtocol    255 Vendor Specific (MSFT RNDIS?)
          iInterface              0
          Endpoint Descriptor:
            bLength                 7
            bDescriptorType         5
            bEndpointAddress     0x81  EP 1 IN
            bmAttributes            3
              Transfer Type            Interrupt
              Synch Type               None
              Usage Type               Data
            wMaxPacketSize     0x0010  1x 16 bytes
            bInterval               1
        Interface Descriptor:
          bLength                 9
          bDescriptorType         4
          bInterfaceNumber        1
          bAlternateSetting       0
          bNumEndpoints           2
          bInterfaceClass        10 CDC Data
          bInterfaceSubClass      0 Unused
          bInterfaceProtocol      0
          iInterface              0
          Endpoint Descriptor:
            bLength                 7
            bDescriptorType         5
            bEndpointAddress     0x82  EP 2 IN
            bmAttributes            2
              Transfer Type            Bulk
              Synch Type               None
              Usage Type               Data
            wMaxPacketSize     0x0040  1x 64 bytes
            bInterval               0
          Endpoint Descriptor:
            bLength                 7
            bDescriptorType         5
            bEndpointAddress     0x03  EP 3 OUT
            bmAttributes            2
              Transfer Type            Bulk
              Synch Type               None
              Usage Type               Data
            wMaxPacketSize     0x0040  1x 64 bytes
            bInterval               0
    Device Qualifier (for other device speed):
      bLength                10
      bDescriptorType         6
      bcdUSB               2.00
      bDeviceClass            2 Communications
      bDeviceSubClass         0
      bDeviceProtocol         0
      bMaxPacketSize0        64
      bNumConfigurations      1
    can't get debug descriptor: Connection timed out

Könnte der Fehler bei dieser letzten Meldung, can't get debug descriptor liegen?

Der `ndiswrapper -l` sagt das:

    [root@centos-server ~]# ndiswrapper -l
    wusb54gsv2 : driver installed
    	device (13B1:0014) present

Und so sieht die Ausgabe von `dmesg | grep ndis` aus:

    [root@centos-server ~]# dmesg | grep ndis
    ndiswrapper version 1.56 loaded (smp=yes, preempt=no)
    usbcore: registered new driver ndiswrapper

Sieht doch eigentlich normal aus, oder?

Nach einem `modprobe ndiswrapper` sagt `iwconfig` jenes:

    [root@centos-server ~]# iwconfig
    lo        no wireless extensions.
    
    eth0      no wireless extensions.
    
    sit0      no wireless extensions.

Oh man... Was noch? Hat jemand eine Idee? Ich habe nun mal diesen ALLNET Stick installier und geladen, da sagt dann dmesg noch weiteres. Das heißt also, er lädt den linksys gar nicht. *Hmm*...

    [root@centos-server Windows XP]# dmesg | grep ndis
    ndiswrapper version 1.56 loaded (smp=yes, preempt=no)
    usbcore: registered new driver ndiswrapper
    usbcore: deregistering driver ndiswrapper
    ndiswrapper version 1.56 loaded (smp=yes, preempt=no)
    ndiswrapper: driver sis163u (OEM,09/30/2004,5.1.1039.1010) loaded
    usbcore: registered new driver ndiswrapper

Kananda ist übrigens just in diesem Moment bei den Olympischen Winterspielen in Vancouver mit 3:2 gegen die USA in der Verlängerung Olympiasieger im Eishockey geworden. Ihr seht, ich kriege doch noch hin und wieder was von meiner Umwelt mit.

Mal schauen, ob er jetzt nach nem Reboot wieder einfriert, oder ob ich WLan erfolgreich aktivieren kann.

[**Update**]

Also er konnte sich mit folgendem Befehl problemlos verbinden:

    wpa_supplicant -iwlan0 -Dwext -c/etc/wpa_supplicant/wpa_supplicant.conf -d

Aber nun habe ich das Problem, dass er Wlan nicht automatisch beim Boot startet. OMG, irgendwie funkioniert ständig irgendwas anderes nicht...

[**Update**]

Es scheint jetzt mit ein paar wiederlichen Einträgen zu funktionieren, er bootet und verbindet sich beim Start. Wahnsinn! Mal sehen ob er das auch nach 2 Tagen noch kann.

[**Downloads**]

So, ich biete hier meine Ndiswrapper-Treiber an.

- **Allnet ALL0263P**: [*.zip](http://picdump.thafaker.de/2010/03/allnet_ndis_xp.zip) (funktioniert bei mir)
- Linksys WUSB54GSv2: *.zip (lief bei mir nicht)
