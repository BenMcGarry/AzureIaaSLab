---
title: RDP & Web Server Configuration
category: Amsterdam
order: 6
---

You will now remotely connect to your Virtual Machine via RDP to configure the IIS (Internet Information Services) Web Server.

1. In the left-hand blade – **click Virtual machines** and **click the VM you just created.**

1. On the Virtual machine blade, click **Connect** near the top, then click **Download RDP File** and **Save** the file. Once it is downloaded, **Open** it. Click **Connect** when prompted.

1. Under **More choices**, Select **Use a different account** then enter the credentials you set when creating the VM. Use the following format for the username: .\\<username\>.

1. At the certificate dialogue, click **Yes**.

1. Once connected to the VM over RDP, in Server Manager (it should open automatically) **click Local Server** on the left and **switch off IE Enhanced Security Configuration**.

    ![Image of Turning off IE Security Configuration]({{ site.baseurl }}/img/ie-sec-config.png)

1. Add the IIS role to the server, to do this go to **Manage** on the top right of Server Manager, then click **Add Roles and Features**.

1. Click **Next** until you reach the **Select server roles** page. Scroll down and **select Web Server (IIS)** then click **Add Features**.

1. Click **Next** until the Install button is available, then **click Install**. This will install IIS on the server.

1. You will now have to wait for IIS to be installed, this should take no more than 5 minutes.

1. Go to **File Explorer** and **navigate to c:/inetpub/wwwroot**. You should see a image called iisstart.png, **right click on the file and click Edit.** Draw on the image identifying which VM it is. (For example **AmsVM0**).

![IIS Name]({{ site.baseurl }}/img/iisname.png)

## [Next]({{ site.baseurl }}/04amsterdam/http)