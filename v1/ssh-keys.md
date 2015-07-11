---
layout: doc
title: SSH Keys
---

# SSH Keys

When a server is provisioned with WarpSpeed, it gets configured for authentication using SSH keys. Password authentication for SSH gets disabled. This is considered best-practice and it helps keep your server secure.

SSH keys come in pairs. One is a private key and that is for you to keep to yourself (don't lose it!). The other is a public key, and that one is to be shared. WarpSpeed needs to be configured with you public key so that it can place this on your servers. The topics below will help you create an SSH key pair (if you don't already have one) and add your public key to your WarpSpeed.io account.

<video src="http://warpspeedio.s3.amazonaws.com/ws_ssh_key_mac.mp4" controls preload="auto" height="auto"></video>

## Topics

- [Creating a new key pair.](#ssh-keys-create)
- [Copying your public key.](#ssh-keys-copy)
- [Configuring in WarpSpeed.](#ssh-keys-warpspeed)

## <a name="ssh-keys-create"></a>Creating a new key pair.

1. First, determine if you have an existing SSH key by running the following command in your terminal:

    ```
    ls -al ~/.ssh
    ```

    If you see `id_rsa` and `id_rsa.pub` you are in good shape and you don't need to continue to the next step.

1. If you do not have an existing key pair, run the following command to generate one:

    ```
    ssh-keygen -t rsa -C "your_email@example.com"
    ```

    When you are prompted for a passphrase, enter something memorable and secure. You will need this passphrase anytime you use your SSH key.

## <a name="ssh-keys-copy"></a>Copying your public key.

Copying your SSH public key to your clipboard in OSX can be done by running the following command in your terminal:

```
pbcopy < ~/.ssh/id_rsa.pub
```

## <a name="ssh-keys-warpspeed"></a>Adding an SSH public key to WarpSpeed.

1. Login to your WarpSpeed account [here](https://warpspeed.io/login).
1. Click on your name in the upper right hand corner of the screen and then select “Account Settings” from the drop down menu.
1. Select the “SSH keys” tab.
1. Add a nickname for the key. Use something memorable that will tell you where the key originated. Perhaps something like macbook-air.
1. Paste the public key from you copied to your clipboard in the “Public Key” text box.
1. Click “Add SSH Key” and celebrate.
