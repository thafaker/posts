---
title: Bookmarklets -- Kleine Helferlein
slug: bookmarklets-kleine-helferlein
date_published: 2008-04-24T17:52:17.000Z
date_updated: 2018-08-22T09:39:03.000Z
---

Bookmarklets sind etwas sehr sehr cooles. Die gibt es eigentlich auch schon viel länger, aber ich bin erst jetzt darauf gestoßen, warum weiß ich auch nicht genau. Im großen und ganzen sind *Bookmarklets* "Lesezeichen", die eine gewisse Funktion ausführen. Das heißt sie speichern keine Adresse für eine Website, sondern vielmehr speichern Sie im Adressfeld für die URL tollen Javascript Code. Und dieser Code führt eine spezielle Funktion aus. Man legt sie sich am Besten oben in die Lesezeichenleiste für schnellen Zugriff.

Ich versuche jetzt einfach mal, an einem Beispiel erklärend darzustellen. Das als Beispiel genommene Bookmarklet ist dafür da, ein Youtube-Video als MP4 Datei zu speichern, also in höherer Qualität als die eigentlichen Videos sind. Im Normalfall hat man nämlich keinen Zugriff auf die Mp4 Dateien. Und so ist das ganze echt bequem.

Also, man nimmt einfach diesen folgenden Link und zieht in in seine Leiste (wie auf dem Bild):

[Get YouTube video (Link nicht mehr verfügbar)](javascript:if%20(document.getElementById('download-youtube-video')==null%20&amp;&amp;%20!!(document.location.href.match(/http:\/\/[a-zA-Z\.]*youtube\.com\/watch/)))%20{var%20yt_mp4_path='http://www.youtube.com/get_video?fmt=18&amp;video_id='+swfArgs['video_id']+'&amp;t='+swfArgs['t'];%20var%20div_embed=document.getElementById('watch-embed-div');div_embed.innerHTML=div_embed.innerHTML+'%3Cbr%20/%3E%20%3Cspan%20id=\'download-youtube-video\'%3E%3Ca%20href=\''+yt_mp4_path+'\'%3EDownload%20as%20MP4%3C/a%3E%20'+%20%20((navigator.userAgent.indexOf('Safari')!=-1)?'(control-click%20and%20select%20%3Ci%3EDownload%20linked%20file%20as%3C/i%3E)':('(right-click%20and%20select%20%3Ci%3ESave%20'+%20(navigator.appName=='Microsoft%20Internet%20Explorer'?'target':'link')%20+'%20as)%3C/i%3E'))+'%3C/span%3E';}void(0);)

[![bookmarklet_draggen](//picdump.thafaker.de/2008/04/bookmarklet_draggen-300x273.jpg)](http://picdump.thafaker.de/2008/04/bookmarklet_draggen.jpg)

Schwupps, ist der Link oben in der Leiste.

[![bookmarklet_droppen](//picdump.thafaker.de/2008/04/bookmarklet_droppen-300x261.jpg)](http://picdump.thafaker.de/2008/04/bookmarklet_droppen.jpg)

Jetzt besuchen wir natürlich sofort Youtube, denn für diese Seite ist jenes Bookmarklet ja geschrieben.

[![bookmarklet1](//picdump.thafaker.de/2008/04/bookmarklet1-300x257.jpg)](http://picdump.thafaker.de/2008/04/bookmarklet1.jpg)

In meinem Beispiel nutze ich das Video des guten alten Headhunter von Front 242. Wir klicken also auf das Bookmarklet.

[![bookmarklet2](//picdump.thafaker.de/2008/04/bookmarklet2-300x230.jpg)](http://picdump.thafaker.de/2008/04/bookmarklet2.jpg)

Und sofort sollte im unteren Bereich...

[![bookmarklet3_not](//picdump.thafaker.de/2008/04/bookmarklet3_not-300x182.jpg)](http://picdump.thafaker.de/2008/04/bookmarklet3_not.jpg)

... ein Link angezeigt werden, welcher den Download der angesehenen Datei (Headhunter) als MP4 Datei erlaubt. So wie im folgenden Bild:

[![bookmarklet4_yes](//picdump.thafaker.de/2008/04/bookmarklet4_yes-300x203.jpg)](http://picdump.thafaker.de/2008/04/bookmarklet4_yes.jpg)

Das wars schon. Großartig, oder? Ich als alter Musikfreund finde das gar sensationell. Und wie man sich schon denken kann, ist das natürlich nur ein einziges kleines Beispiel für ein Bookmarklet. Die Awendungsbeispiele und Gebiete reichen vom verkleinern von Fotos auf Websites bis hin zu einem Bookmarklet, was einfach die Adresse der aktuellen Website direkt ins Email Programm kopiert und das versenden erlaubt oder die [Inverssuche (Link nicht mehr verfügbar)](javascript:Qr=document.getSelection();if(!Qr){void(Qr=prompt('Telefonnummer',''))};if(Qr)location.href='http://dasoertliche.de/Controller?form_name=search_inv&amp;ph='+escape(Qr)) (Nummer nach Namen) von Telefonnummern auf dasOertliche.de

Ach ja, das schönste ist natürlich, Bookmarklets funktionieren mit jedem Browser. Egal ob IE7, Safari oder Firefox, denn auch Opera kann es.

Wer es gern etwas wissenschaftlicher mag, dem sei der Artikel in der [Wikipedia (archiviert)](http://web.archive.org/web/20091001034019/http://de.wikipedia.org:80/wiki/Bookmarklets) ans Herz gelegt. Dort findet sich auch ein Beispiel, wie man die Wikipedia nach -zuvor auf einer Website- markierten Wörtern durchsuchen kann.

Eine weitere großartige Ressource für Bookmarklets stellt folgende [Website](https://www.squarefree.com/bookmarklets/) dar.

**Links**:

- [Download Youtube Videos as MP4 Video](http://googlesystem.blogspot.com/2008/04/download-youtube-videos-as-mp4-files.html)
- [Wikipedia über Bookmarklets (archiviert)](http://web.archive.org/web/20091001034019/http://de.wikipedia.org:80/wiki/Bookmarklets)
- [SelfHTML über Bookmarklets](http://aktuell.de.selfhtml.org/artikel/javascript/bookmarklets/)
