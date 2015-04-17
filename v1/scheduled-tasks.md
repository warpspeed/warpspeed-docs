---
layout: doc
title: Scheduled Tasks
---

# Scheduled Tasks

Sometimes, you'll need to run a task on your server at a scheduled interval. That is what [cron](http://en.wikipedia.org/wiki/Cron) is for. WarpSpeed provides a nice way to manage cron jobs without the need to log into your server.

### Add a Scheduled Task

To add a new scheduled task, follow these steps:

1. Login to your WarpSpeed account [here](https://warpspeed.io/login).
1. Access your "My Servers" dashboard and click on the "Manage" button next to the server you want to create the site on.
1. Select the "Scheduled Tasks" tab and you will see something similar to the following:

	![](/v1/img/scheduled_tasks.png)

1. Enter the command you would like to run.
1. Enter the user the command should be run as. Generally, this should be "warpspeed" unless you have a need to run something as "root".
1. Select the schedule by clicking on the scheduling buttons. Full cron rules can be specified in the boxes below if desired.
1. Verify your inputs and then click the "Add Scheduled Task" button. The Scheduled Task will be added immediately.

### Manage Existing Scheduled Tasks

Access the "Scheduled Tasks" tab of the server management page as described above and look at the "Existing Server Scheduled Tasks" section. Any existing tasks will be listed here. You can remove the task by clicking "Delete", or look at the log from the latest run by clicking "Show Log".
