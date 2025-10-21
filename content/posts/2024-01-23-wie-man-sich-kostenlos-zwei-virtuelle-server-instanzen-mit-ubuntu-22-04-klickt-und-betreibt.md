---
title: Teil 1 - Wie man sich kostenlos eine virtuelle Server-Instanz mit Ubuntu 22.04. klickt und damit GHOST betreibt
slug: wie-man-sich-kostenlos-zwei-virtuelle-server-instanzen-mit-ubuntu-22-04-klickt-und-betreibt
date_published: 2024-01-23T06:19:47.000Z
date_updated: 2024-02-01T20:09:49.000Z
tags: ghost, oracle cloud, lubuntu, free, anleitung, howto, how to
excerpt: Teil 1 - Ich werde in dieser Blogreihe darüber berichten, wie man sich bei Oracle Cloud registriert, eine kostenlose Instanz klickt, die Virtuelle Maschine startet, diese Maschine als Webserver konfiguriert und letztendlich Ghost nebst Datenbank installiert.
---

Ich habe in meiner Announcement-Bar über dem Weblog schon darauf hingewiesen: ich bin mit **thahipster.de** von *Uberspace *hin zu **Oracle Cloud** gewechselt. Das musst ich tun, weil ich Ghost nicht mehr aktualisieren konnte und es bei Uberspace auch keinen Weg mehr gab, so leid es mir tat.
Der ursprüngliche Artikel stammt von [hier](https://bitmapbytes.com/how-to-setup-an-account-with-oracle-cloud/), ich habe ihn aktualisiert und geprüft.
Um so erfreuter bin ich über den Umstand, dass, jetzt wo sie dies hier lesen, der Wechsel geklappt hat. thahipster.de läuft nun auf zwei Servern, einem mit NGinX und Ghost, dem anderen mit MySQL 8 und der zugehörigen Ghost-Datenbank. Und es scheint Snappy zu sein. *Kommentiert gern unter diesem Artikel wenn ihr Fehler entdeckt.*

Ich werde in dieser **Blogreihe** darüber berichten wie man sich bei Oracle Cloud registriert, eine kostenlose Instanz klickt, die Virtuelle Maschine startet, diese Maschine als Webserver konfiguriert und letztendlich Ghost nebst Datenbank installiert.

## Table of Contents

1. **Teil 1 - Einrichten eines Accounts bei Oracle Cloud**
2. [Teil 2 - Hochfahren einer Oracle Virtual Machine](__GHOST_URL__/teil-2-hochfahren-einer-oracle-virtual-machine/)
3. [Teil 3 - Konfiguriere die Oracle Virtual Machine als Webserver](__GHOST_URL__/teil-3-konfiguriere-die-oracle-virtual-machine-als-webserver/)
4. [Teil 4 - Installiere Ghost CMS](__GHOST_URL__/teil-4-installiere-ghost-cms-auf-oracle-cloud-always-free-instanz/)

---

## Teil 1 - Einrichtung Oracle Cloud

In diesem Leitfaden richten wir uns ein kostenloses Oracle Cloud-Konto ein. Wir benötigen die Kreditkarte, aber keine Sorge, diese dient nur der Authentifizierung und Ersteinrichtung des Cloud-Kontos.

💡

Es fallen nur Kosten an, wenn man einen Dienst upgraded oder einen Dienst auswählt, der nicht Teil der Stufe „Immer kostenlos“ ist. Das beachten wir in diesem Tutorial.

### **Signing up for an account**

1. Gehe zur Oracle Cloud-Anmeldeseite:
[https://signup.cloud.oracle.com/](https://signup.cloud.oracle.com/)

![Reg Account oracle cloud](__GHOST_URL__/content/images/2024/01/Bildschirmfoto-2024-01-21-um-20.50.52.png)Reg Account oracle cloud
1. E-Mail Adresse bestätigen

![Verify Email Oracle Cloud&nbsp;](__GHOST_URL__/content/images/2024/02/image-2.png)Verify Email Oracle Cloud 
1. Füge die Kontoinformationen hinzu:

![](__GHOST_URL__/content/images/2024/02/image-3.png)
1. Überprüfe die Adresse und Zahlung

💡

**Ich hatte hier ein paar Probleme mit der Zahlungsüberprüfung**
Aber nach ein paar Versuchen, die Verifizierungskarten zu ändern, war mein Konto eingerichtet.

![](__GHOST_URL__/content/images/2024/02/image-4.png)

💡

**Meine kostenlose Testversion starten??? **
*Machen dir keine Sorgen – es werden keine Kosten berechnet, es sei denn, man aktualisiert einen Dienst oder wählt einen kostenpflichtigen Dienst aus - es kann nicht von allein passieren*

Man kann die *Always Free*-Ressourcen ohne zeitliche Einschränkungen so lange nutzen, wie man möchte – vorbehaltlich der angegebenen Kapazitätsgrenzen. Wenn der 30-Tage Testzeitraum für die erweiterten Dienste endet, kann man die Always Free-Dienste ohne Unterbrechung weiter nutzen. Der 30-Tage-Testzeitraum beinhaltet 250€ Upgradekosten, die man gern verballern kann. Bei mir und in diesem Tutorial steht das aber nicht zur Debatte.

Die Instanzen „Immer kostenlos“ und „Kostenlose Testversion“ können jederzeit nahtlos auf kostenpflichtige Instanzen aktualisiert werden. Bestehende Oracle Cloud-Kunden haben automatisch Zugriff auf Always Free-Dienste – keine Neuanmeldung erforderlich.

Die Einrichtung unseres Oracle Cloud Accounts wäre abgeschlossen.

---

*Hier geht es nun weiter*...

[**Teil 2 - Hochfahren einer Oracle Virtual Machine**](__GHOST_URL__/teil-2-hochfahren-einer-oracle-virtual-machine/)
[

Teil 2 - Hochfahren einer Oracle Virtual Machine

Teil 2 - Ich werde in dieser Blogreihe darüber berichten wie man sich bei Oracle Cloud registriert, eine kostenlose Instanz klickt, die Virtuelle Maschine startet, diese Maschine als Webserver konfiguriert und letztendlich Ghost nebst Datenbank installiert.

![](__GHOST_URL__/content/images/size/w256h256/2019/06/logo.png)thahipster.deHerr Montag

![](https://images.unsplash.com/photo-1526374965328-7f61d4dc18c5?crop=entropy&amp;cs=tinysrgb&amp;fit=max&amp;fm=jpg&amp;ixid=M3wxMTc3M3wwfDF8c2VhcmNofDN8fHZpcnR1YWwlMjBtYWNoaW5lfGVufDB8fHx8MTcwNTk5MTE3MHww&amp;ixlib=rb-4.0.3&amp;q=80&amp;w=2000)
](__GHOST_URL__/teil-2-hochfahren-einer-oracle-virtual-machine/)Der ursprüngliche Artikel stammt von [hier](https://bitmapbytes.com/how-to-setup-an-account-with-oracle-cloud/), ich habe ihn aktualisiert und geprüft.
