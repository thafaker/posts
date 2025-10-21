---
title: Thunderbolt seit 2011 unsicher
slug: thunderbolt-seit-2011-unsicher
date_published: 2020-05-12T03:28:04.000Z
date_updated: 2020-05-12T11:08:39.000Z
tags: thunderbolt, sicherheit, fix.it, thunderspy, firewire
---

Es ist furchtbar, weil es doch meine Lieblingsschnittstelle seit FireWire betrifft, aber gleichzeitig auch gar nicht so abwegig. Gemeint ist der jetzt entdeckte Fehler im Thunderbolt Protokoll und der zugehörigen Infrastruktur, der alle Geräte und Produkte seit der Veröffentlichung vom 10 GB schnellen Thunderbolt 1 im Jahr 2011 betrifft.

Die Unsicherheit stellen Forscher der Uni Eindhoven mit der "Thunderspy" genannten Software eindrücklich unter Beweis. Die Attacke funktioniert ausschließlich mit physischem Zugriff auf ein Gerät mit Thunderbolt 3, erlaubt dann aber das Auslesen sämtlicher Daten und die Installation beliebiger Software, indem der Angreifer den Sperrbildschirm von Windows beziehungsweise Linux umgeht.

Allerdings liest sich der *Proof-Of-Concept* eher wie die Benutzung eines Phasen-Matrix-Rekalibrators aus Star Trek Enterprise: man benötigt nämlich zunächst physischen Zugriff auf das Gerät. Dann muss man (z.B. bei einem Notebook) den Boden abschrauben und sich per SOP8-Zange mit dem *Serial Peripheral Interface* (SPI) des Firmware-Speicherchips verbinden. So gaukelt man dem Gerät Freundlichkeit vor und gibt sich selbst als vertrauenswürdiges Gerät aus. Hat man das geschafft, kann man den Security Level im Controller auf 0 setzen, sodann akzeptiert der Controller jedes Thunderbolt Gerät als vertrauenswürdig. Danach kann der Angreifer sein eigenes Notebook über Thunderbolt verbinden, Code ausführen und so die Passwortsperre umgehen. Eine Speicherverschlüsselung schützt in einem solchen Fall nich.

Hintergrund ist wohl der generell zu lasche Sicherheitsmechanismus seitens Intel und Apple bei Thunderbolt. Eine Abhilfe gibt es bisher nicht. Wer mehr erfahren möchte, kann sich gern in unserem Link bei Heise einlesen.

([via](https://www.heise.de/security/meldung/Thunderspy-Notebooks-ueber-Thunderbolt-Anschluss-kapern-4718468.html))
