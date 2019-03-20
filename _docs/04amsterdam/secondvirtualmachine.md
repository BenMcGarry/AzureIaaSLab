---
title: Creating a Second Windows Virtual Machine
category: Amsterdam
order: 9
---

You will now create a second Windows Virtual Machine. **Please follow these instructions carefully and when looking at the naming convention, focus on Amsterdam VM1**.

1. Click Create a resource at the top of the left blade.

1. In the search filter type **Windows Server** and hit return. Select **Windows Server**.

1. Select **Windows Server 2019 Datacenter** from the drop down menu and **ensure Resource Manager is selected** and click Create.

1. Ensure your subscription is selected. Under resource group, **select the Amsterdam one** you created earlier.

1. Set the following details for the Virtual Machine, leave everything else at default:
    - Virtual machine name: **<vm name\>**
    - Region: **West Europe**
    - Availability Options: **Availability Set, select the set you created earlier (<availability set name\>). If you do not see it listed STOP, do not continue until you can put the second VM within the availability set.**
    - Size:  **DS1_v2 Standard**

1. Type a username and password for your virtual machine.

1. Under Public inbound ports, select **Allow selected ports** and ensure that **RDP (3389)** is selected.

1. Click Next to Disks.

1. Set the disk type to **Standard HDD** and under advanced, set **Use managed disks** to **No**. **Select the storage account that you created for Amsterdam.**

1. Click Next to Networking.

1. **Ensure the following is set for the network leaving everything else at default. Failing to correctly configure it here will cause problems later on**:
    - Virtual network: **<vnet name\>  - Use the one you created earlier.**
    - Public IP: **<instance-level pip name\> - Use the one you just created for the second VM.**
    - NIC network security group: **Select Advanced, then select the one you created earlier (<nsg name\>).**

1. Click Next to Management.

1. Set **Boot diagnostics** and **OS guest diagnostics** to **Off**, this just saves some money on the subscription.

1. Click **Review + create**, then after validating the information click **Create**.

1. The VM may take up to 10 minutes to deploy.

## [Next]({{ site.baseurl }}/04amsterdam/secondrdp)