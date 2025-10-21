---
title: (Linux/Unix) ganzes Verzeichnis komprimieren
slug: linux-compress-directory
date_published: 2015-02-28T08:03:32.000Z
date_updated: 2018-08-22T09:37:55.000Z
tags: linux, unix, directory, compress, tar, tar.gz, zip, terminal, console, how to, howto, anleitung
---

You need to use tar command as follows (syntax of tar command):
`tar -zcvf archive-name.tar.gz directory-name`

Where,

- -z: Compress archive using gzip program
- -c: Create archive
- -v: Verbose i.e display progress while creating archive
- -f: Archive File name

For example, you have directory called /home/jerry/prog and you would like to compress this directory then you can type tar command as follows:
`$ tar -zcvf prog-1-jan-2005.tar.gz /home/jerry/prog`

Above command will create an archive file called prog-1-jan-2005.tar.gz in current directory. If you wish to restore your archive then you need to use following command (it will extract all files in current directory):
`$ tar -zxvf prog-1-jan-2005.tar.gz`

Where,

- -x: Extract files

If you wish to extract files in particular directory, for example in /tmp then you need to use following command:
`$ tar -zxvf prog-1-jan-2005.tar.gz -C /tmp $ cd /tmp $ ls -`
