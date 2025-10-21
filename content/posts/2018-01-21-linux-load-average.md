---
title: Load Average verstehen
slug: linux-load-average
date_published: 2018-01-21T13:58:56.000Z
date_updated: 2018-08-22T09:37:41.000Z
tags: linux, terminal, load average, how to, anleitung, howto, tutorial
---

Ich bin mir nicht sicher, ob Sie schon mal mit Linux zu tun hatten? Also auf der Kommandozeile. Nun, wenn dem aber so ist, dann kennen sie sicher diese ominösen *load average*-Werte, die einem beispielsweise bei *uptime* angezeigt werden, oder nicht? Und wissen Sie denn auch, was diese Werte eigentlich bedeuten, wie sie gelesen werden müssen und ab wann es praktisch nicht mehr gut ist - *overloaded*? Sehen sie, ich auch nicht! 

Grund genug also, einen Artikel darüber zu schreiben!

![](https://images.unsplash.com/photo-1510746001195-0db09655b6db?ixlib=rb-0.3.5&amp;q=80&amp;fm=jpg&amp;crop=entropy&amp;cs=tinysrgb&amp;w=1080&amp;fit=max&amp;ixid=eyJhcHBfaWQiOjExNzczfQ&amp;s=d75873395f350bbdf8c4608f94e3f573)
Photo by [Jonas Svidras](https://unsplash.com/@jonassvidras?utm_source=ghost&amp;utm_medium=referral&amp;utm_campaign=api-credit) / [Unsplash](https://unsplash.com/?utm_source=ghost&amp;utm_medium=referral&amp;utm_campaign=api-credit)

Aber zunächst ein mal zum grundlegenden Verständnis. Warum sind das immer drei Werte, und warum sind die unterschiedlich?

`load average: 1.45, 1.95, 2.22`

Der erste Wert ist die momentane Belastung (1.45). Der zweite Wert ist die Auslastung der letzten 5 Minuten (1.95). Und der dritte Werte ist die Auslastung der letzten 15 Minuten (2.22). Diese drei Zahlen sagen also etwas ganz unterschiedliches über einen Computer aus. Momentan kann die erste Zahl einen hohen Wert haben, was aber noch nichts bedeuten muss, betrifft es ja nur den Moment, das jetzt! Denn wenn man auf den dritten Werten schaut und sich dieser im Rahmen hält, hat man noch kein dauerhaftes Problem, denn auf 15 Minuten gesehen war die Auslastung also doch nicht so hoch. Erst wenn der dritte Wert dauerhaft zu hoch ist, dann ist unser Rechner auch dauerhaft am Ende und seinen Aufageben nicht mehr gewachsen. Aber der Reihe nach, woher weiß ich denn nun, welcher Wert für was steht und wann ich Grund zur Sorge habe?

#### Verkehr, sozusagen

Wir sehen zum Verständnis von **load** eine Single-Core CPU praktisch wie eine Einbahnstraße. Wenn wir uns jetzt vorstellen, wir sitzen an dieser Straße, und diese Autos müssen an uns vorbei fahren und wir würden das steuern, dann wäre das quasi folgendermaßen: Ist die Straße perfekt ausgelastet, dann gäbe es keinen Verzug, es wäre bei 1.0. Alle Autos kämen gleichmäßig durch. Aber nur ein Auto mehr, und wir hätten ein Problem, das Auto müsste warten und käme nicht mehr weiter. *Delay*. Genau so ist das mit unserem Load. Alles unter 1 ist nicht ausgelastet. Alles über 1 ist überlastet. Eins ist also der Wert der perfekten Auslastung, darunter ist noch Luft, darüber ist überlastet.

Wir beziehen dieses Wissen auf unsere drei Werte, die *load average* ausgibt. Erst wenn unser dritter Wert über 1.0 ist, dann haben wir ein Problem, denn dann ist unser Rechner nicht nur kurzzeitig (Wert 1), sondern dauerhaft überlastet.

Der **Load von 0.5** (wenig ausgelastet)
![load_0.5](__GHOST_URL__/content/images/2018/01/load_0.5.png)

Der **Load von 1.0** (quasi perfekt ausgelastet)
![load_1.0](__GHOST_URL__/content/images/2018/01/load_1.0.png)

Der **Load von 1.5** (sozusagen über die Hälfte überlastet)
![load_1.5](__GHOST_URL__/content/images/2018/01/load_1.5.png)

Die Daten bei einem Load über 1.0, die warten müssen, gehen nicht verloren, es dauert nur länger, bis sie bearbeitet werden, ganz so wie bei unserer Straße. Die Autos müssten eben warten bis sie weiter fahren könnten, wir hätten Stau.

#### Also ist ein Load von 1.0 perfekt?

Nun... nicht ganz. Das Problem mit einer Auslastung von 1.0 ist, dass man keinerlei Platz mehr hätte. Kein Quäntchen wäre übrig. Viele Sysadmins schauen also, dass ihre Rechner bei < 0.70 liegen. Wenn dieser Wert dauerhaft überschritten wird, werden Sie aktiv. Knapp über den Daumen gepeilt kann man also als Administrator folgendes konstatieren:

- Ab einem dauerhaften Load von 0.70 sollte man ein Auge darauf haben und darüber nachdenken warum, bevor sich die Dinge zuspitzen und zum Problem werden.
- Bei einem dauerhaften Wert von 1.0 und darüber sollte man schleunigst heraus finden, woran das liegt und das Problem abstellen.
- Bei einem dauerhaften Wert von 5.0 und darüber hat man ernsthafte Schwierigkeiten. Der Rechner hängt entweder schon komplett, oder er ist so langsam, dass eigentlich nichts mehr richtig funktioniert. Dorthin sollte die Reise also niemals gehen, denn dann hat man eigentlich schon verloren.

Ein kluger Administrator lässt es also nicht soweit kommen und passt ab 0.70 auf.

![Beispiel load average Auslastung](__GHOST_URL__/content/images/2018/01/f-r_load-1.png)

In diesem Bild sehen wir einen *load average* von `load average: 5.64, 5.63, 4.62`. Was sagt uns das? Die Kiste ist gerade ziemlich ausgelastet, Wert 1 ist bei über 5. Wir sehen das in diesem Beispiel auch an der CPU-auslastung, diese ist bei knapp 100%. Wir sehen an Wert 2, 5.63, dass dieser Zustand schon länger anhält, da auch dieser über 5 ist. Und bei Wert 3 sehen wir schließlich mit 4.62, dass diese Kiste schon die ganze Zeit viel rechnen muss. Wir hätten also einen völlig überlasteten Computer identifiziert. [[1]](#fn1)

#### load average bei Multi-Prozessor/Multi-Kern CPUs?

Wie ist das denn jetzt bei heutigen Multi-Kern oder Multi-CPU Computern. Gilt hier ebenfalls der Wert von 1, oder verhält es sich anders?

Bei Mehrkern-Computern verhält es sich so, dass der Schwellenwert von Load die Zahl der CPU(Core)s ist. Der Wert von 1 gilt für eine Single-Core-CPU. Bei einem Computer mit 4 Kernen wäre der entsprechende Wert also 4.

Kommen wir nun auf den obigen Screenshot zurück, dann verhält es sich folgendermaßen: Dieser Utilite Pro ist ein 4-Kern-Computer. Der Load von 4 entspräche also 1. Wir sind bei knapp 5, haben also eine Überlastung, aber diese ist gar nicht so hoch, da wir nicht von 1 sondern 4 ausgehen.

*Anders ausgedrückt*: bei einer Single-Core-CPU entspricht der Wert von 1.00 einer Auslastung von 100%. Bei einer Dual-Core Machine entspricht der Wert von 2.00 einer Auslastung von 100%.

Bei einer 4-Kern-Machine würde man erst ab einem dauerhaften Load von 3.70 näher nach schauen, vorher nicht.

Ich hoffe, das war irgendwie verständlich und das Grundprinzip ist klar geworden?

---

1. 
Jedoch muss man hier am beispiel wissen, dass der Utilite Pro gerade einen Kernel kompilierte und deshalb so extrem viel rechnete. Es war also nur ein temporäres Problem. [↩︎](#fnref1)
