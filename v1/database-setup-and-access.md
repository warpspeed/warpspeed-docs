---
layout: doc
title: Database Setup and Access
---

# Database Setup and Access

This section will help you configure and access your databases with WarpSpeed.

## Topics

- [Default database credentials.](#db-credentials)
- [Creating a new database.](#db-create)
- [Connecting to your database over SSH](#api-key-do)

## <a name="db-credentials"></a> Default database credentials.

The WarpSpeed provisioner automatically configures your database credentials. The username default username for production servers is `warpspeed` and the database password will be emailed to you.

## <a name="db-new"></a> Creating a new database.

WarpSpeed makes it easy to create a new MySQL or PostgreSQL database. Follow these steps:

1. SSH into your server by entering `ssh warpspeed@your-server-ip-address` in a terminal.
1. Once you are SSH'ed in, use the `warpspeed` command to create a new database as follows. Note: In the commands that follow, replace `db_name` with the name of the database you want to create. Replace `db_username` with the new user you want to create (this is optional). Replace `password` with the password for the new user (required if db_username is specified). All of the fields should be alphanumeric with no spaces and no special characters other than underscore.
	- MySQL: Type `warpspeed mysql:db db_name db_username password` and hit enter. If prompted, enter your database password.
	- PostgreSQL: Type `warpspeed postgres:db db_name db_username password` and hit enter. If prompted, enter your sudo password.

## <a name="db-create"></a> Connecting to your database over SSH.

Since WarpSpeed locks down your server so that only the SSH, HTTP, and HTTPS ports are open, you will not be able to access your database directly from outside the server. However, you can use SSH tunneling through most database access tools to connect to your database.

To illustrate this configuration, we will be using SequelPro. It is an outstanding free database client for MySQL databases. If you don't already have it, you can download it [here](http://www.sequelpro.com/).

Here is an example of the configuration for connecting to a WarpSpeed production server over SSH. Note, your MySQL username will be `warpspeed` and the database password will be the one that was emailed to you after server creation. Your SSH username and password will be `warpspeed` and the SSH password should be left blank because it will use your SSH key.

![](/v1/img/sequel_pro_production.png)
