---
title: Setting up the Gateways
category: Azure VPN
order: 2
---

We will now setup the gateways on each site to allow the connection.

**NOTE: This part of the lab can take around 30 minutes to complete.**

A Gateway has to have a subnet for its own exclusive use.

1. In the Amsterdam Resource Group, **go to the Amsterdam Virtual Network**. Under Settings go to **Subnets**. Click **Gateway subnet** near the top.

1. Leave everything at its default values and click OK. 

    **Note:** If you cannot create a new Gateway Subnet, it is almost certainly because the address space created with your VNet has been entirely taken up by your VM subnet. You will need to return to your VNet configuration, click on Address space, and add an additional /24. If your existing address space is 10.1.0.0/24, for example, add 10.2.0.0/24 for the gateway subnet. You will need to do the same on both sides, CorpNet and Amsterdam.

1. When complete go to **All Services** then under Networking select **Virtual network gateways**.

1. Click **Add** and use the following settings:
    - Name: **<gateway name\>** (remember this is Amsterdam).

    - **Scroll down to the bottom and set the Location to West Europe. You won’t be offered the right options unless you are in the right region.**

    - Gateway type: **VPN**
    - VPN type: **Route-based**
    - Virtual network: **<vnet name\>** (remember this is Amsterdam).
    - Public IP address: **Create a new address called <gateway pip name\>**.
    - **Ensure your subscription is selected.**

    The resource group should default to <resource group name\> in Amsterdam because it has to be in the same resource group as the VNet. **Click Create**.

1. Provisioning a Gateway takes about 20 minutes. Although you can never see them as raw servers, it provisions two VMs with the gateway software installed and under the control of Azure. You might as well set up the CorpNet half of the configuration while you're waiting. 

    I'm guessing you have the measure of this by now – go ahead and create a Gateway Subnet, PIP and Gateway in the CorpNet region. You can use the instructions for Amsterdam as the basis. **Remember to select West Europe when creating the Gateway**.

    **You have a fairly long break now of about 20 minutes**. Once both Gateways are online, continue with the instructions below.

1. In the left-hand blade – **click All Services** and **under Networking**, **click Connections** then **click Add**. Configure using the following settings then click Ok:
    - Connection type: **VNet-to-VNet**
    - Resource group: **<resource group name\>**. Select your Amsterdam one.
    - Location: **West Europe**

1. **Choose the 2 Gateways** you have just created in Amsterdam and CorpNet. **Make up a shared key then click OK**.

1. **Click OK on the summary page**, then wait until the connections have been successfully created. Remember you can use the bell icon to check progress.

1. You'll treat the "Dev Workstation" on CorpNet as if it is a client machine on your corporate network. Normally you'd physically walk up to the machine and log in to. Because this is in fact a VM running in a data-centre in another country that's not possible. But it does have a private endpoint that permits RDP.

1. **Find the CorpNet VM in the portal, open its blade and click Connect**. Login using the credentials you specified earlier.

1. Pretend you are now logged in to a client in your own corporate network. You need an easy way to connect to the other VMs without remembering the IP addresses. For this we will use the HOSTS file.

1. In the Azure portal, find Amsterdam's VM0. Under Settings then Networking, note the internal IP address (probably 10.1.0.4). Also do this for the second Amsterdam VM.

1. Back in the "Dev Workstation" computer, navigate to C:\Windows\System32\drivers\etc. Use notepad to edit HOSTS.

1. At the bottom of the file after the section with # at the start. Add the following lines adjusting the IP where appropriate, ensure there is no space before the IP and atleast 1 space between the IP and VM name.

    ```
    10.1.0.4     amsvm0
    10.1.0.5     amsvm1
    ```

1. Save the file.

1. Open up a Remote Desktop client and connect to the two VMs in Amsterdam using the names you set above. Go through the various dialogues to log in.

### Site-to-Site VNet Summary

You could now remove all unnecessary PIPs and dispense with NAT port-mapping. If this was a real corporate network, you could manage all your Azure resources as if they are part of your normal on-premises network.

VNet Gateways consist of pairs of VMs running gateway software. You can never log on to the VMs and configure them. The only way you interact with them is through Azure's interfaces (Portal, CLI, Powershell, RG templates, REST APIs etc). But **the fact they are running machines makes them an expensive resource if you're not using them. So delete them from your configuration to contain costs after you have finished the lab** – you'll have 2 less machines running. **You will need to delete the connections first**. [This page](https://azure.microsoft.com/en-gb/pricing/details/vpn-gateway/) shows how pricing is calculated.

## [Next]({{ site.baseurl }}/08summary/summary)