---
title: Teil 2 - Hochfahren einer Oracle Virtual Machine
slug: teil-2-hochfahren-einer-oracle-virtual-machine
date_published: 2024-01-23T06:19:52.000Z
date_updated: 2024-02-01T20:14:58.000Z
tags: ghost, oracle cloud, anleitung, howto, how to, nginx
excerpt: Teil 2 - Ich werde in dieser Blogreihe darüber berichten wie man sich bei Oracle Cloud registriert, eine kostenlose Instanz klickt, die Virtuelle Maschine startet, diese Maschine als Webserver konfiguriert und letztendlich Ghost nebst Datenbank installiert.
---

Ich werde in dieser **Blogreihe** darüber berichten wie man sich bei Oracle Cloud registriert, eine kostenlose Instanz klickt, die Virtuelle Maschine startet, diese Maschine als Webserver konfiguriert und letztendlich Ghost nebst Datenbank installiert.

## Table of Contents

- [Teil 1 - Einrichten eines Accounts bei Oracle Cloud](__GHOST_URL__/wie-man-sich-kostenlos-zwei-virtuelle-server-instanzen-mit-ubuntu-22-04-klickt-und-betreibt/)
- **Teil 2 - Hochfahren einer Oracle Virtual Machine**
- [Teil 3 - Konfiguriere die Oracle Virtual Machine als Webserver](__GHOST_URL__/teil-3-konfiguriere-die-oracle-virtual-machine-als-webserver/)
- [Teil 4 - Installiere Ghost CMS](__GHOST_URL__/teil-4-installiere-ghost-cms-auf-oracle-cloud-always-free-instanz/)

---

**Teil 2 - Hochfahren einer Oracle Virtual Machine**

Öffnen Sie im Oracle Cloud Dashboard – [cloud.oracle.com](https://cloud.oracle.com) – das Navigationsmenü, bewegen Sie den Mauszeiger über „Compute“ und wählen Sie im Compute-Panel „Instanzen“ aus.
![Oracle Cloud Dashboard neue Instanz anlegen](__GHOST_URL__/content/images/2024/01/Bildschirmfoto-2024-01-22-um-16.02.07.png)Oracle Cloud Dashboard neue Instanz anlegen
Wählt links ein "Compartment" aus. Jetzt klicken wir auf "Instanz erstellen" um fortzufahren.
![Oracle Cloud Dashboard neue Instanz erstellen](__GHOST_URL__/content/images/2024/01/Bildschirmfoto-2024-01-22-um-16.03.51.png)Oracle Cloud Dashboard neue Instanz erstellen
Fügen Sie Ihrer VM-Instanz einen Namen hinzu und wählen Sie den Link „**Bearbeiten**“, um „Image und Ausprägung“ zu ändern.
![](__GHOST_URL__/content/images/2024/01/Bildschirmfoto-2024-01-22-um-16.06.43.png)Oracle Cloud Dashboard neue Instanz erstellen
Lassen Sie uns das Image von Oracle Linux 8 auf **Ubuntu** ändern, indem Sie auf die Schaltfläche „**Image ändern**“ klicken. Ubuntu wird offiziell von Ghost unterstützt.
![](__GHOST_URL__/content/images/2024/01/Bildschirmfoto-2024-01-22-um-16.08.18.png)Oracle Cloud Dashboard neue Instanz erstellen
Wählt "**Canonical Ubuntu 22.04**" indem ihr den Haken setzt.

Im nächsten Schritt, also wenn wir weiter nach unten scrollen, müssen wir **unbedingt **die SSH-Keys herunter laden, damit wir später Zugriff auf unsere Instanz erhalten. **Private** und **Public**-Key.
![Oracle Cloud Dashboard SSH-Keys speichern](__GHOST_URL__/content/images/2024/01/Bildschirmfoto-2024-01-22-um-16.10.45.png)Oracle Cloud Dashboard SSH-Keys speichern
Und schließlich können wir die Festplattengröße festlegen. Der Standardwert beträgt 50 GB, wir können ihn jedoch (bei Bedarf) auf bis zu 200 GB erhöhen, das ist dann auch immer noch always free.
![Oracle Cloud Dashboard Festplattengröße](__GHOST_URL__/content/images/2024/01/Bildschirmfoto-2024-01-22-um-16.12.30.png)Oracle Cloud Dashboard Festplattengröße
Wähle abschließend die Schaltfläche „Erstellen“ in der Fußzeile aus. Die Bereitstellung dauert einige Minuten, aber danach verfügen wir über eine Ubuntu-VM, die in der Cloud ausgeführt wird. *Sehr gut*.

---

**Aktualisieren und Auschecken Ihrer neuen VM.**

Wechseln Sie zu den Compute-Instanzen zurück. Dort sollte Ihre neue Instanz mit der Flagge „Immer kostenlos“ angezeigt werden.
![](__GHOST_URL__/content/images/2024/02/Bildschirmfoto-2024-02-01-um-21.13.15-1.png)Oracle Cloud Dashboard Instanzen
Wählen Sie hier Ihren Instanznamen aus. Sie können sehen, dass der Standardbenutzername „ubuntu“ zugewiesen wird, und auch die öffentliche IP-Adresse der VM. Kopieren Sie die öffentliche Adresse und konfigurieren Sie ihren SSH Client der Wahl, bei mir ist das einfach das Terminal von Mac oder Linux. Wie man via Terminal und Key per SSH zu einem Server verbindet, hat Oracle [hier](https://docs.oracle.com/en-us/iaas/Content/GSG/Tasks/testingconnection.htm) beschrieben, es ist der normale Standardweg.
![Oracle Cloud Dashboard öffentliche externe IP](__GHOST_URL__/content/images/2024/01/Bildschirmfoto-2024-01-22-um-16.30.43-1.png)Oracle Cloud Dashboard öffentliche externe IP
`ssh -i private-vm-key.key ubuntu@Eure_öffentliche_IP`

Und schon seid Ihr mit eurem neuen Server verbunden:
![iTerm 2 macOS ssh Verbindung zu neuer Oracle Instanz](__GHOST_URL__/content/images/2024/01/Bildschirmfoto-2024-01-22-um-16.34.03.png)iTerm 2 macOS ssh Verbindung zu neuer Oracle Instanz
---

Lasst uns das System erst mal updaten, dazu nutzen wir die Standardbefehle von Ubuntus Paketmanager **apt**.

    # Update the packages
    sudo apt update
    
    # upgrade packages 
    sudo apt upgrade

💡

*Akzeptiert jede zusätzliche Anfrage zur Nutzung von Speicherplatz. Je nachdem wie viele Updates geladen und installiert werden müssen, kann das eine Weile dauern.*

Herzlichen Glückwunsch, eure Instanz steht und läuft.

---

*Hier geht es nun weiter*...

[**Teil 3 - Konfiguriere die Oracle Virtual Machine als Webserver**](__GHOST_URL__/teil-3-konfiguriere-die-oracle-virtual-machine-als-webserver/)
[

Teil 3 - Konfiguriere die Oracle Virtual Machine als Webserver

Teil 3 - Ich werde in dieser Blogreihe darüber berichten wie man sich bei Oracle Cloud registriert, eine kostenlose Instanz klickt, die Virtuelle Maschine startet, diese Maschine als Webserver konfiguriert und letztendlich Ghost nebst Datenbank installiert.

![](__GHOST_URL__/content/images/size/w256h256/2019/06/logo.png)thahipster.deHerr Montag

![](https://images.unsplash.com/photo-1489875347897-49f64b51c1f8?crop=entropy&amp;cs=tinysrgb&amp;fit=max&amp;fm=jpg&amp;ixid=M3wxMTc3M3wwfDF8c2VhcmNofDV8fGRhdGFiYXNlfGVufDB8fHx8MTcwNTk5MTIwMHww&amp;ixlib=rb-4.0.3&amp;q=80&amp;w=2000)
](__GHOST_URL__/teil-3-konfiguriere-die-oracle-virtual-machine-als-webserver/)
