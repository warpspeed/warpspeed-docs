---
layout: doc
title: Provisioning Servers
---

# Provisioning Servers

WarpSpeed makes it super easy to provision a server with just what you need. WarpSpeed currently supports Linode and Digital Ocean. If you haven't already set up your accounts and configured your <a href="/v1/api-keys">API Keys</a> within WarpSpeed, please do so before proceeding.

<video src="http://warpspeedio.s3.amazonaws.com/ws_server_create.mp4" controls preload="auto" height="auto"></video>

Follow these steps to provision a new server:

1. Login to your WarpSpeed account [here](https://warpspeed.io/login).
1. Access your "My Servers" dashboard and click the "Create Server" button and you will see a screen that looks like this:

	![](/v1/img/create_server.png)

1. A server name is auto generated, but feel free to change it. Just use alphanumeric characters with dash separators.
1. Choose a provider. The options available to you here will be based on the API Keys you have configured for your account.
1. Select the installers you would like to run.
1. Select SSH Keys to add to the server. The options availabe to you here will be based on the keys you have configured for your account. Since WarpSpeed only allows key-based authentication, you must select at least one key.
1. Choose your plan and region for your server host. The prices here are related to your configured server provider and you will be billed for hosting directly from your provider. The options available here should be the same as if you went directly to their site.
1. If you desire any additional features from your provider, select the appropriate checkboxes. It should be noted that some providers charge additional fees for certain features, such as backups. Also, all features are not available in all regions.
1. Verify all your inputs, then click the "Create Server" button. You will be able to track the status of the new server on your "My Servers" dashboard. When setup is complete (usually 5-10 minutes), you will receive an email containing the relevant login information for your server.

