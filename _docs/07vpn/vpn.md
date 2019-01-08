---
title: Overview
category: Azure VPN
order: 1
---

Thinking about the Amsterdam site – it currently has 3 public endpoints. One instance-level IP address directly attached to each VM and a load-balanced endpoint.

![VPN Setup]({{ site.baseurl }}/img/vpnsetup.png)

An argument often posited at this configuration is that the attack-surface is larger than it needs to be. By providing so much connectivity to the outside world, you are inviting disaster. Often the answer suggested is to use NATing and port-mapping between the load-balanced PIP and the servers:

![VPN Debate]({{ site.baseurl }}/img/vpndebate.png)

The diagram above shows, in red, how high-numbered ports can be mapped on to individual servers. In this case to RDP in to AmsVM1, if the IP address is 179.16.53.22, you’d specify 179.16.53.22:5001. This reduces the number of exposed IP addresses but it makes it easier for an attacker to find the IP address (it's the same as your web server's) and perform a port-scan to see what response they get on all ports. And is the attack surface really reduced? All you've done is swap multiple IP addresses for multiple ports and put them on a well-known endpoint.

So perhaps the answer is to remove all externally facing ports and protocols, except the ones your service needs (probably HTTP and HTTPS). Then use a VPN from your on-premises network to connect to the servers. Like this:

![VPN Design]({{ site.baseurl }}/img/vpndesign.png)

This makes the VNet in Amsterdam look like a branch office to your corporate network. The 2 address spaces can't overlap, because the VPN Device and the VNet Gateway would get confused if any IP address had multiple routes.

For the next part, you don’t have access to a corporate network with a VPN device that you can configure. So you are going to simulate the environment by pretending that the CorpNet site is your corporate network. This is made a little easier than in real life because Azure understands how to connect the 2 sites together. In your own corporate network you'd have to configure the VPN gateway yourself. Azure makes this easy by generating a script file for the make and model of VPN device you have on your network.

In this lab, you'll have to use a little imagination and pretend when you are logged in to a server in the CorpNet region that you are actually logging in to a server on your corporate network.

Azure offers 3 options for VNet connectivity: Site-to-Site, VNet-to-VNet and ExpressRoute. In real life you'd configure a Site-to-Site network or even an ExpressRoute circuit. For this lab you'll configure a VNet-to-VNet VPN. Most of the steps are the same for configuring a Site-to-Site VNet and the principles are exactly the same.


## [Next]({{ site.baseurl }}/07vpn/gatewaysetup)