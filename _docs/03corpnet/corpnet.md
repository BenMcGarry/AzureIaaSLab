---
title: CorpNet Setup
category: CorpNet
order: 1
---

First we need the build the simulated corporate network which will include a developer workstation. This can be referred to as a jump box into the Amsterdam network.

1. Go to the [Azure portal](https://portal.azure.com) and log in using your Azure subscription credentials.

1. Click **Create a resource** at the top of the left blade.

1. In the search filter type **Visual Studio 2017** and hit return.

1. Select **Visual Studio Community 2017 (latest release) on Windows Server 2016 (x64)**, then in the rightmost blade **ensure Resource Manager is selected** and click Create.

1. Ensure your subscription is selected. Under resource group, click **Create new** and set the name to **rgCorpNet**.

1. Set the following details for the Virtual Machine, leave everything else at default:
    - Virtual machine name: **vmCorpNet**
    - Region: **West Europe**
    - Size:  **D2_v3 Standard** (If this size is not available, any machine with 2 cores).
  
1. Type a username and password for your virtual machine.

1. Under Inbound Port Rules, select **Allow selected ports** and ensure that **RDP (3389)** is selected.

1. Click Next to Disks.

1. Ensure the OS disk type is set to **Standard SSD**.

1. Click Next to Networking.

1. Under Virtual Network, click **Create New** and set the name to **vnetCorpNet**. Under Select inbound ports, ensure that **RDP (3389) is already selected** to allow direct access to the VM.

1. Click Next to Management.

1. Set **Boot Diagnostics** and **OS guest diagnostics** to **Off**, this just saves some money on the subscription.

1. Click **Review + create**, then after validating the information click **Create**.

1. It will now show the deployment screen, click the refresh icon every so often to check the status. This may take up to 10 minutes to deploy.

1. On the left blade, select **Resource groups** and go to **your Resource Group**. **Select the newly made Virtual Machine**.

1. On the Virtual machine blade click **Connect** near the top. Then click **Download RDP File**.

1. Open the downloaded RDP File and click **Connect**.

1. Under **More choices**, Select **Use a different account** then enter the credentials you set when creating the VM. Use the following format for the username: .\\<username\>.

1. At the certificate dialogue, click **Yes**.

1. Ensure you are connected to the VM and logged in. 

    **Note**: You may be prompted to configure some privacy settings. These are settings on the Windows 10 Enterprise image. As this is a throwaway VM we can just accept the default values and continue.

1. Open Visual Studio 2017. At the sign-in box, click Sign In. Sign in with the account that you are using for your Azure subscription.

1. Click on the Server Explorer bar in the very left of the main Visual Studio 2017 interface, then click on Azure. After a few seconds, your new Azure subscription should appear. 

    Here you can see resources within your Azure subscription. This is primarily used when developing and deploying applications from Visual Studio 2017 directly onto Azure. For the purpose of this lab we will not be using this functionality and have shown this purely for informational purposes.

1. Now that Visual Studio 2017 is configured, you can close it down.

**You may use this virtual machine for the lab, However the instructions will assume you are using the local computer. You may have to re-do some of the initial setup if you choose to use this virtual machine.**

## [Next]({{ site.baseurl }}/04amsterdam/resourcegroup)
