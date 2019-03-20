---
title: Creating a Windows Virtual Machine
category: Amsterdam
order: 5
---

You will now create a Virtual Machine based on Windows Server 2019. Here you will use all of the resources you just created. **Please follow the instructions carefully.**

1. Click Create a resource at the top of the left blade.

1. In the search filter type **Windows Server** and hit return. Select **Windows Server**.

1. Select **Windows Server 2019 Datacenter** from the drop down menu and **ensure Resource Manager is selected** and click Create.

1. Ensure your subscription is selected. Under resource group, **select the Amsterdam one** you created earlier.

1. Set the following details for the Virtual Machine, leave everything else at default:
    - Virtual machine name: **<vm name\>**
    - Region: **West Europe**
    - Availability Options: **Availability Set, create a new Availability Set named <availability set name\> leaving Fault and Update domains at their default values**
    - Size:  **DS1_v2 Standard**
  
1. Type a username and password for your virtual machine.

1. Under Public inbound ports, select **Allow selected ports** and ensure that **RDP (3389)** is selected.

1. Click Next to Disks.

1. Set the disk type to **Standard HDD** and under advanced, set **Use managed disks** to **No**. **Select the storage account that you created for Amsterdam.**

1. Click Next to Networking.

1. **Ensure the following is set for the network leaving everything else at default. Failing to correctly configure it here will cause problems later on**:
    - Virtual network: **<vnet name\> -  Use the one you created earlier.**
    - Public IP: **<instance-level pip name\> - Use the one you created earlier or you will experience DNS issues.**
    - NIC network security group: **Select Advanced, then Create new, then enter <nsg name\>.**

1. Click Next to Management.

1. Set **Boot diagnostics** and **OS guest diagnostics** to **Off**, this just saves some money on the subscription.

1. Click **Review + create**, then after validating the information click **Create**.

1. The VM may take up to 10 minutes to deploy.

**Notes**

If you go to **Resource groups** on the left menu and open the resource group you created earlier, you will see all of the resources that have been created. Notice the Network interface was automatically created and it has an auto-generated name. The name comes from the VM it is attached to plus a random number.

Network security groups are objects that contain rules to secure traffic flow. **Click on the Network interface** and in the left-hand menu, click **Network security group**, then the **network security group for this resource (<nsg name\>)** then **Inbound security rules**. Notice how any source IP address is permitted to come in on port 3389 (RDP).

## [Next]({{ site.baseurl }}/04amsterdam/rdp)