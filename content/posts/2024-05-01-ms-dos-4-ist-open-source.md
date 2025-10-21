---
title: MS-DOS 4 ist Open Source
slug: ms-dos-4-ist-open-source
date_published: 2024-05-01T13:37:25.000Z
date_updated: 2024-05-02T11:34:46.000Z
tags: Microsoft Multitasking MS-DOS, vintage computing, ms-dos, open source
---

**Microsoft** hat vor wenigen Tagen **MS-DOS 4.0** (genauer: 4.01) unter eine MIT-Lizenz -und als Open Source zur Verfügung gestellt. Dies dient vor allem historischen Belangen. So ist man in der Lage Quellcode anzuschauen und zu verstehen, wie sich Microsoft, MS-DOS und auch spätere Inkarnationen entwickelt haben und was Assembler in den 80er Jahren eigentlich bedeutet hat. Ein Stück Museum, *eine museal-computerhistorische Geschichte*. Und ich finde das großartig.
![](__GHOST_URL__/content/images/2024/05/Bildschirmfoto-2024-05-01-um-15.36.47.png)
Aber MS-DOS 4 ist nicht gleich 4, denn es gab zwei verschiedene Varianten. Ein MS-DOS, welches es jedoch nie zum öffentliche Release schaffte, nannte sich **Microsoft Multitasking MS-DOS** ([Link zum Manual](https://github.com/microsoft/MS-DOS/blob/main/v4.0-ozzie/Multitasking%20DOS%20BETA%20-%20Intro.pdf)) und stammt von MS-DOS 2 ab. Und dann gab es noch eine Weiterentwicklung von MS-DOS 3.X, die in MS-DOS 4.01 mündet, also jenes, welches wir als MS-DOS 4 kennen. Ein Singletask Operating System, so wie alle DOS bis 6.22.

Ursprünglich wollte ein englischer Forscher namens Connor '*Starfrost'* Hyde mit dem früheren Microsoft-CTO *Ray Ozzie*, der damals für Lotus arbeitete, über Software aus dessen Sammlung sprechen, [schreiben die Microsoft-Mitarbeiter Scott Hanselman und Jeff Wilcox](https://cloudblogs.microsoft.com/opensource/2024/04/25/open-sourcing-ms-dos-4-0/). Hyde hatte sich eigentlich für die Beziehung zwischen MS-DOS 4, dessen Multitasking-Version (MT) bis hin zu OS/2 interessiert, letztlich führten dessen Recherchen zu dieser Veröffentlichung.

Microsoft ging schon vor einigen Jahren den Weg des Open Source und veröffentlichte MS-DOS 1 und später 2 unter der MIT-Lizenz, jetzt folgen Multitasking (was besonders spannend aus historischer Sicht) und eben MS-DOS 4. 

Einige *Enthusiasten* (z.B. das legendäre **FreeDOS** Projekt) haben die neuen 4er Quellen bereits erfolgreich kompiliert, was etwas Schwierigkeiten bereitete. Prinzipiell genügt dazu originale Hardware aus der Zeit oder eine gut konfigurierte Virtuelle Maschine. 

MS-DOS 4 kompiliert unter FreeDOS

Unter MS-DOS kompilieren die Quellen tatsächlich problemlos, aber unter FreeDOS muss man ein bisschen was *aufräumen*. Die kurze Zusammenfassung warum es sich nicht auch direkt unter FreeDOS kompilieren lässt, lautet: GitHub benutzt** UTF-8 **als Enkodierung und MS-DOS benutzt **Code Page 437**. 

Wie oben schon angemerkt weist Microsoft wie schon bei den früheren DOS-Releases darauf hin, dass es den Quellcode lediglich aus *historischen Gründen* freigegeben hat und die Dateien statisch seien; Pull Requests werden natürlich ignoriert 😄 Wer damit experimentieren und programmieren wolle, möge den Code bitte forken. Die auf GitHub verfügbare Betaversion von Multitasking MS-DOS lasse sich aber **definitiv ausführen**, versichert Microsoft. Dafür sei in dem Unternehmen ein originaler IBM Personal Computer XT herangezogen worden sowie die Emulatoren PCem und [86Box](https://86box.net/).

Ich habe total Lust auf meinem Vintage Computer diese Multiuser-Version zu kompilieren und einfach mal auszuprobieren, damit rumzuspielen. Wenn ich Zeit habe, irgendwann, werde ich das bestimmt auf echtem Blech versuchen und eventuell ein kleines Video davon anfertigen.

## Ressourcen

- [MS-DOS Multitasking Manuals](https://github.com/microsoft/MS-DOS/tree/main/v4.0-ozzie)
- [Building MS-DOS 4.00 on FreeDOS](https://www.youtube.com/watch?v=X7r76V_gWQ8)
- [Microsoft MS-DOS Github Repo](https://github.com/microsoft/MS-DOS)
