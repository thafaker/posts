---
title: Laaaangeweile // InURL Google-Hacks
slug: laaaangeweile-inurl-google-hacks
date_published: 2007-07-12T22:51:28.000Z
date_updated: 2018-08-22T09:39:08.000Z
---

Schon vor längerer Zeit, quasi Anfang letzen Jahres, ging ein neuer Google Hack im Netz um wie ein Lauffeuer. Hack passt eigentlich ganz gut da man ja die ursprüngliche Funktion für etwas ganz anderes Verwendet, nämlich um mit Google Links zu Webcams zu finden. Das eigentlich interessante ist, dass diese zum Teil gar nicht für die Öffentlichkeit bestimmt sind!
![caminurloutside.png](//picdump.thafaker.de/2007/07/caminurloutside.png)
Heutige auf dem Markt befindliche Webcam Modelle verfügen über einen eingebauten Mini-Webserver, der den Live-Stream oder ein Standbild über einen Standard Web-Browser betrachtbar macht. Leider verfügen die wenigsten Modelle über die Möglichkeit eine Authentifizierung zu aktivieren. Hat man nun die Kamera nicht in einem geschützten Netz installiert, sondern direkt an das Internet angebunden, so läuft man Gefahr, dass ein Suchroboter *irgendwie* Kenntnis von dieser URL erhält.

**Möglichkeiten**:

Google bietet 2 interessante Suchparameter an:

"inurl" = Teilstring, der in der URL vorkommen soll

"intitle" = Teilstring, der im Seitentitel vorkommen soll

Wenn man diese Parameter nun mit den Standard URLs, oder Seitentiteln der diversen Webcam Hersteller füttert findet man zahlreiche direkte Webcam Links.

**Hier ein paar Beispiele (mit Anführungszeichen!)**:

inurl:"view/indexFrame.shtml"

inurl:"view/index.shtml"

intitle:axis camera

intitle:"snc-rz30 home"

inurl:"ViewerFrame?Mode=Motion"

inurl:LvAppl intitle:liveapplet

intitle:"Live View / - AXIS"

"Powered by webcamXP"

inurl:indexFrame.shtml "Axis Video Server"

MOBOTIX M1" and "open menu"

intitle:flexwatch

intext:"Copyright by Seyeon TECHCo"

intitle:"WJ-NT104 Main"

inurl:"axis-cgi/mjpg"

sample/LvAppl/

inurl:home/homeJ.html

inurl:main/flashLogin.html

inurl:next_file=main_fs.htm

inurl:/login.ml

intitle:User

"Webthru User Login"

"Please enter username and password to log in to system"

inurl:Ctl/index.htm?Cus

Configuration "Pop-up Live Image"

inurl:"*.viewnetcam.com"

inurl:Remote/index.php3

intitle:Live Video

"TOSHIBA Network Camera - User Login"

Es gibt Websiten, die die gefundenen Webcams mit Thumbnails indizieren und mit Meta-Informationen, wie dem Standort katalogisieren.
![Opentopia Webcam Catgorizer](//picdump.thafaker.de/2007/07/webcaminurl.png)
[ http://www.opentopia.com/hiddencam.php](http://www.opentopia.com/hiddencam.php)
