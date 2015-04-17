---
layout: doc
title: Firewall Management
---

# Firewall Management

By default, WarpSpeed sets up a restrictive firewall to keep your server secure. Inbound traffic is limited to the follow:

- 22 for SSH
- 80  for HTTP
- 443 for HTTPS

No ports are open for remote database access, and it is highly recommended that you do not open any other ports unless necessary. If you would like to access your database remotely, you can do so via SSH tunneling as documented [here](/v1/database-setup-and-access).

### Manage Existing Rules

To manage existing rules for your server's firewall follow these steps:

1. Login to your WarpSpeed account [here](https://warpspeed.io/login).
1. Access your "My Servers" dashboard and click on the "Manage" button next to the server you want to create the site on.
1. Click on the "Firewall Rules" tab and you will see the following:

	![](/v1/img/firewall_management.png)

1. You can see the default ports in the "Existing Firewall Rules" section. You can delete any rule except the SSH/22 rule because without that WarpSpeed will not be able to manage your server.

### Add a New Rule

To add new rules, follow these steps:

1. Acecss the "Firewall Rules" tab of your server management page as described above.
1. Select a nickname for the rule. Generally, this should be the service you are allowing.
1. Enter the port number you want to allow.
1. Optionally, enter the IP address you want to restrict this rule to.
1. Verify you inputs and then click "Add Firewall Rules".
