---
layout: doc
title: Site Configuration
---

# Site Configuration

WarpSpeed uses Nginx as its web server. Phusion Passenger is used for Node, Python, and Ruby sites. PHP-FPM is used for PHP sites. Sometimes you need to configure settings within your nginx site config or maybe your php fpm pool config. WarpSpeed provides an easy way to do that without logging into your server.

To access site configuration, perform the following steps:

1. Login to your WarpSpeed account [here](https://warpspeed.io/login).
1. Access your "My Servers" dashboard and click on the "Manage" button next to the server your site is on.
1. Access your site details by clicking on the "Manage" button next to the site you want to deploy code to.
1. Click on the "Configuration" tab.

Once in the configuration section for your site, you will have options that will allow you to edit the Nginx configuration and PHP-FPM Pool configuration (if applicable). It also allows you to reload your site, which will perform a reload for Nginx and restart for your site's PHP-FPM Pool (if applicable).

After performing a "Site Reload", pay close attention to the message you receive back. If you have an error in the configuration files your server may not work properly. If you receive an error, be sure to edit your config files and then perform another "Site Reload" to verify your server is running as expected.