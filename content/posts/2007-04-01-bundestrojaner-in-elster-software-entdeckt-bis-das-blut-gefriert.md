---
title: Bundestrojaner in ELSTER-Software entdeckt // Bis das Blut gefriert
slug: bundestrojaner-in-elster-software-entdeckt-bis-das-blut-gefriert
date_published: 2007-04-01T14:00:18.000Z
date_updated: 2018-08-22T09:38:02.000Z
---

Wie der [Chaos Computer Club](http://www.ccc.de/updates/2007/bundestrojaner-elster) berichtet: 
> Seit dem 19. März 2007 wird die aktuelle ELSTER-Software für das Jahr 2006/2007 in der Version [8.1.0.0](https://www.elster.de/) für den Steuerbürger bereitgestellt. Schon von Anfang an hegten Experten Zweifel an der Integrität der 18 MB großen .exe-Datei. Nach einer mehrtägigen intensiven Analyse fand der Chaos Computer Club (CCC) nun deutliche Hinweise, dass über die fragwürdige Software der sog. [Bundestrojaner](http://de.wikipedia.org/wiki/Bundestrojaner) verbreitet wird.

Der Bundestrojaner, kürzlich als neues Werkzeug des Überwachungsstaates in die Schlagzeilen geraten, soll das Ausspähen der gesamten steuerpflichtigen Bevölkerung ermöglichen. Jeder Bürger mit eigenem Einkommen wird in Zukunft verpflichtet, die Steuererklärung mittels ELSTER-Software abzugeben. Dass es dem CCC nach wenigen Tagen gelang, den Trojaner ausfindig zu machen, spricht nicht eben für die Qualität der Spitzelsoftware.

Die Analyse zeigte verschiedene verdächtige Module, wie z. B. wte0104-brsjm.digit, das u. a. vorhandene Mikrofone und Kameras in modernen Computern einschalten kann. Weitere Routinen dienen der Durchsuchung der auf dem Rechner gespeicherten Dateien. Eine Funktion sendet Daten vom Benutzerrechner ferngesteuert an den BKA-Rechner mit der IP-Adresse [217.7.176.25](http://www.ripe.net/whois?searchtext=217.7.176.25).

Der Trojaner tauscht offenbar auch einige Systemdateien aus, um sich unabhängig vom ELSTER-Programm auf dem System einzunisten. Die Schadsoftware erzwingt danach einen Neustart des Rechners. Auf dem Bildschirm des betroffenen Computers erscheint dazu die Fehlermeldung: "Systemfehler 70797976 - Neustart erforderlich."

Pikanterweise wird ein Port auf dem infizierten Rechner geöffnet, der es erlaubt, neue Suchbegriffe nachzuladen. Das ist insofern problematisch, da die Suchfunktion eine Schwachstelle enthält, die es einem Angreifer erlaubt, nicht nur Suchbegriffe, sondern beliebige Daten und ausführbaren Code auf dem Rechner zu platzieren. "Damit ist der unbemerkten Manipulation aller Daten Tür und Tor geöffnet," sagte CCC-Spezialexperte Jens-Thorben Janckiewozki.

Eine erste Ausnutzung dieser Nachladeschwachstelle wurde auch schon in der freien Wildbahn beobachtet. Ein schwer zu analysierender, auf Schwachstellen des Bundestrojaners aufsetzender Wurm dient wahrscheinlich dem Abfangen von PIN- und TAN-Eingaben von Onlinebanking-Benutzern der Postbank. Auch erste Zusammenschlüsse von gekaperten Rechnern zu sogenannten Botnetzen wurden im Verlaufe des Samstags beobachtet. Der Chef des BSI hatte unlängst Botnetze als größte Gefahr im Internet ausgemacht.

Bisher war weder das BKA noch das Bundesinnenministerium für eine Stellungnahme zu erreichen. Unter der Hand gab ein Techniker des BKA jedoch zu, dass in den eigenen Reihen niemand den Trojaner programmiert hätte. Dafür mussten schon aus Kostengründen im Ausland Fachkräfte angeworben werden. Die großen Antivirenhersteller haben mittlerweile ebenfalls mit der Analyse begonnen und hoffen in den nächsten Tagen entsprechende Updates zu verbreiten.

[tags]Computervirus, Elster, Staat, Bundestrojaner, CCC, gläserner Brüger, BSI, Antivirus[/tags]
