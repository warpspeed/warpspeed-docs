---
layout: doc
title: API Keys
---

# API Keys

WarpSpeed.io uses [API Keys](http://en.wikipedia.org/wiki/Application_programming_interface_key) to access your [Digital Ocean](https://www.digitalocean.com/?refcode=e8387d479043) or [Linode](https://www.linode.com/?r=bed2c06e157de72a8f97d0c7035069800c9b342b) account to automatically create servers for you. The topics below will help you configure API Keys in your WarpSpeed.io account.

## Topics

- [Obtaining an API key for your Digital Ocean account.](#api-key-do)
- [Obtaining an API key for your Linode account.](#api-key-linode)
- [Adding an API key to your WarpSpeed account.](#api-key-warpspeed)

## <a name="api-key-do"></a>Obtaining an API key for your Digital Ocean account.

<video src="http://warpspeedio.s3.amazonaws.com/ws_api_key_do.mp4" controls preload="auto" height="auto"></video>

1. If you don’t already have an account, create one [here](https://www.digitalocean.com/?refcode=e8387d479043).
1. Login to your account and then click the “API” link in the top menu bar.

    ![](/v1/img/do_api_key_1.png)

1. Locate and click the “Generate New Token” button in the upper left hand portion of the screen.

    ![](/v1/img/do_api_key_2.png)
    
1. Enter “warpspeed” in the token name text box.
1. In the “Select Scopes” section, be sure to check the “Write” checkbox.

    ![](/v1/img/do_api_key_3.png)
    
1. Click the “Generate Token” button.
1. The API key you generated will be displayed only once for security reasons. Copy this key so you can paste it into your WarpSpeed account settings.

    ![](/v1/img/do_api_key_4.png)

## <a name="api-key-linode"></a>Obtaining an API key for your Linode account.

<video src="http://warpspeedio.s3.amazonaws.com/ws_api_key_linode.mp4" controls preload="auto" height="auto"></video>

1. If you don’t already have an account, create one [here](https://www.linode.com/?r=bed2c06e157de72a8f97d0c7035069800c9b342b).
1. Login to your account and then click on the “my profile” link in the upper right hand corner. You will be prompted for your password.
1. Click on the “API Keys” tab on the far right of the “My Profile” page.
1. Use the “Add an API key” form to create a new API key. Enter the label "warpspeed" and leave expires set to “Never”, then click “Create API Key”.

    ![](/v1/img/linode_api_key_1.png)
    
1. The API key you generated will be displayed only once for security reasons. Copy this key so you can paste it into your WarpSpeed account settings.

    ![](/v1/img/linode_api_key_2.png)
    
## <a name="api-key-warpspeed"></a>Adding an API key to your WarpSpeed account.

1. Login to your WarpSpeed account [here](https://warpspeed.io/login).
1. Click on your name in the upper right hand corner of the screen and then select “Account Settings” from the drop down menu.
1. On the “Server Providers” tab, select the Provider that you are adding the key for.
1. Add a nickname for the key. If you only have one account for a particular provider, this can just be the provider name. If you have multiple accounts, name it something that will help differentiate the accounts.
1. Paste the API key from your server provider in the “API Key” text box.
1. Click “Add Server Provider” and celebrate.
