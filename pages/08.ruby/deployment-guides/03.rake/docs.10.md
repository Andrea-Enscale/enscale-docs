---
title: Rake
taxonomy:
    category:
        - docs
visible: true
---

### RAKE_DEPLOY

In Enscale, you can create a list of commands to be executed by rake immediately after deployment.

In order to do this, you will need to create your _rake\_deploy_ file and place it in your project’s root folder.

Once the deployment is finished, rake will read your _rake\_deploy_ file and it will execute the commands in the order of their listing.

After the commands are executed, the _rake\_deploy_ file is deleted, however you can see the results in the [_rake\_deploy.log_ file](https://enscale.com/docs/10/environments/access/log-files).

Enscale also checks for a _rake\_deploy_ file each time the application node is restarted; so if you need rake to perform additional commands, other than during the initial deployment (e.g. ad-hoc or during application updates) simply ensure the _rake\_deploy_ file is present in your application’s root folder and restart the node.

### What should my _rake\_deploy_ file look like?

Each command should be on a separate line:
```
$COMMAND_NAME_1
$COMMAND_NAME_2

...

$COMMAND_NAME_N
```

For each line,`rake $COMMAND_NAME_X` is executed.

!!! Ensure that the commands are listed in the appropriate order, as rake will execute them successively.

