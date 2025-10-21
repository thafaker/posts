---
title: Diaspora MySQL Tabellen Error
slug: diaspora-mysql-tabellen-error
date_published: 2011-12-01T17:50:17.000Z
date_updated: 2018-08-22T09:38:27.000Z
---

Wenn ihr nach der Installation und dem erfolgreichen Start eures **Diaspora-Pods** einen Fehler erhaltet, diverse MySQL Tabellen würden nicht gefunden werden, so ist das ein Bug, weil Diaspora eigentlich mit der Ruby-Datenbank läuft.

> After calling login of the Diaspora-Pod (yourdomain.com/users/ we get the error
> 
> Mysql2::Error in Devise/sessionsController#new
> 
> Table 'DATABASENAME.users' doesn't exist
> 
> Rails.root: /home/diaspora
> 
> lib/chrome_frame.rb:39:in `call'
> 
> because there are no tables in the new database.
> 
> ---
> 
> ODER im Produktionsmodus ebenfalls folgender Fehler im Log:
> 
> ---
> 
> rake aborted!
> Table 'diaspora_production.contacts' doesn't exist
> 
> Tasks: TOP => resque:work => rescue:setup
> 
> ---

Abhilfe schaffte bei mir die Eingabe von folgenden zwei Befehlen (nacheinander)

> `bundle exec rake spec``bundle exec rake db:migrate`

Und nun rennt mein Diaspora-Pod ziemlich gut vor sich hin, was mir rein gar nichts einbringt, außer natürlich dem **Success**.

Leider konnte ich den Fehler nur bei einem Pod im Development-Modus lösen, läuft dieser im Productionmode, so tritt der Fehler weiterhin auf.

---

*Um auf dem Laufenden zu bleiben, könnt ihr uns auf [Twitter](http://twitter.com/#%21/thafakerde) folgen oder die [Facebook-Seite](http://de-de.facebook.com/pages/thafaker-auf-Beton/154600141278763) besuchen.*

---
