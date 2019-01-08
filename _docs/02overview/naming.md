---
title: Naming Conventions
category: Overview
order: 3
---

There is a lot of infrastructure to build. It is easy to get lost if you make up the names of the various resources such as VMs, Load Balancers, Virtual Networks and so on as you go along.

**You can download the naming convention [spreadsheet here]({{ site.baseurl }}/resources/NamingConventions.xlsx).**

A recommended approach for this lab is **<resource-type\><resource-name\><unique-name\>**. So vmamsvm0myproject is a VM called amsvm0 and uniquely named myproject. The unique name might typically be an application, service name, department, region, project or similar entity.

For the purposes of this lab, you could just use your last name. Bear in mind that some of these names appear as DNS names, it is therefore important that they be world-unique. So, if your last name is "Smith" or "Jones" or you share a last name with somebody else doing this lab today, you should get creative!

1. In the Azure Portal, go to **Cost Management + Billing** on the left blade, select **Subscriptions** under Billing, **Select your subscription** then **copy the Subscription ID**. Put this in your naming convention file.

In the instructions that follow, wherever you see naming entries such as **<resource group name\>**, refer to the naming convention file and bear in mind the region (Amsterdam, Virginia or CorpNet).

If you would like to read more on Microsoft's recommendations for naming conventions. Please go [here](https://docs.microsoft.com/en-us/azure/architecture/best-practices/naming-conventions).

## [Next]({{ site.baseurl }}/03corpnet/corpnet)