---
title: Creating a Public IP Address (PIP)
category: Amsterdam
order: 4
---

You will now create a Public IP Address (PIP), this will be bound to your first Virtual Machine to give it a public IP address that can be used to communicate with it.

1. In the left-hand blade – **click All Services** and **under Networking**, **click Public IP addresses** then **click Add.**

1. Name: **<instance-level pip name\>**

1. SKU, IP Version, IP address management and Idle timeout **left at default values**.

1. DNS name label: **<instance-level pip DNS name\>** (This needs to be world-unique and lower-case with only numbers or letters, no special characters).

1. **Ensure your subscription is selected.**

1. Resource group: **Select the one you created for Amsterdam.**

1. Location: **West Europe**.

1. Click **Create**.

1. Your Public IP Address will now be created. Notice near the top right corner, the status of "creating" might be displayed. If not, click the bell icon to see when the Public IP Address has been created.

## [Next]({{ site.baseurl }}/04amsterdam/virtualmachine)