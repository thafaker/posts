---
title: how to mass edit post status in ghost database (ghost.db)
slug: ho-to-mass-edit-post-status-in-ghost-database
date_published: 2015-04-02T20:49:15.000Z
date_updated: 2018-08-22T09:39:22.000Z
tags: ghost, how to, english, howto, anleitung, mass editing sql, sqlite, ghost db, scheme.js
---

Maybe you've also asked yourself a few times "how can I change the post status of one or more posts in my ghost blog". Because you migrated from [wordpress to ghost](__GHOST_URL__/thafaker-de-von-wordpress-zu-ghost/) and set the status of more than 250 posts to draft long time ago - but want to change that now, *after* the migration to ghost. 

1. At first I backed up the sqlite database (17,9 MB) to my Mac. You can find it there: `$webserver/ghost/content/data/ghost.db` If you are fucked up, there is always a working copy on your webserver. *Hopefully*! I backuped the DB twice.
2. Shortly after, I installed a free sqlite tool to peek around with the dbase, named  **sqlitebrowser.app** and is completely free to use, for *Mac OS X* (dunno what to do in windows). Download it [here](http://sourceforge.net/projects/sqlitebrowser/). Not nice, but functional enough for our plan.
3. Now I started the app and loaded the db into it.
4. I firstly executed the following command to see how many posts are affected:
`SELECT count(*) FROM posts WHERE status = 'draft'`
5. Count: 255
6. Okay, there are 255 posts in my db which are in state "draft" and not visible for my audience. I need to change that.
7. The final command is:
`UPDATE posts SET status= 'published' WHERE status = 'draft';`
8. done. That's all. All the 255 posts are now published. Mass edited by the power of the sql command. Don't forget to click "write changes".
9. Upload your edited database back to your server.
10. Login to ghost to see if there are any drafts - there shouldn't be one.
11. DONE.

It is possible to edit only posts from a specific time, maybe you have drafts from 2009, than you can use the following code and edit it for your needs:
`SELECT count(*) FROM posts WHERE created_at = '2005' AND status = 'draft'`

This will show all drafts from the year 2005.

Another example, all posts after a specific date:
`UPDATE posts SET status= 'published' WHERE  created_at = < '2009-09-09 09:09:09' AND status = 'draft';`

*Hope that helps*.
