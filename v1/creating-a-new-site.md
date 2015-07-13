---
layout: doc
title: Creating a New Site
---

# Creating a New Site

Follow the instructions below to create a new site on one of your WarpSpeed servers. You can create multiple sites on each server (as many as the server can handle), and each site can utilize a different supported hosting technology (HTML, Node, PHP, Python, Ruby). This makes hosting many sites very economical.

<video src="http://warpspeedio.s3.amazonaws.com/ws_site_create.mp4" controls preload="auto" height="auto"></video>

1. Login to your WarpSpeed account [here](https://warpspeed.io/login).
1. Access your "My Servers" dashboard and click on the "Manage" button next to the server you want to create the site on. You will be brought to your server's sites page and you will see something like this:

	![](/v1/img/create_site.png)

1. Enter the domain name you plan to use with your site. Do not include the "www". If you are hosting just a single subdomain, you can enter that here. Ex: "app.myawesomedomain.com".
1. Select a site type. This will affect how the server gets configured so it is important that this matches the technology your site uses. The options are: HTML, Node JS, PHP, Python, and Ruby.
1. Select any additional options. Currently, you have a choice of "Allow wildcard subdmomains". This means that if you enter "myawesomedomain.com" as your domain name, any subdomain such as "sub1.myawesomedomain.com" or "sub2.myawesomedomain.com" will be served by this site.
1. Verify your inputs and click the "Add Site" button. The site will be created immediately and will then appear under the "Configured Sites" section.
