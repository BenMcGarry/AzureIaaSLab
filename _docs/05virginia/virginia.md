---
title: Virginia Infrastructure
category: Virginia
order: 1
---

Before you deploy a load balancer to the 2 Virtual Machines you have running in Amsterdam, you will create a similar set of infrastructure in Virginia, East US. This will be quicker to do because you will use a Azure Resource Manager (ARM) Template. In this lab, you will get a small amount of experience of working with Azure Resource Manager templates, JSON data and Powershell.

You will export the configuration as it stands to a template and then re-deploy that template to a different region (East US) using Powershell. There are some modifications you will need to make so you do not get conflicting names.

![Parameter Template Export/Import Example]({{ site.baseurl }}/img/template-parameter.png)

A Azure Resource Manager (ARM) Template is a configuration file written in JavaScript Object Notation (JSON). When you deploy a template, Azure opens it and reads out the resource types, their names, locations and other relevant properties like domain names.

It then sets up a process to build the infrastructure and can perform many tasks in parallel. It will deploy both Virtual Machines in parallel which speeds deployment. It also parses the file to look for dependencies – for example a Virtual Machine depends on a NIC which depends on a VNet. It takes care of all these problems.

The template is an indication to Azure of what you want the final state of the deployment to look like. It is idempotent; that is, it takes care of things like "a storage account of that name already exists". If it doesn't exist, it creates one. If it does exist it uses the existing one. But it only knows about things that are discoverable at deployment time. If, for example, you deploy a template with a domain-name that is already in use it will fail.

Templates have 5 sections. The first 2 are very short (one line each) – schema and contentVersion. You can ignore them. The next 3 are interesting – parameters, variables and resources. You can hard-code the parameters section if you want to but it's usually better to have a separate parameters file and fill that in for each unique deployment you make.

So the Virtual Machines in the first deployment might be AmsVM0 and AmsVM1; in the second deployment they are VirgVM0 and VirgVM1. The template remains the same throughout but you have edited a parameter file:

![Parameter Template]({{ site.baseurl }}/img/parameterfile.png)

## [Next]({{ site.baseurl }}/05virginia/createtemplate)