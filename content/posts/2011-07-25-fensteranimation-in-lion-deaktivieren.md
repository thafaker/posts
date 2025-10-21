---
title: Fensteranimation in Lion deaktivieren
slug: fensteranimation-in-lion-deaktivieren
date_published: 2011-07-25T09:14:06.000Z
date_updated: 2018-08-22T09:38:35.000Z
---

Wer die Animation in Lion, bei der die Fenster kurz verzögert aufspringen, für nervig erachtet, kann diese über das *Terminal* schnell deaktivieren: Dafür genügt die Eingabe von

    Defaults write NSGlobalDomain NSAutomaticWindowAnimationsEnabled -bool NO

sowie die anschließende Bestätigung mit der Return-Taste. Um die Fenster-Bewegung zu reanimieren, ist das "NO" am Ende durch ein "YES" zu ersetzen.

Eventuell will man sogleich das 3D-Dock deaktivieren, welches mit 10.5 Einzug erhielt, dies wird in folgendem Artikel beschrieben. [MAC OS X 3D-Dock abschalten](__GHOST_URL__/to-remind-mac-os-x-105-leopard-3d-dock-abschalten/).
