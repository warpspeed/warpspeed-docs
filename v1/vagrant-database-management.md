---
layout: doc
title: Database Management for Development
---

# Database Management for Development

Database management and access in development is nearly identical to that for production. You can create databases using the `warpspeed` command or via a db client. Additionally, can only access the database from your host machine via ssh.

## Topics

- [Default database credentials.](#db-credentials)
- [Creating a new database.](#db-new)
- [Connecting to your database over SSH](#db-connect)

## <a name="db-credentials"></a> Default database credentials.

The default database credential for the development environment are:

    username: vagrant
    password: vagrant

These apply for MySQL and PostgreSQL. MongoDB does not have password authenciation by default.

## <a name="db-new"></a> Creating a new database.

WarpSpeed makes it easy to create a new MySQL or PostgreSQL database. Follow these steps:

1. First, access your virtual machine using `vagrant ssh`.
1. Once you are SSH'ed in, use the `warpspeed` command to create a new database as follows. Note: In the commands that follow, replace `db_name` with the name of the database you want to create. Replace `db_username` with the new user you want to create (this is optional). Replace `password` with the password for the new user (required if db_username is specified). All of the fields should be alphanumeric with no spaces and no special characters other than underscore.
    - MySQL: Type `warpspeed mysql:db db_name db_username password` and hit enter. If prompted, enter your database password.
    - PostgreSQL: Type `warpspeed postgres:db db_name db_username password` and hit enter. If prompted, enter your sudo password.

## <a name="db-connect"></a> Connecting to your database over SSH.

To access your database via an app on your host machine, you will need to use an SSH connection. This is so that the developemnt environment mimics the production environment as closely as possible.

To illustrate a sample connection, we will be using SequelPro. It is an outstanding free database client for MySQL databases. If you don't already have it, you can download it [here](http://www.sequelpro.com/).

Here is an example of the configuration for connecting to the WarpSpeed Vagrant VM via SSH. Note, your MySQL username and password will be `vagrant` and `vagrant` respectively. Your SSH username and password will also be `vagrant` and `vagrant`.

![](/v1/img/sequel_pro_vagrant.png)
