---
title: Ein paar coole "Default Write" Kommandos für OS X
slug: ein-paar-coole-default-write-kommandos-fur-os-x
date_published: 2012-10-09T20:01:10.000Z
date_updated: 2018-08-22T09:39:14.000Z
---

![redsn0w_just_boot_tethered_now_terminal](//picdump.thafaker.de/2011/08/redsn0w_just_boot_tethered_now_terminal-150x150.png)Yo, da OS X auf einem Unix-artigen OS (BSD) basiert und deshalb auch grundlegend über ein Terminal verfügt, diese eben auch noch genau so mächtig wie unter Linux o.ä. ist und ich dieses OS gerne benutze, ist es nun Zeit, ein paar Befehle vorzustellen, die das Look & Feel von OS X nachhaltig verändern können, via Terminal. 

Los gehts, meine persönlichen Lieblinge sind 3D-Dock und Dock Delay.

### Remove the Auto-Hide Dock Delay

Wenn man das Dock ausblendet, gibt es eine kurze Verzögerung, diese kann man mit folgendem Befehl deaktivieren, und fortan erscheint das Dock sofort:
`defaults write com.apple.Dock autohide-delay -float 0 && killall Dock`
### 3D-Dock deaktivieren

Mit diesem Befehl schaltet man das 3D-Dock aus und stellt ein zweidimensionales Doch ein, so wie es damals unter OS X 10.4 aussah:
`defaults write com.apple.dock no-glass -boolean YES; killall Dock`
### Mission Control beschleunigen

Noch ein Befehl, der kurze Verzögerungen, diesmal im Mission Control, entfernt und dadurch OS X schneller abgehen lässt.
`defaults write com.apple.dock expose-animation-duration -float 0.12 && killall Dock`
### Mache die Symbole von ausgeblendeten Programmen im Dock durchsichtig

Cooler Befehl, der die Symbole von Programmen die gerade ausgeblendet sind, im Dock durchsichtig darstellt. Somit kann man auch im Dock sehen, was ausgeblendet ist. [So sieht das aus](http://osxdaily.com/2010/06/22/make-hidden-application-icons-translucent-in-the-dock/).
`defaults write com.apple.Dock showhidden -bool YES && killall Dock`
### Textauswahl in Quicklook aktivieren

Warum es per Default nicht geht, kapiert keiner, so kann man es aktivieren.
`defaults write com.apple.finder QLEnableTextSelection -bool TRUE;killall Finder`
### Versteckte Dateien im Finder anzeigen

Yo, kann man auch so im Finder aktivieren, aber wenn man ein mal dabei ist, kann man es auch per Terminal machen.
`defaults write com.apple.finder AppleShowAllFiles -bool YES && killall Finder`
### Verstecke alle Desktop Symbole

Mit folgendem Befehl kann man alle Symbole auf seinem Desktop ausblenden, sie sind dann aber noch über den Finder aufzurufen, nur der Desktop ist eben frei.
`defaults write com.apple.finder CreateDesktop -bool false && killall Finder`
### Speicherort von Screenshots ändern

Screenshots werden immer auf dem Desktop gespeichert, aber natürlich kann man den Speicherort ändern. Zum Beispiel auf /Bilder/Screenshots oder /Desktop/Screenshots.
`defaults write com.apple.screencapture location ~/Pictures/Screenshots`
### Speicherformat von Screenshots ändern

Passend zum Tipp vorher kann man mit einem Befehl auch festlegen, dass Screenshots nicht als PNG sondern als JPG gespeichert werden. PNG sind mir zu groß und eigentlich reicht die schlechtere Qualität von JPGs völlig für meine Screenshotbelange.
`defaults write com.apple.screencapture type jpg && killall SystemUIServer`
