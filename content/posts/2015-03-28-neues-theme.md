---
title: New Theme
slug: neues-theme
date_published: 2015-03-28T20:52:55.000Z
date_updated: 2018-08-22T09:37:55.000Z
tags: hello world, wp2ghost, error, wp-content, english
---

**It's** been a long time since I first tried to move my weblog at [thafaker.de (archiviert)](http://web.archive.org/web/20060425043208/http://www.thafaker.de:80/) to ghost.

The weblog there at thafaker.de is powered by *Wordpress*. So far, so good, there are different ways to export everything and import it back to ghost and normally, it's not a big deal. But for me, it is.

Mostely the MOVE is made with xml and json, export from wordpress to *xml*, [convert](https://github.com/jonhoo/wp2ghost) it to *json*, import to ghost via json - done.

But this only works if your database at wordpress is not too big. Like mine is. *Otherwhise*, **Worpdress** fails to run the export script long enough and it falls into errors or simply does nothing. I can export it via SQL, but I dont know how I can convert my whole 60 MB zipped SQL Database and use it with json.

And that's the reason I never got this thing done. But with this new [Theme](http://zutrinken.com/) I am actually running here at janmontag.de - and now we are going back to my headline - I will try it again. The Moveing. I got new motivation because it looks so nice, the typo is so sexy and… yeah, I simply love it.

- I exportet everything to xml from wordpress by years, so I have several xml files with the content of my old wordpress weblog
- I tried to install wp2ghost but it doenst work. I can't get it running on my mac neither in my uberspace. [**UPDATE**] It runs now.
- After the posts itself (the text), there is no solution for all the images in my weblog. Again, I startet my blog in 2005, there are 60 MB posts.sql and lots of Gigabyte Images and other things.
- [**UPDATE**] Things going better and better. I now used the a way described above. I only export xml by year and than wp2ghost it to json, the converting-process runs flawelessly and than I  directly import it to ghost. *It works*.
- …

Hello friends, now I can finally say the golden words: **I AM DONE**. You can browse this weblog, it countains every article since 2005. But there is still the problem with my old uploaded wp-content. Maybe I can change the new urls to the old folder via .htaccess file.
