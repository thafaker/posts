---
title: Shitstorm über Android
slug: datenleck-im-android
date_published: 2011-05-18T09:05:28.000Z
date_updated: 2018-08-22T09:38:38.000Z
---

Tja, nun hat es **Android** also doch erwischt. Nach all den [Datenspack-Debatten](__GHOST_URL__/apple-und-die-gps-daten/) über Apples iOS Politik und den zugegeben recht gruseligen Aufzeichnungen der Bewegungsprofile, hat es auch die derzeitige Bastion freier Software auf Telefonen erwischt: Android, Googles OS für Mobiltelefone, hat ein Datenleck! Aber dies hier soll kein Rant werden und auch keine Genugtuung für das Apple-Bashing in der letzten Zeit: nein, es soll nur darauf hinweisen dass bei all der Komplexität in heutigen Telefonen -ähnlich wie bei früheren Windows-Versionen die aufgrund der Altlasten und Kompatibilität- gewisse Fehler und Datenprobleme immer wieder auftauchen werden.

Wobei sich hier die Frage stellt, ob das wirklich so ein großer Fehler ist, wie [SpOn](http://www.spiegel.de/netzwelt/gadgets/0,1518,763288,00.html) da reißerisch berichtet. Wir sagen: NEIN!

[...] Googles Android-Anwendungen übertragen Daten unverschlüsselt, sagen Wissenschaftler der Universität Ulm. Angreifer können dadurch an Anmeldedaten gelangen, um vertrauliche Daten einzusehen, zu ändern oder zu löschen. Google reagiert nur halbherzig darauf. [Golem]

Hier müssen wir aber mal eben einhaken: Wer eine Verbindung zu einem offenen WLAN herstellt und dann persönliche  Daten unverschlüsselt überträgt, geht ein großes Sicherheitsrisiko ein. Das weiß jeder und das macht sogar Windows automatisch, also sich zu bekannten (und unverschlüsselte sind ja defacto bekannte Wlans) WLans zu verbinden.

[...] Der Angreifer kann fortan den gesamten unverschlüsselten Datenverkehr  mitlesen. Dazu ist lediglich eine Software wie [Wireshark](http://www.wireshark.org/) ((Netzwerk-Protokoll-Analysierer und Traffic-Auswerter)) notwendig. [...]

Jetzt kommen wir aber zum eigentlichen Problem, dass aber auch nicht nur bei Android so sein dürfte: [...] Der Kalender und das Adressbuch von Android überträgt Authentifizierung-Token immer unverschlüsselt. Das gilt auch für die Android-Anwendung Picasa. Wer mit seinem Android-Smartphone ein unverschlüsseltes WLAN-Netzwerk verwendet, läuft Gefahr, dass seine Anmeldedaten ausspioniert werden, ähnlich wie bei einem Session-Cookie. Ein Angreifer kann dann vollen Zugriff auf alle bei Google hinterlegten Daten erhalten und diese nach Belieben einsehen, ändern oder löschen.

Die eigentliche Schwachstelle in Android, die von den Ulmer Forschern  entdeckt wurde, befindet sich in den Google-Diensten, die auf den  Smartphones und Tablets genutzt werden. *Mindestens alle zwei Wochen* muss  sich ein Anwender mit seinem Nutzernamen und seinem Passwort bei den  Google-Servern authentifizieren. Über eine verschlüsselte  HTTPS-Verbindung werden die Anmeldedaten übertragen - von den  Google-Servern erhält man daraufhin ein so genanntes authToken, das  maximal zwei Wochen gültig ist. Damit kann ohne erneute  Authentifizierung mit Google-Diensten wie dem Kalender, der  Kontaktverwaltung sowie dem Fotodienst Picasa kommuniziert werden.

Die eigentliche Sicherheitslücke befindet sich also in der Kommunikation mit  Hilfe dieses oben bereits genannten *authTokens*. Der Datenaustausch mit den Google-Diensten findet wie beschrieben eben  unverschlüsselt statt, so dass ein Angreifer das authToken mitlesen  kann, um damit Zugriff auf die Google-Dienste zu erhalten, so dass die  dort gespeicherten Daten ausgespäht werden können. Die Ulmer Forscher  sind der Ansicht, dass die Arbeit der Kriminellen erleichtert wird,  indem automatisch eine Verbindung zu bekannten WLANs hergestellt wird,  die sich leicht fälschen lassen. [[Winfuture](http://winfuture.mobi/news/63266)]

**[Update]**

Gegenüber der Nachrichtenagentur 'dpa' hat sich ein Google-Sprecher zu  den Berichten über die Sicherheitslücke geäußert: "Wir sind uns des  Problems bewusst, haben es in den jüngsten Android-Versionen für  Kalender und Kontakte bereits beheben können und sind dabei, es auch für  Picasa zu lösen."  [[Winfuture](http://winfuture.mobi/news/63266)]

**Weitere Informationen:**[Beschreibung der Schwachstelle der Ulmer Forscher (archiviert)](http://web.archive.org/web/20110520001656/http://www.uni-ulm.de:80/en/in/mi/staff/koenings/catching-authtokens.html)![](//vg06.met.vgwort.de/na/de2ff7fac6de4fd6a3aac8d70b99ff2d)

`**Artikelfoto**: (C) ladebildschirm.de`
