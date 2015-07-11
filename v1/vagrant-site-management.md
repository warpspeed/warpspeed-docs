---
layout: doc
title: Vagrant Site Management
---

# Vagrant Site Management

When you are managing your production server with WarpSpeed, you get a nice web interface. For your development server, you get the WarpSpeed CLI (Command Line Interface). This guide will give you all the information you need to create and manage sites within your development virtual machine.

## WarpSpeed CLI

To use the WarpSpeed command line interface, you first need to access your virtual machine. Do so by running the following commands within a terminal in your host environment.

```
# access the warpspeed vagrant directory
cd ~/warpspeed-vagrant

# start your virtual machine
vagrant up

# ssh into your virtual machine
vagrant ssh
```

Once you are in your virtual machine, type `warpspeed` and hit enter. You should see something similar to this:

```
Usage: warpspeed [COMMAND] [PARAMS] [OPTIONS]...
  This is the WarpSpeed.io server management utility.
  For complete information, visit: warpspeed.io.

Available commands:

  site:create [TYPE] [NAME] [OPTIONS]...
  site:remove [NAME] [OPTIONS]...
  site:reload [NAME]

  mysql:db [DBNAME] [USER] [PASS]
  mysql:backup [DBNAME]

  postgres:db [DBNAME] [USER] [PASS]
  postgres:backup [DBNAME]

  update
```

This shows all of the basic commands and how to use them, but we will describe each in more detail here.

## warpspeed site:create [TYPE] [NAME] [OPTIONS]...

This command will create a site template along with all of the necessary server configuration. The directory for the site's files will be created in the `~/Sites` directory, which will be mirrored to your virtual machines `~/sites` directory.

### TYPE

WarpSpeed supports 5 different types of sites currently:

1. html
2. node
3. php
4. python
5. ruby

Each site type requires special configuration and that is why it is necessary to provide this information to the `warpspeed` command. Please pass the site type as lower case.

### NAME

The site should be named based on the domain that will be used to access the site (without the www). For example, if your domain is `awesome.com`, the site name would be `awesome.com`. For the case of development, it is common to replace the `.com` (or other TLD) with `.dev`. So that would make the site name `awesome.dev`.

### OPTIONS

The following options are available to the `site:create` command.

```
--force     # This will overwrite the current configuration for the site if it already exists.
            # This is useful to create server configuration files for an existing site.

--push      # This creates a git repo for push deploy and should only be used for the production server.

--wildcard  # This will allow all subdomains of this domain to be redirected to this site.
            # For instance: test1.domain.com, test2.domain.com, ... could all point to `domain.com`.
```

## warpspeed site:remove [NAME] [OPTIONS]...

This command will remove the configuration for a site, and optionally remove all the site files as well.

### NAME

This is the name of the directory for the site within the `~/sites` folder and is the same as the name you specified in the `site:create` command.

### OPTIONS

```
--all       # This will remove the entire site directory. Use caution, there is no undo!
```

## warpspeed site:reload [NAME]

This command will restart nginx and passenger or php (if necessary). This command is the equivalent of:

```
sudo service nginx reload
touch ~/sites/site.dev/tmp/restart.txt

### OR ###

sudo service nginx reload
sudo service php5-fpm-site.dev restart
```

### NAME

This is the name of the directory for the site within the `~/sites` folder and is the same as the name you specified in the `site:create` command.

## Site Configuration Files and Logs

If you need to edit site configuration files or access logs, you can find them in the following locations:

```
# nginx configuration (main)
/etc/nginx/nginx.conf

# nginx configuration (per-site)
# site env config can go here
/etc/nginx/sites-available/site.dev

# nginx log (main)
# passenger logs will end up here too
/var/log/nginx/error.log

# nginx log (per-site)
/var/log/nginx/site.dev-error.log

# php.ini
/etc/php5/fpm/php.ini

# php fpm pool (per-site)
# site env config can go here
/etc/php5/fpm# cd pool.d/site.dev.conf

# php log (per-site)
/var/log/php/php-fpm-site.dev.log
```

Many of these files need elevated permission for access or editing. You can use `sudo` for individual commands or `sudo -i` to become the root user (use caution).
