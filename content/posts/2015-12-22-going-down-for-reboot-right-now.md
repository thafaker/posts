---
title: Going down for reboot right now - Ghost 0.7.4
slug: going-down-for-reboot-right-now
date_published: 2015-12-22T22:17:43.000Z
date_updated: 2018-08-22T09:39:26.000Z
tags: fix.it, ghost, update, 0.7.4
---

Ghost 0.7.4 steht zum Download zur Verfügung. Grund genug, unser System zu aktualisieren und die Website kurzzeitig offline zu nehmen. Theoretisch merkt man nichts. Praktisch hoffentlich auch nicht. *Hoffentlich*.

![](__GHOST_URL__/content/images/2015/12/findings-ghost.jpg)

Ghost 0.7.4 is now available on GitHub, npm and Ghost.org. This contains a handful of bug fixes for things which weren't quite right in 0.7.3, particularly relating to the new Public API features.

#### Highlights

- [Fixed] Tag pages for tags starting with numbers
- [Fixed] Helpers still causing aSyNcId errors when used inside the `{{#get}}` helper
- [Fixed] `ghost.url.api()` utility issue with multiple requests
- [Fixed] authentication error on resubmitting setup/two
- [Fixed] broken `@last` when using `{{#foreach}}` with limit
- [Fixed] Duplicate URL input field in image uploader

#### Wie aktualisieren?

Auf Uberspace gibt es ein geiles `update-ghost.sh` Script, was automatisch ein Backup anlegt, den Service stoppt, Ghost aktualisiert und wieder startet. *Easy Living*.

#### Download

- [Ghost selbst](https://ghost.org/download/)

**Note**: Having a correctly configured url in config.js is a hard requirement since 0.7.2. If you get the error Access Denied from url whilst trying to login, please see the configuration documentation.
