---
title: Ultimate Guide to Mac Pro (BigMac)
slug: ein-kleiner-abriss-zu-meinem-mac-pro-bigmac-2
date_published: 2019-04-06T20:19:49.000Z
date_updated: 2025-09-24T07:16:56.000Z
tags: bigmac, apple, macpro, anleitung, howto, how to
excerpt: In dieser Zusammenfassung beschreiben wir, wie man den Mac Pro aufrüstet. Vom Speicher über die Grafikkarte bis hin zur CPU. Worauf ihr achten solltet erfahrt ihr in diesem Artikel. Viel Spaß beim Lesen und Upgraden.
---

**Da** ich ja ein glühender Verfechter des *Käsereibe* genannten **MacPros** bin und selber so einen Rechner ([Link](__GHOST_URL__/tag/bigmac/)) besitze, möchte ich an dieser Stelle kurz zusammen führen, was es bedeutet und wie man vorgehen kann, wenn man (möglichst günstig) so ein Gerät anzuschaffen gedenkt. Und wie man am besten aufrüstet. Denn in dem Mac steckt Potential, was gehoben werden sollte. Dazu werde ich wie immer etwas weiter ausführen aber trotzdem versuchen, mich kurz zu halten. Auf meine bereits geschriebenen Artikel zum Thema werde ich verlinken.

![Mein MacPro mit Cinema Display 30&quot;](__GHOST_URL__/content/images/2019/04/cinema2.jpg)
Mein MacPro mit Cinema Display 30"
### Ultimate Guide to Mac Pro 4,1 and 5,1

Es gibt sicher schon diverse Anleitungen, aber diese hier ist meine! Grundsätzlich kann man meinen Artikel in vier große Gliederungspunkte unterteilen, die sich wie folgt darstellen:

1. Mac Pro kaufen
2. Grafikkarte aufrüsten
3. CPU aufrüsten
4. Speicher aufrüsten
5. NVMe SSD
6. macOS 10.15 auf MacPro5,1 4,1
7. Welchen Bildschirm für den cMP?

Dass der MacPro eine wahnsinnig sexy Maschine mit tollen Eigenschaften und einem professionellen Design ist, darüber müssen wir gar nicht sprechen. Auch über das ausgeklügelte Kühlkonzept, das quasi kabellose Design auch nicht. Und über die leichte Erweiterbarkeit erst recht nicht. Fangen wir also an.

#### Mac Pro anschaffen

Zunächst muss man sich einen Mac Pro kaufen. Die Mac Pros sehen bis auf kleine Details alle relativ gleich aus und werden seit 2006, mit dem Wechsel von PowerPC hin zur Intel x86-Architektur, so gebaut.[[1]](#fn1) Aber nur die aktuellen Macs können hardwareseitig auch wirklich gut aufgerüstet werden, die anderen sind eigentlich schon zu alt. Der MacPro5,1 von 2012 ist der aktuelleste und letzte *Käsereibemac*. Wenn ihr so einen kriegen könnt - nehmt den. Da dieser allerdings recht selten und derzeit noch unverhältnismäßig teuer ist, gibt es Alternativen.

Es hat sich heraus gestellt, dass ab dem MacPro4,1 von 2009 die Hardware praktisch nicht mehr geändert worden ist und das Upgrade auf MacPro5,1 2010 und 2012 rein aus firmware-technischer Sicht basiert. Und Firmwares sind Software. Und Software kann man aktualisieren. Heißt also, man kann sich problemlos einen MacPro4,1 von 2009 für kleineres Geld kaufen und diesen MacPro auf einen 5,1 von 2012 updaten. Das habe ich auch getan. Allerdings habe ich großen Wert darauf gelegt, dass ich einen Dual-Prozessor MacPro kaufe. Und zwar den kleinsten, ich habe mir einen MacPro4,1 mit 2 x 2,26 GHz XEON CPUs gekauft. Der MacPro mit Single und Dual-CPU sind identisch, aber die Prozessorkarte ist natürlich unterschiedlich (auf der Speicher und CPU verbaut sind) und diese kostet gut und gern alleine schon 400€ für Dual-CPUs. Und nur mit Dual-CPU ist der MacPro ein echtes Biest. Wenn man also zunächst günstig einen SingleCore kauft und später aufrüsten will, ist das keine gute Idee. Lieber etwas warten und gleich einen Dual Prozessor MacPro kaufen.

- MacPro4,1 2009 mit Dual CPU kaufen. [Hier](https://www.ebay.de/itm/Apple-Mac-Pro-2009-2-x-2-26-GHz-Quad-Core-Intel-Xeon-32-GB-RAM/143195661900?hash=item215720664c:g:U3AAAOSwkiZcoQ-x) (**nicht mehr verfügbar**) habe ich mal exemplarisch ein Beispiel verlinkt.

So, wenn ihr jetzt so einen zu Hause habt, dann könnt ihr weiter machen - es lohnt sich :-)

#### Grafikkarte aufrüsten

Es ist Geschmackssache ob man die Grafikkarte aufrüstet. Aber da mein MacPro per Default nur mit einer ab Werk verbauten **nVidia Geforce 120** mit *512MB* bestückt ist, tat ich gut daran, diese abzugraden.

Nun ist es mit den Grafikkarten im MacPro jedoch folgendermaßen. Man kann praktisch jede PCI-Express Grafikkarte x16 verbauen und die funktionieren auch innerhalb von macOS, jedoch haben diese ein Windows-BIOS und kein Mac-BIOS und zeigen deshalb keinen Boot-Screen. Den Apfel wenn man einschaltet. Der Bildschirm bleibt schwarz bis zum Login-Fenster von macOS, dann schaltet er ein. Allerdings hat man so auch keine Recovery-Funktion. Man kann beim Boot keine andere Boot-Platte auswählen und man kann sein System nicht recoern, kommt nicht in den Installer und kann somit auch kein Windows installieren. Ich finde das problematisch. Aber es gibt eine Lösung. Irgendwann gab es mal eine *nVidia Geforce GTX 680* original für den Mac. Von dieser Grafikkarte extrahierte jemand das Bios. Das geht mit einem nVidia-Tool ganz simpel unter Windows. Dann zeigte ich, das praktisch jede Geforce 680 GTX die dem Referenzdesign entspricht, mit diesem Mac-BIOS kiompatibel ist. Und was bedeutet das? Nun, man kauft sich für 30 Euro auf eBay eine gebrauchte Geforce 680 GTX für Windows, flasht das Mac-BIOS drauf und hat fortan eine originale 100% Mac-Grafikkarte. Großartig, oder? Und ich muss sagen, diese 680 GTX reicht sogar noch zum zocken. Wie das geht habe ich in folgendem Artikel Schritt für Schritt beschrieben.

- [How to Flash Geforce 680 GTX for Mac](__GHOST_URL__/wie-man-eine-pc-grafikkarte-fur-den-mac-um-flasht-efi-rom/).

Einen großen Vorteil habe ich euch noch gar nicht genannt. Apple unterstützt mit macOS Mojave nur noch Metal-fähige Grafikkarten, das heißt, ein MacPro ist normalerweise außen vor. Nun ratet mal welche Grafikkarte von Apple original für Metal und macOS 10.14 unterstpützt wird? Richtig, die Geforce 680 GTX :-)

So, nun haben wir einen MacPro4,1 mit einer echten Mac-Geforce Grafikkarte der nun auch nativ und ohne Patches das aktuelleste macOS 10.14 Mojave untersützt. Das können sonst nur die neu gekauften Macs. Zeit also, sich um die Prozessoren zu kümmern.

#### CPU aufrüsten

Ich habe ja schon ans Herz gelegt, warum ihr unbedingt einen Dual-CPU MacPro kaufen sollt. Nur den kann man mit wirklich Dampf unter der Bude aufrüsten. Es gibt eine simple Anleitung aus seinem MacPro4,1 per Firmware-Upgrade einen MacPro5,1 zu machen. dann unterstützt er plötzlich 1333MHz-DDR3-Speicher und Westmere XEONs mit 6 Kernen. Wenn man zwei CPUs hat, dann spielt man also mit 12 echten Kernen und 24-HT-Kernen rum. Gepaart mit 32 GB-Ram ist das ziemlich enorm :-) Allerdings gibt es etwas zu beachten. Der MacPro4,1 kann nur mit *delidded* CPUs umgehen. Diese Prozessoren haben keinen Heatspreader. Das hat Apple so entschieden, weil die Wärmeabfuhr dann deutlich besser ist, als mit einem Deckel. Allerdings kann man neue CPUs nur mit Heatspreader kaufen. Man muss diese CPUs also köpfen. Oder man kauf bereits vorgeköpfte CPUs, die muss man dann nur noch einsetzen. Allerdings sind diese natürlich teurer. Ich habe mir zwei XEONS 5680 CPUs für zusammen 90€ gekauft und diese selber geöpft. Wie das alles geht mit dem Upgrade und dem Köpfen, das beschreibe ich euch in folgendem Artikel:

- [How To Delid and Upgrade your MacPro 4,1 CPU](__GHOST_URL__/how-to-delid-and-upgrade-your-macpro-4-1-cpus/)

#### Speicher aufrüsten

Hier gibt es nicht viel zu berichten. Der MacPro4,1 läuft grundsätzlich mit 1066MHz Speicher, wenn man aber das Upgarde auf 5,1 durchführt und auch entsprechende XEON Westmere CPUs verbaut, dann kann er 1333MHz Speicher vwenden. Ich habe mir für knapp 80€ 4 x 8 GB Ram Riegel gekauft und diese verbaut. ECC-Ram. Funktioniert absolut problemlos.

- [Als ich neulich den Arbeitsspeicher aufrüstete](__GHOST_URL__/als-ich-neulich-den-arbeitsspeicher-erweiterte/)

Als kleines Update dient der folgende kurze Artikel, in welchem ich auf Triple-Channel und seine Vorzüge eingehe. Bei mir war der Geschwindigkeitszuwachs von über 1000 Geekbench4-Punkten nicht nur mess- sondern auch fühlbar.

- [MacPro5,1 Triple Channel Speicher RAM](__GHOST_URL__/macpro5-1-triple-channel/)

#### NVME SSD?

Eigentlich kann der MacPro nicht von NVME-SSDs booten, bisher, sondern nur von den älteren AHCI-Karten. Diese werden mittlerweile nicht mehr hergestellt und so gehen die Preise dafür in die Höhe. Mit **macOS 10.14** spendierte Apple seinem (also auch meinem) uralten MacPro ein Bootrom-Update auf 140.0.0.0.0 und führte so den nativen Support von NVME ein [[2]](#fn2). Ihr könnt euch also eine PCIE 4x Adapterkarte für den MacPro kaufen, dort eine NVME-SSD einbauen und darauf euer Betriebssystem installieren. Das bringt einen Datendurchsatz von 1500 MB / Sec. Unglaublich. Diesen Schritt bin ich allerdings noch nicht gegangen, sondern boote meinen MacPro noch herkömmlich von einer SSD die ich am SATA-Port angeschlossen habe. Ich habe eine 512er für macOS und eine 128er für Windows 10 in Dualboot-Konfiguration. Ach ja, ein kleines und leichtes Linux habe ich auch noch drauf, das kann man immer mal gut gebrauchen. Ansonsten betreibe ich meinen Mac Pro mit diversen drehenden HDDs, man braucht ja schließlich immer mal Platz.

![hw](__GHOST_URL__/content/images/2019/04/hw.png)
MacPro4,1 mit NVME-fähigem Bootrom
[**UPDATE**] Mittlerweile habe ich meinem MacPro eine NVMe M2 SSD spendiert und darauf mein OS installiert, es ist meine Bootplatte. Wie ich das gemacht habe, erfahrt ihr [in folgendem Artikel](__GHOST_URL__/nvme-ssd-in-macpro4-1/).

#### macOS 10.15 Catalina auf MacPro4,1 installieren

Da Apple die Käsereibe-Macs aka classicMacPro (cMP) aus dem Verkehr gezogen und ihnen die Lizenz für die Fähigkeit zur Nutzung von nacOS 10.15 Catalina verboten hat, muss eine andere Lösung sein. Entweder man nutzt die Möglichkeit vom legendären DosDude1, der einen Patcher für den Installer entwickelt hat, mit dem man einfach trotzdem installieren kann, was allerdings mit einigen Einschränkungen (vor allem keine Updates möglich, man muss immer wieder komplett neu installieren) einher geht. Oder man geht den Weg über OpenCore. [OpenCore am MacPro5,1](__GHOST_URL__/macos-10-15-catalina-auf-macpro5-1/) habe ich hier beschrieben, viel Erfolg.

#### Ein Bildschirm

Ach so… noch was: einen Bildschirm brauchte ich ja auch noch. Nach einigem Hin und Her bin ich tatsächlich an dieses legendäre 30" Apple Cinema Display gekommen, welches jetzt bei mir den Dienst verrichtet. Es ist der Hammer. Der Mac Pro ist der Hammer.

- [Mein 30 Zoll Apple Cinema Display](__GHOST_URL__/das-legendare-30-zoll-cinema-display-von-apple/)

![about-3](__GHOST_URL__/content/images/2019/04/about-3.png)
Mein MacPro Ultimate
#### Mac Pro 2019 aka 7,1

![](__GHOST_URL__/content/images/2019/06/mac-pro-display-100798260-large.jpg)

Apple hat auf der [WWDC 2019](__GHOST_URL__/wwdc-2019/) endlich einen neuen, modularen MacPro vorgestellt. Die Leistung ist überragend, der Preis ist es auch, kurzum: er wird kontrovers diskutiert, allerdings handelt es sich hier um ein Profi-Gerät für Geschäftskunden die damit Content erstellen, der die Preise rechtfertigt.[[3]](#fn3) Wir haben über diesen neuen [MacPro7,1 2019 ganz ausführlich an dieser Stelle](__GHOST_URL__/macpro7-1-die-neue-kasereibe/) berichtet.

*Vielen Dank für eure Geduld, es bleibt spannend*.

---

1. 
Und selbst der [Powermac G5](https://d3nevzfk7ii3be.cloudfront.net/igi/APBogP6JMWqGqlmB) sah schon fast so aus, wie er MacPro mit Intel-CPU. Es gibt ein paar kleine Details vom Aufbau im Inneren sowie nur einen CD-Rom-Schacht und die forderen Anschlüsse, aber an sich ist er nahezuh identisch. [↩︎](#fnref1)

2. 
Apple aktualsiert im Jahr 2019 das Bootrom eines Computers von 2009. Das ist unglaublich. Und natürlich ziemlich großartig für uns Nutzer. [↩︎](#fnref2)

3. 
So ein Gerät ist nicht für Endkunden, es ist für Firmen, sie produzieren damit Inhalte in 4K und in 8K, hier werden unglaubliche Summen umgesetzt, so ein Rechner wird über Jahre abgeschrieben und so ist die finanzielle Belastung am Ende nicht höher als bei anderem Profi-Equipment. Die paar Endkunden die sich so ein Teil leisten wollen, werden aber auch kein Problem mit dem Preis haben. Aber ja, der Preis ist grundsätzlich erst mal hoch! [↩︎](#fnref3)
