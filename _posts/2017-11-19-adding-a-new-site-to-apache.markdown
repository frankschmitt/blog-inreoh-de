---
layout: post
title:  "Cheatsheet: Adding a new webapp to Apache"
date:   2017-11-19 17:46:13 +0100
categories: apache webapp
---
# Basic config (as root)
- create a new user
useradd <app>\_user 

- copy your app to /var/www
cp myapp /var/www

- set the owner
chown -r <app>\_user.<app>\_user /var/www/myapp

- update Apache config
vim /etc/apache2/sites-available/<app>.conf
cd /etc/apache2/sites-enabled && ln -s ../sites-available/<app>.conf

- update SSL certificates
certbot -apache 


