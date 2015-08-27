---
layout: doc
title: Integration with Codeship
---

# Integration with Codeship

![Codeship](http://i0.wp.com/webuilddesign.com/wp-content/uploads/2014/10/codeship.jpg) 

[Codeship](https://codeship.com) is a wonderful resource for developing code. It is a tool that can provide "powerful continuous integration and delivery". When paired with WarpSpeed, you can run your test suite effectively and immediately deploy your code. Together, WarpSpeed and Codeship make for a power continuous integration and delivery platform.

## Two Ways to Integrate

Codeship can be integrated with the WarpSpeed pull or push deploy workflow. The implementation for pull deploy is more suitable for use with Codeship since information about the success of each deploy will be displayed in the WarpSpeed user interface. Both methods will be discussed for complete coverage of this topic.

## Pull Deploy

<video src="http://warpspeedio.s3.amazonaws.com/ws_codeship_pull.mp4" controls preload="auto" height="auto"></video>

1. Log in to your WarpSpeed account and manage a site that has been pull deployed.
1. Copy the bolded trigger URL.
1. In a separate tab, log in to your [Codeship](https://codeship.com) account.
1. Press the "Select Project" tab in the navigation bar, and select "Create a new project".
1. Connect to the GitHub or Bitbucket repository you will be using.
1. Configure the setup commands for the testing environment and configure the testing pipelines. Click "Save and go to the dashboard".
1. Navigate to the project settings by pressing "Select Project" again, this time clicking the gear next to your project.
1. In the "Deployment" section, add a new deployment pipeline for the branch of your repository you will be using.
1. Using the custom script option, add and save the command `curl YOUR_TRIGGER_URL_HERE`.

Now every time that you push to this branch of your repository, Codeship will run your test suite and, upon success there, will trigger a pull deploy on your WarpSpeed server! You can view the latest deployment results by visiting your Site's deployment page in the WarpSpeed user interface.

## Push Deploy

<video src="http://warpspeedio.s3.amazonaws.com/ws_codeship_push.mp4" controls preload="auto" height="auto"></video>

1. Log in to your WarpSpeed account and manage a site that has been push deployed.
1. In a separate tab, log in to your [Codeship](https://codeship.com) account.
1. Press the "Select Project" tab in the navigation bar, and select "Create a new project".
1. Connect to the GitHub or Bitbucket repository you will be using.
1. Configure the setup commands for the testing environment and configure the testing pipelines. Click "Save and go to the dashboard".
1. Navigate to the project settings by pressing "Select Project" again, this time clicking the gear next to your project.
1. In the "Deployment" section, add a new deployment pipeline for the branch of your repository you will be using.
1. Using the custom script option, add and save the command `curl -sSL https://raw.githubusercontent.com/codeship/scripts/master/deployments/git_push.sh | bash -s`. This will execute a script that Codeship wrote that requires two environment variables.
1. In the "Environment" section, add two environment variables, `REMOTE_REPOSITORY` and `REMOTE_BRANCH`. The repository will be the git remote that WarpSpeed provides after you activated push deploy (what comes after the “git remote add …”). The branch will be the branch of the project you want to push.
1. In the "General" section, copy the ssh public key. 
1. On WarpSpeed, navigate back to the server you are using. Click the "SSH Keys" tab, and add your Codeship project's public key.


Now every time that you push to this branch of your repository, Codeship will run your test suite and, upon success there, will push to your WarpSpeed server!

