---
title: Creating a Storage Account
category: Amsterdam
order: 3
---

You will now create a Storage Account which the Virtual Machine disks will be stored in.

1. In the left-hand blade – **click Storage accounts** and **click Add.**

1. **Ensure your subscription is selected.**

1. Resource group: **Select the one you created for Amsterdam.**

1. Name: **<storage account name\>**. Note: this will eventually end up as a DNS name in the form "storeamsbemcgarry.blob.core.windows.net". **DNS names must be world-unique.**

1. Location: **West Europe**.

1. Performance: **Standard**.

1. Account kind: **StorageV2 (general purpose v2).**

1. Click **Review + create**, then after validating the information click **Create**.

1. Your Storage Account will now be created. Notice near the top right corner, the status of "creating" might be displayed. If not, click the bell icon to see when the Storage Account has been created.

## [Next]({{ site.baseurl }}/04amsterdam/pip)