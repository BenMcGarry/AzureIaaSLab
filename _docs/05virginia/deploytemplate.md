---
title: Deploying the Template
category: Virginia
order: 3
---

1. Locate Powershell ISE in the start menu, right-click and choose **Run as administrator**.

1. **At the command-prompt, cd to the directory in which you extracted the template.** For example:

    ```
    cd "C:\Users\trainee\Downloads\ARM Template"
     ```

1. In Powershell ISE, go to File > Open to open the deploy.ps1 script from the same location.

1. Type cls to clear the screen.

1. **Run the powershell script with the green arrow at the top**. If you get a "File Cannot be loaded because running scripts is disabled on this system" error when you try to run the script, run the following command to clear it and click Yes to All then re-run the deploy.ps1 script.

    ```powershell
    Set-ExecutionPolicy Unrestricted
     ```

1. When prompted, at the security warning, select **Run Once**.

1. Refer to the Subscription ID at the top of the naming convention table. Enter your Subscription ID when prompted (alternatively, in the portal go to **Cost Management + Billing then Subscriptions** to find your Subscription ID).

1. When asked for a Resource Group, type "<resource group name\>" **Note: This is a new resource group – you are now deploying to Virginia. The name will be something like "rgVirg".**

1. The deployment name is only used for logging – you can type anything.

1. You will be prompted to login. Use your portal credentials for this.

1. After a short time you will be prompted for a location for the new resource group – **specify eastus**. This is merely the location of the resource group itself, the location of the resources you are about to deploy is determined by the previous edits you made to the template in which you specified "eastus".

1. It'll probably take around 15 minutes to deploy everything, but you can see it gradually deploying in the Azure portal. **If you go to your resource groups, select your Virginia one and click deploying at the top, you can see the status of the template deployment.**

1. To save time, rather than deploying the load balanced infrastructure into Virginia (you'll be doing this in Amsterdam soon anyway), you'll just install a web server on to one of the VMs (it will probably be called something like vmvirgvm0).

    **RDP in to <vm name\> and install IIS as you did for the servers in Amsterdam. Decorate the default web page in an interesting and artistic way to signify it's running in Virginia.**

1. Test that when you connect to the DNS name of the PIP, you get the web page you expect.

## [Next]({{ site.baseurl }}/06loadbalancertrafficmanager/loadbalancerandtrafficman)
