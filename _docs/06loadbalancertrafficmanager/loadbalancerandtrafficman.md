---
title: Overview
category: Load Balancer & Traffic Manager
order: 1
---

The diagram below shows what you have already provisioned in blue. The red resources are what you are about to provision. You'll need a separate PIP for the load balancer and you'll need to configure the load balancer to take traffic from the new PIP and load balance across your 2 existing VMs.

![Load Balancer Diagram]({{ site.baseurl }}/img/loadbalancer.png)

These tasks can be performed in the Azure Portal, but you'll perform them now using the Azure CLI just to give you experience of using a different method of configuration.

## [Next]({{ site.baseurl }}/06loadbalancertrafficmanager/lbendpoint)