---
layout: doc
title: Introduction
disqus: false
---

# WarpSpeed v1 Docs

Thanks for using WarpSpeed. The articles and screencasts on this site will help you learn how to use WarpSpeed to quickly and easily provision servers and deploy your code.

This site is hosted on [GitHub](https://github.com/warpspeed/warpspeed-docs). If you find any issues or see areas that are lacking, we would appreciate your contributions to help the WarpSpeed community.

<video src="http://warpspeedio.s3.amazonaws.com/intro.mp4" controls preload="auto" height="auto"></video>

### What is WarpSpeed?

WarpSpeed is a server management tool that makes it easy to provision new servers, create sites, and deploy your code. We believe that WarpSpeed solves 80%+ of web deployment use cases. It also helps encourage best practices including version control with Git, Git deployment, and matching your development environment with your production environment. WarpSpeed was developed out of a need that wasn't being met by other available solutions.

### What Programming Languages are Supported?

WarpSpeed supports the following:

1. Static HTML
1. JavaScript via NodeJS
1. PHP
1. Python
1. Ruby

One of the great things about WarpSpeed is that you can use all of these different languages together on one server in harmony.

### How is my Server Hosted?

WarpSpeed is a bring-your-own-host server management tool. Currently, [Digital Ocean](https://www.digitalocean.com/?refcode=e8387d479043) or [Linode](https://www.linode.com/?r=bed2c06e157de72a8f97d0c7035069800c9b342b) are supported.

All of your hosting fees are paid directly to your server host. WarpSpeed just makes it easy to manage the provisioning of servers, the creation of sites, and the deployment of your code. All WarpSpeed servers start out with base Ubuntu 14.04 install, as provided by your host, and then the WarpSpeed provisioning scripts are run on the base image.

### Why don't I use the pre-configured images my host provides?

First of all, know that it is in your hosts best interest for you to have one server per site you deploy. You want a ghost blog, use a new image. Want to run wordpress, use a new image. Want to host your ruby project, yet another server. This is seriously a total waste. Shared hosting providers put hundreds of sites on a server that looks much like your VPS. Also, think about some of these things...

1. Do you know the details of how the image was configured? Is it secure? Do you know that is wasn't created by an intern? WarpSpeed provides complete visibility via its open source scripts. Years of work and studying of best practices have gone into the WarpSpeed scripts.
1. Do you develop in more than one language? Good luck finding an image that will allow you to host different technologies together.
1. Do you need to set up SSL, or configure your firewall, or modify your site config? Time to start searching for another tutorial. We've been there, and that is why WarpSpeed exists.

### Who should use WarpSpeed?

Any software developer that is hosting personal or small business websites in HTML, Node, PHP, Python, or Ruby can streamline their development and deployment process by using WarpSpeed. We believe that WarpSpeed will meet the needs of 80%+ of web deployment use cases.

### Who shouldn't use WarpSpeed?

WarpSpeed certainly isn't a fit for all deployment scenarios. If you are developing a site that is expecting huge amounts of traffic, you need to scale quickly, or you have 99.99% uptime requirements then WarpSpeed is not the right choice. You will likely need load balancers, many redundant servers, elastic cloud resources, etc. WarpSpeed simply isn't designed to handle these types of sites, and in our calculations, these cases account for less than 20% deployment scenarios. However, if you have a small to medium site that you would like to grow into something great, WarpSpeed can be a great start that will help you keep more money in your bank account.

### How is my Server being configured?

One of the very best things about WarpSpeed is that all the provisioning and deployment scripts are [open source](https://github.com/warpspeed). This is also a huge differentiator since most of our competitors keep their scripts private. We prefer to provide a transparent service  that is affordable and saves you a lot of time.

All of the scripts are written in Bash and have been organized and templated carefully. We have done our best to attain the best compromise between locking down your server and still making things usable. Please check out the scripts and feel free to make suggestion if you think we can do better.
