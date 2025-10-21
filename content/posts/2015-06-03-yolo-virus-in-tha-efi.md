---
title: Yolo Virus in tha EFI
slug: yolo-virus-in-tha-efi
date_published: 2015-06-03T20:00:55.000Z
date_updated: 2018-08-22T09:39:25.000Z
tags: apple, virus, efi, bios
---

Sogenannte *BIOS-Viren* sind in der PC-Welt nichts ungewöhnliches, also "Viren", die sich in einem persistenten Bereich des BIOS einnisten und dort **Schadcode** ausführen. Da dies im BIOS passiert, also unabhängig vom eigentlichen Betriebssystem auf diesem Rechner (egal ob Windows oder Linux), ist das natürlich besonders kritisch. Man kann hier nämlich sein Betriebssystem so oft neu installieren wie man will, der Virus/Backdoor/Schadcode bleibt.

Rootkits werden so gern verankert. Aber wie dem auch sei: Sowas gibt es jetzt auch für den alle Mac's mit ihrer EFI-Firmware. Und zwar aufbauend über den uralten Thunderbolt/FireWire-Bug, der das Schreiben direkt in den Speicher erlaubt. Doch langsam und Schritt für Schritt… 

*Yolo*, mag man da denken. Und es ist auch Yolo, zumindest für die Viren-Entwickler. Aber nicht für uns. Denn der Bug **is really serious**. Also einfach gefährlich. Für den oben erwähnten zugrunde liegenden Fehler benötigte man physischen Zugriff auf das Gerät, musste also quasi davor sitzen. Was die Sache natürlich sehr entspannte. So für 99% aller Nutzer. Aber was ist mit *sicherheitsrlevanten* Personen deren Mac genau so kompromittiert wird? Genau! Kann man jederzeit und immer belegen, dass jenes eigene Notebook nie unbeobachtet angetastet werden konnte? Nein, kann man nicht. Andererseits sind solche Szenarien immer arg konstruiert, was sie aber trotzdem nicht unmöglich macht.

![](__GHOST_URL__/content/images/2015/06/bios-1.png)

Der jetzt gefundene Bug kann allerdings über jede aktuelle Sicherheitslücke, z.B. in Safari etc., genutzt werden, also durch den Besuch einer kompromittierten Website installiert werden, was ihn jetzt natürlich potentiell wieder für 99% aller Nutzer gefährlich macht. Eigentlich ist ein EFI-BIOS auf nur Lesbar gestellt, sodass man nicht hinein schreiben kann. Doch leider sind alle Macs offen und für sie gilt das *read-only* nicht. Man kann also fröhlich überschreiben, ohne größerem Brimborium, was den Bug quasi überhaupt erst so gefährlich macht.

> It means that you can overwrite the contents of your BIOS from userland and rootkit EFI without any other **trick other than a suspend-resume cycle**, a kernel extension, flashrom, and root access.

Das Loch ist also das beschreibbare EFI und der Schlaf/Suspend-Mode.

Apple hat dafür allerdings ein Update veröffentlicht, die Macs sind also wieder sicher. Zumindest fast. Denn leider hat Apple ausschließlich für Geräte ab mid-2014 ein Update bereit gestellt, ALLE GERÄTE DAVOR BLEIBEN OFFEN. Bäm!

Und wenn also solche gravierenden Bugs in allen älteren (älter meint hier ab 2014 und abwärts) Geräten stecken, so muss man sich fragen, ob Apple sowas nicht echt mit Absicht einbaut respektive drin lässt. Als **Backdoor-Man**. Um mal einen Song der Doors zu zitieren.

Es gibt dagegen also keinen wirksamen Schutz, außer, seinen Mac niemals in den Suspend/Sleep-Mode wechseln zu lassen. Was eigentlich unmöglich scheint.

*Well…*
