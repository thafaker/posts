---
title: [HOW TO] Bootfähigen USB Stick unter OS X erstellen
slug: how-to-bootfahigen-usb-stick-unter-os-x-erstellen
date_published: 2012-06-16T08:08:43.000Z
date_updated: 2018-08-22T09:37:36.000Z
---

![120px-Supertalent_USB-Stick](//picdump.thafaker.de/2010/10/120px-Supertalent_USB-Stick.jpg)Viele OS X und Macuser möchten gern mal ein Linux testen. Dies ist auch gar nicht so schwierig, mit Boot Camp baut man sich eine zweite Partition (mit nur drei Klicks) auf welche man dann easy durch Boot von einer CD eine Linux-Distri installieren kann. Allerdings gibt es Beispiele, wo man das nicht so machen kann. Zum Beispiel wenn a) das Gerät gar kein CD-Laufwerk (wie das MacBool Air) hat oder b) man bereits Windows auf seiner BootCamp Partition installiert hat und eine dritte Festplatte bräuchte oder man c) schlicht nichts an seinem Rechner verändern möchte. Für letzten Fall eignet sich ein bootfähiger USB-Stick (mit nem Linux drauf) sehr gut.

Im folgenden Artikel beschreiben wir in 10 Schritten, wie man einen bootfähigen USB-Stick unter OS X erstellt, am Beispiel von Ubuntu.

**Achtung:** Ihr müsst die aktuelle ISO Datei von Ubuntu [downloaden](http://www.ubuntu.com/download/desktop).

**Tip:** Drag and drop a file from Finder to Terminal to 'paste' the full path without risking typing errors.

1. 

[Download Ubuntu Desktop](http://www.ubuntu.com/download/desktop)

2. 

Open the Terminal (in /Applications/Utilities/ or query Terminal in Spotlight).

3. 

Convert the .iso file to .img using the convert option of hdiutil (e.g.,hdiutil convert -format UDRW -o ~/path/to/target.img ~/path/to/ubuntu.iso)

**Note:** OS X tends to put the .dmg ending on the output file automatically.

4. 

Run diskutil list to get the current list of devices.

5. 

Insert your flash media.

6. 

Run diskutil list again and determine the device node assigned to your flash media (e.g. /dev/disk2).

7. 

Run diskutil unmountDisk /dev/diskN (replace N with the disk number from the last command; in the previous example, N would be 2).

8. 

Execute sudo dd if=/path/to/downloaded.img of=/dev/rdiskN bs=1m (replace /path/to/downloaded.img with the path where the image file is located; for example, ./ubuntu.imgor ./ubuntu.dmg).

- Using /dev/rdisk instead of /dev/disk may be faster
- If you see the error dd: Invalid number '1m', you are using GNU dd. Use the same command but replace bs=1m with bs=1M
- If you see the error dd: /dev/diskN: Resource busy, make sure the disk is not in use. Start the 'Disk Utility.app' and unmount (don't eject) the drive

9. 

Run diskutil eject /dev/diskN and remove your flash media when the command completes.

10. 

Restart your Mac and press alt/option key while the Mac is restarting to choose the USB stick.
