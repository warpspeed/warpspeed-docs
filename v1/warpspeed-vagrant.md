---
layout: doc
title: WarpSpeed Vagrant
---

#WarpSpeed Vagrant

To streamline your development workflow, WarpSpeed provides a Vagrantfile that will set up a development environment that closely matches your production environment.

In this guide, we will be referring to the host environment and the virtual machine. The host environment is your PC or laptop. It is likely running OSX or Windows. The virtual machine is a virtual computer that runs inside your host environment. For WarpSpeed, the virtual machine runs Ubuntu 14.04 x64.

To begin, please install the prerequisites shown below.

##Prerequisites

###64 Bit Processor

WarpSpeed utilizes Ubuntu 14.04 x64 and a 64 bit processor with hardware acceleration is needed to run the WarpSpeed Vagrant environment.

###VirtualBox

VirtualBox is a cross-platform virtualization application. It's free and easy to use, and you can download it here:

[https://www.virtualbox.org/wiki/Downloads](https://www.virtualbox.org/wiki/Downloads)

###Vagrant

Vagrant is a tool that makes creating virtual environments quick and easy. Download Vagrant here:

[https://www.vagrantup.com/downloads.html](https://www.vagrantup.com/downloads.html)

###Git

Git is an outstanding and popular version control system. Download Git here:

[https://git-scm.com/downloads](https://git-scm.com/downloads)

##Downloading the WarpSpeed Vagrantfile

Once you have finished installing the prerequisites, download the WarpSpeed Vagrant project by accessing the link below and selecting "Download Zip" in the right menu.

[https://github.com/warpspeed/warpspeed-vagrant](https://github.com/warpspeed/warpspeed-vagrant)

Extract the downloaded zip file to an easy to access location, like your home directory, and rename the extracted folder to `warpspeed-vagrant`.

##Create your Sites Directory

Within your home directory, create a new directory called `Sites`. This directory will be used to store all your web projects. The `Sites` directory will also get "mirrored" to your virtual machine. By doing this, you get the best of both worlds... you can edit and version control files in your local environment and run everything inside your virtual machine.

##Swap the Vagrantfile (Windows Only)

If you are a Windows user, you need to use the `Vagrantfile-windows`. To do this, delete the `Vagrantfile` from the `warpspeed-vagrant` file and then rename `Vagrantfile-windows` to `Vagrantfile`.

##Create the Virtual Machine

Vagrant makes this part easy. Start by opening a terminal and cd'ing to the `warpspeed-vagrant` directory. Next, type `vagrant up` and vagrant will begin creating and provisioning your virtual machine.

The initial creation of the virtual machine will take some time. The entire Ubuntu 14.04 disk will need to be downloaded and then all WarpSpeed dependencies will be installed.

If you are using the NFS based Vagrantfile (Mac or Linux), you will need to enter your account password during the startup of the virtual machine.

##Accessing the Virtual Machine

To access your virtual machine, open a terminal and cd to the `warpspeed-vagrant` directory. Next, run the `vagrant ssh` command. Your virtual machine will need to be running for this to work. It you receive a message that says it isn't running, use the `vagrant up` command to start the virtual machine.

Default credentials:

```
# these are not required when using vagrant ssh, but would be required for other ssh access
username: vagrant
password: vagrant
```

##Workflow

Editing of your web app and version control tasks should all take place in your host environment. Your files should be stored in your `~/Sites` directory. Editing of web configuration and creation of databases should happen inside your virtual machine. Your web application files can be found in the `~/sites` directory inside your virtual machine.

##What's Next

Now that you have a development environment that makes it easy to develop and test your code, what's next? Well, you want to create sites and databases, and fortunately WarpSpeed makes that easy too. Please see the next section of the docs for more details.

###Useful Vagrant Commands

Here is a list of the most commonly used Vagrant commands. All of these should be run within the `~/warpspeed-vagrant` directory (where the Vagrantfile is located) in your host environment.

	cd ~/warpspeed-vagrant

	vagrant status			# outputs status of the vagrant machine
	vagrant up				# starts and provisions the vagrant environment
	vagrant ssh				# connects to machine via SSH
	vagrant suspend			# suspends the machine
	vagrant resume			# resume a suspended vagrant machine
	vagrant halt			# stops the vagrant machine
	vagrant destroy			# stops and deletes all traces of the vagrant machine
