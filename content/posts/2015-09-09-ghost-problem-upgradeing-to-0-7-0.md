---
title: "[GHOST] Problem upgrading to 0.7.0 (SQLITE_ERROR: too many SQL variables)"
slug: ghost-problem-upgradeing-to-0-7-0
date_published: 2015-09-09T11:48:26.000Z
date_updated: 2018-08-22T09:39:25.000Z
tags: error, ghost, english, update, sqlite, uberspace, upgrade, slite, 0.7.0, SQLITE_ERROR: too many SQL variables
---

I tried to upgrade to the freshly announced Ghost 0.7.0, "the biggest major update in 2015" - but I ended up with a database error after the migration/update is complete. My ghost is using **sqlite** on an uberspace account. So far, so bad. 

This is the error I get:

---

` Migrations: Database upgrade required from version 003 to 004`
` Migrations: Creating database backup`
` Migrations: Database backup written to: /thafaker-2015-09-09.json`
` Migrations: Populating default settings`
` Migrations: Complete`
` Migrations: Updating fixtures`
` Migrations: Upgrading fixtures to 004`
` Migrations: Update isPrivate setting`
` Migrations: Update password setting`
` Migrations: Update ghost-admin client fixture`

`ERROR: SQLITE_ERROR: too many SQL variables`

` Error: SQLITE_ERROR: too many SQL variables`

---

This is exactly the same problem the [user](https://ghost.org/forum/installation/19384-when-trying-to-upgrade-i-get-this-error-error-sqlite_error-too-many-sql-variables/) is getting here. But there is also no solution.

Sadly, I don't know how to post to the ghost-forum, so I just linked the article.

When I try to check my database with sqlite command line, everything is okay, so there should be another problem.
