---
title: Weitere Virtualisierung auf dem M1
slug: weitere-virtualisierung-auf-dem-m1
date_published: 2020-12-22T14:02:02.000Z
date_updated: 2021-04-14T13:29:00.000Z
tags: apple silicon, mac mini, apple m1, windows 10, windows 10 for arm
---

Ich habe euch ja neulich mal [aufgeschrieben](__GHOST_URL__/starting-windows-10-on-macmini-m1/), wie man mithilfe von QEMU und Windows 10 for Arm eben jenes Windows 10 auf einem Mac mit Apple Silicon M1 Prozessor laufen lassen kann. Und das funktioniert. Aber erwartungsgemäß furchtbar schlecht, da all diese Dinge noch pre-Alpha sind. In frühestem Entwicklungsstadium.
![thahipster.de auf Windows 10 for Arm on MacMini M1 AppleSilicon QEMU](__GHOST_URL__/content/images/2020/12/Bildschirmfoto-2020-12-18-um-08.41.26-1.png)thahipster.de auf Windows 10 for Arm on MacMini M1 AppleSilicon QEMU
Und jetzt kommen auch die ganzen kommerziellen Anbieter langsam in die Puschen, so wie auch Parallels. Parallels bietet zum Download eine Technical Preview an, mit welcher man andere ARM-Betriebssysteme virtualisieren kann, wie z.B. Windows 10 for Arm oder aber auch ein Linux for Arm. X86 Systeme funktionieren (noch) nicht. Ich probiere das gerade mit der Developer Review von Windows 10 for Arm und installiere.

Um eine virtuelle Maschine auf einem neuen Mac-Computer mit dem Apple-M1-Chip auszuführen, hat das Parallels Engineering-Team eine neue Virtualisierungs-Engine entwickelt, die die hardwaregestützte Virtualisierung des Apple-M1-Chips nutzt und ARM-basierte Betriebssysteme in einer virtuellen Maschine ausführen kann. Aufgrund des signifikanten Unterschieds zwischen Intel x86- und ARM-Architekturen ist es nicht möglich, entweder bestehende virtuelle Maschinen auszuführen, die auf Mac-Computern mit Intel-Prozessoren erstellt wurden, oder eine neue virtuelle Maschine mit Intel x86-basiertem Betriebssystem zu erstellen.
![Parallels 16 for Mac M1 mit Windows 10 for Arm](__GHOST_URL__/content/images/2020/12/Bildschirmfoto-2020-12-22-um-14.29.58.png)Parallels 16 for Mac M1 mit Windows 10 for Arm
Es muss sich um ARM x64 Software handeln, ARM x32 funktioniert nicht. Die Installation läuft problemlos durch. Nachdem das Betriebssystem erfolgreich installiert worden ist, benötigt man eine Serial Nummer für Parallels. Da es sich um eine Technical Preview handelt, gibt Parallels diese kostenlos heraus.

Die Freischaltnummer erhaltet ihr im Backend eures Accounts, tragt diese in die Software ein.

Im Anschluss kann man die übliche Windows Konfiguration durchführen. Ist dies beendet, sollte man ein fröhliches Windows 10 sein eigen nennen können.
![thahipster.de in Parallels M1 unter Windows 10 for Arm auf Mac M1](__GHOST_URL__/content/images/2020/12/Bildschirmfoto-2020-12-22-um-14.52.58.png)thahipster.de in Parallels M1 unter Windows 10 for Arm auf Mac M1
### Downloads:

- [Download](https://b2b.parallels.com/apple-silicon)**Parallels 16 for Mac** Technical Preview (Account erforderlich)
- Download **Windows 10 for Arm** (**Windows Insider Preview ARM64*)* unter [https://www.microsoft.com/en-us/software-download/windowsinsiderpreviewARM64](https://www.microsoft.com/en-us/software-download/windowsinsiderpreviewARM64), das ist eine virtuelle Festplatte, VHDX Image. (Account erforderlich)
- [Diskussion zu Linux auf dem Mac M1](https://www.phoronix.com/scan.php?page=news_item&amp;px=Ubuntu-Apple-M1-Parallels-Pre) Chip
- An dieser Stelle möchte ich auf das Projekt "Does It ARM" hinweisen [Link](https://doesitarm.com/). 

Nach einem ersten Test, also der Installation von Windows 10, dem weiteren Setup, der Konfiguration und der Installation weiterer Programme läuft das ganze ohne weitere Probleme schon recht stabil. Ich werde bei Gelegenheit weitere Software unter Windows testen.
