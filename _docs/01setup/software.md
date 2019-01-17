---
title: Software Setup
category: Setup
order: 2
---

**If you are at a Microsoft Technology Centre for this lab. You may skip these steps as they have already been done for you.**


We need to get Visual Studio Code installed. Go [here](https://code.visualstudio.com/Download) and click the Windows Download.

![VS Code Download]({{ site.baseurl }}/img/vscode.png)

When prompted to Run or Download. Hit Run and continue with the installation. Select the following options when prompted:

![VS Code Install]({{ site.baseurl }}/img/vscodeinstall.png)

We need to install the AzureRM Powershell module to be able to run Powershell commands for Azure, it might already be installed. To check this open powershell and run: 

```powershell
Get-InstalledModule -Name AzureRM -AllVersions
```

If AzureRM is returned you are good to go!. If not run the following commands in Powershell with Administrative rights.

```powershell
Install-Module -Name AzureRM -AllowClobber
```

If you get prompted about it being an unsafe repository, Answer **Yes** or **Yes to All** to continue with the installation.

Then we need to make sure the module is loaded. Run the following command:

```powershell 
Import-Module AzureRM
```

We are now all setup for the lab!

## [Next]({{ site.baseurl }}/02overview/overview)
