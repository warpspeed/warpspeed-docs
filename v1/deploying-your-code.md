---
layout: doc
title: Deploying your Code
---

# Deploying your Code

After you have created a new site on your server, it is time to get your code deployed. WarpSpeed offers several ways to deploy your code. Here are the supported deployment methods:

- Push Deploy
- Pull Deploy
- SFTP Deploy

Push and pull deploy assume you are using git for source versioning. If you aren't, you should strongly consider it. Please see the details about each method below.

## Push Deploy

Push deploy utilizes git to push your code from your local development environment to your WarpSpeed server by issuing a simple "git push" command. Push deploy is great for individual developers or for teams where there is one person responsible for deploying code.

To enable push deploy for your site, perform the following steps:

1. Login to your WarpSpeed account [here](https://warpspeed.io/login).
1. Access your "My Servers" dashboard and click on the "Manage" button next to the server your site is on.
1. Access your site details by clicking on the "Manage" button next to the site you want to deploy code to.
1. Click on the "Activate Push Deploy" button. You should see a success message along with some instructions on how to use push deployment.
1. Copy the "git remote add ..." command that is give to you after push deploy activation.
1. Open your terminal and browse to your project directory, then paste the command to add the new git remote and hit enter. You have now created a git remote that will allow you to push code to the site configured on your server.
1. To push your code, run "git push warpspeed master" from your project directory in your terminal.

To configure actions that happen each time your code is deployed, you may create a "warpspeed.sh" file in your project's root directory. See the "Post Deploy Actions" section below for details.

## Pull Deploy

Pull deploy utilizes git for code deployment. Pull deploys can be initiated by clicking a button in the WarpSpeed.io interface or by accessing a special site URL. The special URL can also be placed in a post-commit hook in your repository to auto-deploy each time code is pushed or it can even be added to your continuous integration tool. Pull deploys are great for teams where you have existing deployment or test tools that you need to integrate with.

When a pull deploy is initiated, WarpSpeed will SSH into your server and issue a "git pull" for the specified site. This requires your server to be able to access your git repository. In order to provide access, you must add you server's public key to your git account.

To enable pull deploy for your site, perform the following steps:

1. Login to your WarpSpeed account [here](https://warpspeed.io/login).
1. Access your "My Servers" dashboard and click on the "Manage" button next to the server your site is on.
1. Access your site details by clicking on the "Manage" button next to the site you want to deploy code to.
1. If you haven't yet you should have the option to "Activate Pull Deploy". Before doing so, please make sure you have copied your server's public key to your git account.
1. Next, enter your repositories URL and branch into the input boxes and then click "Activate Pull Deploy". If an error occurs during pull deployment, you will either need to wait for a timeout (up to 30 minutes) or use the "Revert Site" button to revert your site to its default configuration.

## Post Deploy Actions

If you would like to run a set of commands each time your code is deployed (via push or pull), you may do so by creating a "warpspeed.sh" file in your project's root directory. If the file exists, it will be run after successful deployment.

Some useful things to place in your post deploy actions file are:

- Running db migrations
- Installing software updates
- Building static HTML sites

Make sure to set the appropriate environment settings within your "warpspeed.sh" file to ensure the script will work as you expect. The script will be executed within the root directory of your site.

## SFTP Deploy

If you don't use git for version control, you can also deploy your code via SFTP.

