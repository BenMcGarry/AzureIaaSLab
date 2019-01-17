---
title: Provision Traffic Manager
category: Load Balancer & Traffic Manager
order: 4
---

We will now provision the Traffic Manager between West Europe and East US regions.

1. In the left-hand blade – **click All Services** and **under Networking**, **click Traffic Manager profiles** then **click Add.**

1. Use the following settings for the Traffic Manager:
    - Name: **<traffic manager DNS name\>**. Make sure it's lowercase.
    - Routing method: **Priority**
    - **Ensure your subscription is selected.**
    - Resource group: **<resource group name\>**. Choose Virginia, it just needs a resource group to be kept in.
    - Resource group location: East US.

    Then click **Create**.

1. In the portal, go to the resource group you put the Traffic Manager in and go to the Traffic Manager. On the settings blade go to **Configuration**. Set the **DNS time to live (TTL) to 100 seconds**. Leave the other settings at their default values then **click Save** near the top of the screen.

1. On the left blade for Traffic Manager **go to Endpoints** and **click Add**. Notice in Type there are 3 options. 
    - An external endpoint is one where the endpoint isn't hosted in Azure. For this you must provide the FQDN. 
    - A nested endpoint connects to an endpoint that has already had the Traffic Manager treatment. So it's Traffic Manager on top of another Traffic Manager. 
    - **You will select Azure endpoint** because your endpoints are PIPs hosted in Azure. 

1. **Click Target resource type** and **select Public IP address**. 

1. For the Virginia endpoint use the following settings:
    - Name: **<endpoint name\>**
    - Target resource type: **Public IP address**
    - Target resource: **<instance-level pip name\>** (remember this is one of your individual VMs in Virginia with the webserver)
    - Priority: **1**

1. For the Amsterdam endpoint use the following settings:
    - Name: **<endpoint name\>**
    - Target resource type: **Public IP address**
    - Target resource: **<load balancer pip name\>**
    - Priority: **2**

    Virginia has a higher priority than Amsterdam so it will route traffic to Virginia and only route to Amsterdam if Virginia fails.

1. Select **Overview** in the Traffic Manager menu and note the Traffic Manager DNS name at the top.

1. Test the Traffic Manager by going to that URL and notice that it doesn’t matter how many times you refresh – you are always taken to the Virginia web server.

1. Open a command prompt and type **ping <traffic manager DNS name\>.trafficmanager.net**. You won't get a response; Azure drops all ICMP Echo packets sent to it. But DNS name resolution will occur and you'll notice the underlying Virginia endpoint address being queried.

1. Use the portal to **stop your Virginia VM with the web server on**.

1. It takes Traffic Manager a moment to notice that a server has gone offline.

When Traffic Manager becomes aware that the Virtual Machine is no longer responding, it will start issuing the IP address for Amsterdam. But for your client's DNS resolver to notice, it will need to wait for the DNS cache to timeout. You may therefore need to wait around 5 minutes.

There are multiple layers of caching in operation. The Traffic Manager system itself monitors the endpoints and takes a moment to detect a failure. The TTL in the chain of DNS servers between your client machine and Traffic Manager influences it. Your organisation might have a proxy with cached web files. The local DNS resolver in your client has a timeout. The web browser will usually cache static files. 

To test failback, try a fresh instance of an InPrivate Browser every few minutes. Before using it, try issuing the ipconfig /flushdns command at the command prompt.

## [Next]({{ site.baseurl }}/07vpn/vpn)
