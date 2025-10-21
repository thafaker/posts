---
title: Set up your own Email server on Ubuntu 22.04
slug: set-up-your-own-email-server-on-ubuntu-22-04
date_published: 1970-01-01T00:00:00.000Z
date_updated: 2024-02-27T12:16:01.000Z
tags: anleitung, howto, how to, ubuntu, linux
draft: true
---

This article aims to set up an Email server on Ubuntu 22.04 ([Jammy](https://releases.ubuntu.com/jammy/)). Please note that this article may gloss over some details or some information. **Please note**– that setting up a custom mail server depends on your use case and this article will only go through the details which will help you set up simple sending/receiving functionality. 

This article will also go through the details of setting up an Email Server with [SPF](https://www.cloudflare.com/learning/dns/dns-records/dns-spf-record/) records, [DKIM](https://www.cloudflare.com/learning/dns/dns-records/dns-dkim-record/#:~:text=A%20DKIM%20record%20is%20a,to%20verify%20an%20email's%20authenticity.), [Catch-All Email](https://web.archive.org/web/20230701150544/http://wiki.metawerx.net/wiki/CatchAllEmailAddress#:~:text=A%20catch%2Dall%20mail%20address%20is%20a%20special%20email%20address%20at%20your%20domain%20name%20that%20catches%20all%20email%20for%20undefined%20email%20addresses.) accounts, Virtual Mail Box domains, Email accounts, [DMARC](https://en.wikipedia.org/wiki/DMARC), and [Webmail](https://en.wikipedia.org/wiki/Webmail).

### **Before you get started**

Before we get started, We expect you to have a basic understanding of [common Linux Utilities](https://www.hostinger.com/tutorials/linux-commands), additionally, please ensure that the following ports are open and not blocked by any firewall.
PortInfo25SMTP80HTTP110POP3143IMAP443HTTPS465SMTPS587Secure SMTP993Secure IMAP995Secure POP3
ports for email server & webmail

### Prerequisites

- A machine facing the internet (I used [Vultr](https://www.vultr.com/))
- Ubuntu 22.04 instance
- General know-how in operating Linux Systems
- Domain (I will be using **`dinge-vernetzt.de`**) 
- General know-how in adding DNS records (I used [Cloudflare](https://cloudflare.com/))

### Generating SSL Certificate

We will be using an SSL certificate issued by [Certbot](https://certbot.eff.org/) so that the mail gets encrypted in transit. To do this, first, install Certbot using the following command:

    sudo apt install -y certbot

After it has been installed, run the following command to issue a certificate for your domain, make sure to replace **`your_domain`** with your domain name:

    sudo certbot certonly --manual --preferred-challenges dns -d your_domain

It should then ask for an email, put in your email, accept the terms and conditions, and continue. Then, it should display the DNS records you must add to your domain like in the screenshot below.
![](https://cdn.rafled.com/aih/wp-content/uploads/2023/07/03033521/image-4.png)
Add your DNS records and continue. Then, it should successfully generate the certificate and you should get a response similar to this:
![](https://cdn.rafled.com/aih/wp-content/uploads/2023/07/03033732/image-5-1024x365.png)
### Setting up Postfix

Install Postfix using the following command:

    sudo apt install -y postfix

You will get a TUI similar to this:
![](https://cdn.rafled.com/aih/wp-content/uploads/2023/07/01155300/image-1024x497.png)
Ensure that it is selected on the **`Internet Site`** option and press Enter.

You will then be prompted to enter the “System mail name”. In there, you will put your domain name like in the screenshot below, and press Enter.
![](https://cdn.rafled.com/aih/wp-content/uploads/2023/07/01155808/image-1-1024x509.png)
It should continue the installation process…
![](https://cdn.rafled.com/aih/wp-content/uploads/2023/07/01160410/image-2-1024x502.png)
First, backup the original Postfix file using the following command:

    sudo mv /etc/postfix/main.cf /etc/postfix/main.cf.bak

Then, create a new Postfix file and paste the following contents. Make sure to replace my_domain with your domain name.

    sudo nano /etc/postfix/main.cf

    smtpd_banner = $myhostname ESMTP my_domain
    biff = no
    append_dot_mydomain = no
    readme_directory = no
    
    # TLS parameters
    smtp_use_tls = yes
    smtp_tls_security_level = may
    smtp_tls_session_cache_database = btree:${data_directory}/smtp_scache
    
    smtpd_tls_auth_only = yes
    smtpd_tls_received_header = no
    smtpd_tls_session_cache_timeout = 3600s
    smtpd_use_tls = yes
    smtpd_tls_security_level = may
    smtpd_tls_session_cache_database = btree:${data_directory}/smtpd_scache
    smtpd_tls_cert_file = /etc/letsencrypt/live/my_domain/fullchain.pem
    smtpd_tls_key_file = /etc/letsencrypt/live/my_domain/privkey.pem
    smtpd_relay_restrictions = permit_mynetworks, permit_sasl_authenticated,  reject_unauth_destination
    
    smtpd_sasl_auth_enable = yes
    smtpd_sasl_type = dovecot
    smtpd_sasl_path = private/auth
    
    virtual_transport = lmtp:unix:private/dovecot-lmtp
    virtual_mailbox_domains = /etc/postfix/virtual_mailbox_domains
    
    myhostname = mail.my_domain
    myorigin = /etc/mailname
    message_size_limit = 50000000
    mydestination = localhost.$mydomain, localhost
    relayhost =
    mynetworks = 127.0.0.0/8 [::ffff:127.0.0.0]/104 [::1]/128
    mailbox_size_limit = 0
    recipient_delimiter = +
    inet_interfaces = all
    inet_protocols = all
    alias_maps = hash:/etc/aliases
    alias_database = hash:/etc/aliases
    virtual_alias_maps = hash:/etc/postfix/virtual
    
    milter_default_action = accept
    milter_protocol = 6
    smtpd_milters = inet:127.0.0.1:8892
    non_smtpd_milters = $smtpd_milters
    
    policyd-spf_time_limit = 3600
    smtpd_recipient_restrictions =
       permit_mynetworks,
       permit_sasl_authenticated,
       reject_unauth_destination,
       check_policy_service unix:private/policyd-spf

Then, save and close the file.

#### Creating a Virtual Mail Box Domain

Line 26 of Postfix instructs Postfix to look for a file for Virtual Mailbox domains, which will allow you to create email accounts without having to create a Unix account. You may learn more about this [here](https://www.postfix.org/ADDRESS_CLASS_README.html#virtual_mailbox_class). 
Create the file using the following command:

    sudo nano /etc/postfix/virtual_mailbox_domains

In the file, put the following contents and replace my_domain with your domain name and save and exit.

    my_domain #domain

Now, run the following command to change the file format recognizable by Postfix. You will have to run this command every time you make any changes to the **`/etc/postfix/virtual_mailbox_domains`** file.

    sudo postmap /etc/postfix/virtual_mailbox_domains

#### Editing Postfix master file

Now, we will be editing the master file which will enable SMTP service, make sure to preserve the formatting in this file as a formatting issue may also cause the config to not work.

Find the line with the following content:

    smtp      inet  n       -       y       -       -       smtpd

We will be adding a Spamassassin filter (even though we haven’t set it up yet). It will ensure that every incoming mail will go through the spam filter and add spam headers. Add this right after that line:

       -o content_filter=spamassassin
    spamassassin unix -     n       n       -       -       pipe
       user=spamd argv=/usr/bin/spamc -f -e
       /usr/sbin/sendmail -oi -f ${sender} ${recipient}

After that in a new line, add the following content:

    submission inet n       -       y       -       -       smtpd
    smtps      inet  n       -       y       -       -       smtpd
      -o syslog_name=postfix/submission
      -o smtpd_tls_security_level=encrypt
      -o smtpd_sasl_auth_enable=yes

And at the end of the file, add the following content:

    policyd-spf  unix  -       n       n       -       0       spawn
        user=policyd-spf argv=/usr/bin/policyd-spf

Finally, save and close the file.

### Setting up Dovecot

Install Dovecot and the dependencies required to run IMAP, POP3, and LMTP service using the following command.

    sudo apt install -y dovecot-core dovecot-imapd dovecot-pop3d dovecot-lmtpd

After the installation has been completed, edit the following file:

    sudo nano /etc/dovecot/conf.d/10-mail.conf

Look for the following line:

    mail_location = mbox:~/mail:INBOX=/var/mail/%u

and change the line to:

    mail_location = maildir:/var/mail/vhosts/%d/%n

Save and close the file. 
The **`%d`** represents the domain name and **`%n`** represents the users. So, now we will have to create a directory for the domain. This will be applicable for every new domain you add to your server.

Create a directory and replace `my_domain` with your domain name:

    sudo mkdir -p /var/mail/vhosts/my_domain

#### Creating virtual user & group for Dovecot

Once that’s done, we will now create a virtual mail user and group for the Dovecot service.

First, create the vmail group

    sudo groupadd -g 5000 vmail

Then, create the vmail user and add the user to the vmail group

    sudo useradd -r -g vmail -u 5000 vmail -d /var/mail/vhosts -c "Virtual Mail User"

Then, change the ownership of the vhosts directory to the vmail user and group.

    sudo chown -R vmail:vmail /var/mail/vhosts/

#### Editing Dovecot Master configuration

Once you are done with that, we will now edit the Dovecot Master configuration. To do that, open the master file using the following command:

    sudo nano /etc/dovecot/conf.d/10-master.conf

In the file, find the following lines and uncomment them (remove the hashtag symbol)

      inet_listener imaps {
        #port = 993
        #ssl = yes
      }

      inet_listener pop3s {
        #port = 995
        #ssl = yes
      }

Find this line:

    service lmtp {
      unix_listener lmtp {
        #mode = 0666
      }
    
      # Create inet listener only if you can't use the above UNIX socket
      #inet_listener lmtp {
        # Avoid making LMTP visible for the entire internet
        #address =
        #port =
      #}
    }

and replace it with:

    service lmtp {
    unix_listener /var/spool/postfix/private/dovecot-lmtp {
        mode = 0600
        user = postfix
        group = postfix
      }
    }

Find this line:

      # Postfix smtp-auth
      #unix_listener /var/spool/postfix/private/auth {
      #  mode = 0666
      #}

replace it with:

    unix_listener /var/spool/postfix/private/auth {
      mode = 0666
      user = postfix
      group = postfix
    }

Then finally, save and close the file.

#### Setting up Dovecot Authentication

Note: We will be using basic text authentication in Dovecot. But will be using SSL/TLS.

First, we will configure Dovecot to use secure authentication. To do so, open the following file:

    sudo nano /etc/dovecot/conf.d/10-auth.conf

Uncomment the following line by removing the hashtag symbol.

    #disable_plaintext_auth = yes

Find the entry below

    auth_mechanisms = plain

Then, change the authentication from **`plain`** to **`plain login`**.

    auth_mechanisms = plain login

Disable the default Dovecot authentication behavior which requires the user to have a UNIX account. Find the following line:

    !include auth-system.conf.ext

Add the pound symbol to comment it out:

    # !include auth-system.conf.ext

Then, find the following line:

    #!include auth-passwdfile.conf.ext

and uncomment it by removing the hashtag symbol

    !include auth-passwdfile.conf.ext

Finally, Save and Exit the file.

#### Setting up Dovecot User DB

**Note**: For the sake of simplicity, we will be using a simple text-based file for storing users’ email & password. You may use a database system like the one used in [ArchWiki](https://wiki.archlinux.org/title/Virtual_user_mail_system_with_Postfix,_Dovecot_and_Roundcube).

Edit the Dovecot Password file, to do this, open the file using the following command:

    sudo nano /etc/dovecot/conf.d/auth-passwdfile.conf.ext

The original file should look like this:

    # Authentication for passwd-file users. Included from 10-auth.conf.
    #
    # passwd-like file with specified location.
    # <doc/wiki/AuthDatabase.PasswdFile.txt>
    
    passdb {
      driver = passwd-file
      args = scheme=CRYPT username_format=%u /etc/dovecot/users
    }
    
    userdb {
      driver = passwd-file
      args = username_format=%u /etc/dovecot/users
    
      # Default fields that can be overridden by passwd-file
      #default_fields = quota_rule=*:storage=1G
    
      # Override fields from passwd-file
      #override_fields = home=/home/virtual/%u
    }

Make the following edits to the file:

    # Authentication for passwd-file users. Included from 10-auth.conf.
    #
    # passwd-like file with specified location.
    # <doc/wiki/AuthDatabase.PasswdFile.txt>
    
    passdb {
        driver = passwd-file
        args = scheme=PLAIN username_format=%u /etc/dovecot/dovecot-users
    }
    
    userdb {
        driver = static
        args = uid=vmail gid=vmail home=/var/mail/vhosts/%d/%n
      # Default fields that can be overridden by passwd-file
      #default_fields = quota_rule=*:storage=1G
    
      # Override fields from passwd-file
      #override_fields = home=/home/virtual/%u
    }

Save and close the file.

#### Creating Email (Dovecot) Users

Once you have completed the previous process, create the Dovecot users file which holds the Usernames and Passwords. Run the following command to create and edit the Dovecot user file.

    sudo nano /etc/dovecot/dovecot-users

Add the users you want using the following format, make sure to replace `your_domain` and `your_password` with the one you use. You can add as many users as you want using the following format.

    admin@your_domain:{plain}your_password
    info@your_domain:{plain}your_password
    ...

![example of dovecot user db](https://cdn.rafled.com/aih/wp-content/uploads/2023/07/03091328/image-6-1024x532.png)
Save and Close the file.

#### Setting Dovecot for SSL Authentication

To configure Dovecot to use SSL, edit the following file:

    sudo nano /etc/dovecot/conf.d/10-ssl.conf

Find the line:

    ssl = yes

Change to:

    ssl = required

Find the lines:

    ssl_cert = </etc/dovecot/private/dovecot.pem
    ssl_key = </etc/dovecot/private/dovecot.key

Make sure you replace `my_domain` with your domain name. Change to:

    ssl_cert = </etc/letsencrypt/live/my_domain/fullchain.pem
    
    ssl_key = </etc/letsencrypt/live/my_domain/privkey.pem

Then, save and close the file.

#### Setting Up Catch-All Email Accounts

Note: Because we have already added the line for Virtual Accounts in Postfix, we will not have to make any additional changes. 
If you do not want a Catch-All account, you will have to remove the line **`virtual_alias_maps = hash:/etc/postfix/virtual`** from **/etc/postfix/main.cf**. You may then skip this part.

To set up, Catch-All Email Account, you will have to run the following command to create a file with user mapping:

    sudo nano /etc/postfix/virtual

Then in the file contents, make sure to replace my_domain with your domain name and use the following format. Make sure you replace `catchall` it with the email address you want to use. 
Make sure that the email account is already created in **`/etc/dovecot/dovecot-users`** file.

    @my_domain catchall

In the above format, it will forward all emails which are addressed to the ones without an account to `**catchall@my_domain**`. 
For example, if an email is sent to `foo@dinge-vernetzt.de` but it does not exist then the email will be sent to `catchall@dinge-vernetzt.de`.

Additionally, if you want to forward emails from multiple specific addresses to a single email address you can do so with the following format:

    administrator@my_domain admin
    webmaster@my_domain admin

In the above format, it will “catch” the emails addressed to `admin@my_domain` and `webmaster@my_domain` and send it to `admin@my_domain`

After you are done, save and close the file. Then, finally, run the following command to update the Postfix database. 
**Note**: You will need to run the following command every time you update the virtual mapping.

    sudo postmap /etc/postfix/virtual

### Setting Up SpamAssassin

Install SpamAssassin using the following command.

    sudo apt-get install spamassassin spamc -y

After it completes installing, add a SpamAssassin user using the following command. Just press the `Enter `key on any information which has been asked.

    sudo adduser spamd --disabled-login

#### Configuring SpamAssassin

To assign the user and edit the config, run the following command:

    sudo nano /etc/default/spamassassin

Find the line:

    OPTIONS="--create-prefs --max-children 5 --helper-home-dir"

Replace it with:

    OPTIONS="–create-prefs –max-children 5 –username spamd –helper-home-dir /home/spamd/ -s /home/spamd/spamd.log"

Find the line:

    CRON=0

Change to:

    CRON=1

After you made the changes, Save and Close the file.

Now, you will have to make the backup of the SpamAssassin local configuration file. Execute the following command:

    sudo mv /etc/spamassassin/local.cf  /etc/spamassassin/local.cf.bk

Then, create a new local file using the following command:

    sudo nano /etc/spamassassin/local.cf 

Paste the following contents into the file:

    rewrite_header Subject ***** SPAM _SCORE_ *****
    report_safe             0
    required_score          5.0
    use_bayes               1
    use_bayes_rules         1
    bayes_auto_learn        1
    skip_rbl_checks         0
    use_razor2              0
    use_pyzor               0
    ifplugin Mail::SpamAssassin::Plugin::Shortcircuit
    endif

Save and Exit the file.

### Checking SPF on incoming mail

We need to ensure we do not get any forged emails, to check that, install the following package

    sudo apt install -y postfix-policyd-spf-python

### Setting Up & Generating DKIM Keys

Install the required packages to set up DKIM:

    sudo apt install -y opendkim opendkim-tools

First, set the **`DOMAIN`** variable in the terminal using the following command. Make sure to replace my_domain with your domain name.

    DOMAIN=my_domain

Then, open the OpenDKIM configuration file using the following command:

    sudo nano /etc/opendkim.conf

Find the following lines and uncomment them (remove the pound symbol):

    #Mode                   sv
    #SubDomains         no

Add the following lines after SubDomains

    AutoRestart         yes
    AutoRestartRate     10/1M
    Background          yes
    DNSTimeout          5
    SignatureAlgorithm  rsa-sha256

Then, add the following lines at the end of the file:

    KeyTable           refile:/etc/opendkim/key.table
    SigningTable       refile:/etc/opendkim/signing.table
    ExternalIgnoreList  /etc/opendkim/trusted.hosts
    InternalHosts       /etc/opendkim/trusted.hosts

Find the line with the content:

    Socket                  local:/run/opendkim/opendkim.sock

And replace it with:

    Socket                  inet:8892@localhost

Save and Close the file.

Create the required directories & change permissions using the following commands:

    sudo mkdir /etc/opendkim
    sudo mkdir /etc/opendkim/keys
    
    sudo chown -R opendkim:opendkim /etc/opendkim
    sudo chmod go-rw /etc/opendkim/keys

Then create the signing table using the following command:

    sudo echo "*@$DOMAIN    default._domainkey.$DOMAIN
    *@*.$DOMAIN    default._domainkey.$DOMAIN" > /etc/opendkim/signing.table

After that, create the key table using the following command:

    sudo echo "default._domainkey.$DOMAIN    $DOMAIN:default:/etc/opendkim/keys/$DOMAIN/default.private" > /etc/opendkim/key.table

Next up, is the trusted hosts file:

    sudo echo "127.0.0.1
    localhost
    
    .$DOMAIN" > /etc/opendkim/trusted.hosts

Now, We will generate the Keys. Create a directory for the domain using the following command:

    sudo mkdir /etc/opendkim/keys/$DOMAIN

Then, we will generate the keys themselves using the following command:

    sudo opendkim-genkey -b 2048 -d $DOMAIN -D /etc/opendkim/keys/$DOMAIN -s default -v

Then, set permissions for the key files using the following commands:

    sudo chown opendkim:opendkim /etc/opendkim/keys/$DOMAIN/default.private
    sudo chmod 600 /etc/opendkim/keys/$DOMAIN/default.private

### Setting Up SPF, DKIM, MX, and other DNS Records

First, Login to your DNS Registrar.

#### A Records

First, we will have to add **A record** for the mail server. Put the Name **`mail`**and put the IPv4 Address for your server. Here’s an example of the configuration I used on Cloudflare. 
![](https://cdn.rafled.com/aih/wp-content/uploads/2023/07/03124812/image-9-1024x325.png)

**Note:** If you are using Cloudflare, disable proxy on the record because you will not be able to access the ports when you use your domain name for SMTP or any port.

**Note**: If you have AAAA Records, you should add that too.

#### MX Record

Then, add the **MX record**. Put the Name as **`mail`**, mail server as **`mail.my_domain`** (replace my_domain with your domain), and put priority at **10**. Here’s an example of the configuration I used on Cloudflare.
![](https://cdn.rafled.com/aih/wp-content/uploads/2023/07/03125309/image-10-1024x327.png)
#### SPF Record

You may use an [SPF Generator](https://mxtoolbox.com/SPFRecordGenerator.aspx) if you want to generate one or you can use the following format. Add a **TXT Record** with your domain as a name and make sure to replace `my_ipv4` with your Mail server IPv4 address. 

If you have IPv6 Address, you will have to add **`ip6:your_ipv6`** after **`ip4`**

    v=spf1 mx ip4:my_ipv4 -all

Here’s an example:
![](https://cdn.rafled.com/aih/wp-content/uploads/2023/07/03130152/image-11-1024x413.png)
#### DMARC Record

To add DMARC Record, Add a **TXT Record** and put the Name as **`_dmarc`** , and use the following format make sure to use your email.

    v=DMARC1; p=reject; pct=100; fo=1; rua=mailto:admin@my_domain

Here’s an example:
![](https://cdn.rafled.com/aih/wp-content/uploads/2023/07/03130840/image-12-1024x356.png)
#### DKIM Record

To add DKIM Record, Add a **TXT Record** and put the name as `**default._domainkey**`. In the `/etc/opendkim/keys/your_domain`directory, there should be a file called `default.txt`, view the contents using the following command and make sure to remove any spaces and double quotes.

    cat mail.txt

For example:
![](https://cdn.rafled.com/aih/wp-content/uploads/2023/07/03181917/image-19-1024x137.png)
When adding to Cloudflare:
![](https://cdn.rafled.com/aih/wp-content/uploads/2023/07/03182026/image-20-1024x411.png)
### Finalizing & Restarting Services

We have finally completed setting up the services necessary for an email server, now, we will execute the following commands to enable services at boot & restart services where we had changed configurations.

Restart Postfix:

    sudo systemctl restart postfix

Restart Dovecot:

    sudo systemctl restart dovecot

Enable & Start SpamAssassin:

    sudo systemctl enable --now spamassassin

Restart OpenDKIM:

    sudo systemctl restart opendkim

### Installing WebMail

As for our WebMail, there are a wide array of choices we can choose from but, I prefer [SnappyMail](https://snappymail.eu/). You may use your own WebMail client like RoundCube, etc.

I will be using [NGINX](https://nginx.org/en/) as a web server, but feel free to choose your own WebServer.

#### Install Nginx

    sudo apt install -y nginx

#### Add PHP Repository & Install dependencies:

    sudo apt-add-repository ppa:ondrej/php

    sudo apt install -y php8.2-{fpm,mbstring,xml,curl,exif,gd,gnupg,imagick,intl,ldap,zip}

#### Setup Directory

Create a directory for webmail & switch to the root user

    sudo mkdir /var/www/mail && sudo bash

Navigate to the directory

    cd /var/www/mail

#### Setup SnappyMail

Run the following commands to download the SnappyMail release and extract it

    wget https://github.com/the-djmaze/snappymail/releases/download/v2.28.3/snappymail-2.28.3.tar.gz
    
    tar -xvf snappymail-*.tar.gz

Change permissions of the folder

    find . -type d -exec chmod 755 {} \;
    find . -type f -exec chmod 644 {} \;
    chown -R www-data:www-data .

#### Setup NGINX vhost

To setup NGINX vhost, first create a file using the following command:

    sudo nano /etc/nginx/sites-enabled/mail

And paste the following content: Replace my_domain with your domain name

    server {
            listen 80;
            listen [::]:80;
    
            root /var/www/mail;
    
            index index.php;
    
            server_name mail.my_domain;
    
            location / {
                    try_files $uri $uri/ =404;
            }
    
            location ~ \.php$ {
                    include snippets/fastcgi-php.conf;
                    fastcgi_pass unix:/run/php/php8.2-fpm.sock;
            }
    }

Here’s an example:
![](https://cdn.rafled.com/aih/wp-content/uploads/2023/07/03150322/image-15-1024x549.png)
Then, restart the following services:

    sudo systemctl restart nginx

#### Generate SSL for webmail

Get the certbot nginx plugin to get SSL 

    sudo apt install python3-certbot-nginx

To generate SSL, replace my_domain with your domain name and run the following command:

    sudo certbot --nginx -d mail.my_domain

#### Accessing & Setting up WebMail Admin

Now, go to `https://mail.my_domain/?admin` after replacing my_domain with your domain. 
This will generate the unique password file for which you will be able to log in to the admin interface. 

Run the following command to get your password:

    sudo cat /var/www/mail/data/_data_/_default_/admin_password.txt

The password should be shown in your terminal, copy it and log in using the password on the admin screen. The username is “admin”.

When you log in using the password that was just generated, it will show a banner asking you to change the password, you must change the password to a secure one. An example of the banner is shown below.
![](https://cdn.rafled.com/aih/wp-content/uploads/2023/07/03155012/image-17-1024x636.png)
Select “**Domains**” from the sidebar and click on click on “Add domain”. In the Name field, add your domain name, in the IMAP server input, use **`localhost`**, Secure: **`SSL/TLS`**, Port: **`993`**. In the SMTP server input, use **localhost**, Secure: **None**, Port: **`25`**. Deselect `**Use Authentication**` and select `Use **Login as Sender**`. Finally, click on save.

Note: You may choose secure ports also.

Remove any of these un-needed domains
![](https://cdn.rafled.com/aih/wp-content/uploads/2023/07/03155939/image-18.png)
You may customize the WebMail to your liking.

### Logging in & Sending Emails

After you are done with your customization, you may log in to WebMail. Go to `mail.my_domain` and log in with the email and password you set while creating Dovecot Accounts.

You may now send a Test Email using your mail server
![sending from custom email server webmail](https://cdn.rafled.com/aih/wp-content/uploads/2023/07/03182236/image-21.png)![receiving email from custom email server](https://cdn.rafled.com/aih/wp-content/uploads/2023/07/03182338/image-22.png)
If you have any suggestions or want to give any feedback please do so in the comments below 👇.

July 3, 2023

By

[admin](https://www.aih.app/author/admin/)

[General](https://www.aih.app/category/general/)[Tech](https://www.aih.app/category/tech/)[dovecot](https://www.aih.app/tag/dovecot/)[email](https://www.aih.app/tag/email/)[mail server](https://www.aih.app/tag/mail-server/)[postfix](https://www.aih.app/tag/postfix/)[self hosted](https://www.aih.app/tag/self-hosted/)[snappymail](https://www.aih.app/tag/snappymail/)[spamassassin](https://www.aih.app/tag/spamassassin/)[ubuntu](https://www.aih.app/tag/ubuntu/)[vps](https://www.aih.app/tag/vps/)

---

### Related Posts:

- [Setting up Hurricane Electric IPv6 on Ubuntu 22.04](https://www.aih.app/2022/10/17/setting-up-hurricane-electric-ipv6-on-ubuntu-22-04/)
- [Installing Windows 11 Pro on Vultr](https://www.aih.app/2023/02/24/installing-windows-11-pro-on-vultr/)
- [Setup IPv6 on Ubuntu 22.04 on Oracle Cloud](https://www.aih.app/2023/04/15/setup-ipv6-on-ubuntu-22-04-on-oracle-cloud/)
- [Use OpenVPN on a Secondary OpenWRT router](https://www.aih.app/2023/04/28/use-openvpn-on-a-secondary-openwrt-router/)

---

## aih.app

A [rafled.com](https://rafled.com/) subsidiary, © 2022 – Current
![](https://www.gstatic.com/adsense/autoads/icons/gpp_good_24px_blue_600.svg)
**Einstellungen für Datenschutz und Cookies**Von Google verwaltet. Entspricht dem IAB-TCF. CMP-ID: 300
