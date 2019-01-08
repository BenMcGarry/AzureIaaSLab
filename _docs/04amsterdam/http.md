---
title: Enabling HTTP Support
category: Amsterdam
order: 7
---

You will now enable HTTP connections into the network to allow the IIS Web Server to be contactable. This will involve creating a new rule in the Network security group to allow HTTP traffic over port 80 into the virtual network.

1. In the left-hand blade – click **Resource groups** and click the **Resource group you are working in**, then click your **Network security group <nsg name\>**.

1. Select **Inbound security rules**.

1. Click **Add** then create a new rule using the following details leaving everything else at default:
    - Destination port ranges: **80**
    - Name: **AllowHTTP**

    Click **Add** to create the rule.

1. Go back to your **Resource group** and select your **Public IP address**. On the Overview blade it should show it's fully qualified domain name in the structure of **\<instance-level pip DNS name\>.westeurope.cloudapp.azure.com**. There should be a small copy icon next to it. **Click it**.

1. You should now be able to connect to the webserver, in a browser connect to your copied URL and you should see your page with the modified image.

## [Next]({{ site.baseurl }}/04amsterdam/secondpip)