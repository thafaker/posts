---
title: Was sind eigentlich Delta RPM?
slug: was-sind-eigentlich-delta-rpm
date_published: 2011-04-17T16:48:05.000Z
date_updated: 2018-08-22T09:38:38.000Z
---

Jeder der in jüngerer Vergangenheit ((so in den letzten 4 Jahren)) an einer Linux-Distribution auf RPM ((Suse, RedHat, Fedora (Core), CentOS, Mandrake...)) basierend gearbeitet hat, wird bei Update-Prozessen mit Delta-RPMs in Berührung gekommen sein.

Aber was zur Hölle sind diese Delta RPM?

![180px-RPM_Logo.svg](//picdump.thafaker.de/2011/04/180px-RPM_Logo.svg_.png)Delta-RPM-Pakete enthalten die Unterschiede zwischen einer alten und  einer neuen Version eines RPM-Pakets. Wenn Sie ein Delta-RPM auf ein  altes RPM anwenden, ergibt dies einen vollständig neuen RPM. Es ist  nicht erforderlich, dass eine Kopie des alten RPM vorhanden ist, da ein  Delta-RPM auch mit einem installierten RPM arbeiten kann. Die  Delta-RPM-Pakete sind sogar kleiner als Patch-RPMs, was beim Übertragen  von Update-Paketen über das Internet von Vorteil ist. Der Nachteil ist,  dass Update-Vorgänge mit Delta-RPMs erheblich mehr CPU-Zyklen  beanspruchen als normale oder Patch-RPMs.

So, dann hätten wir also auch dieses Mysterium enttarnt und können wieder ganz gepflegt unserer Arbeit nachgehen.
