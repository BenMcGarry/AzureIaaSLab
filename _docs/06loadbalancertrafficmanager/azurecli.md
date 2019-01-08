---
title: Install and configure the Azure CLI
category: Load Balancer & Traffic Manager
order: 2
---

1. Go [here](https://docs.microsoft.com/en-us/cli/azure/install-azure-cli) to download the Azure CLI. 

1. Click **Install on Windows** then **Download the MSI installer**. Run this file and continue with the installation.

1. Once installed, open a command prompt and type az. Scroll back to the top of the page and marvel at the ASCII-art.

1. To log in type the following and follow the on-screen instructions.

    ```powershell
    az login
    ``` 

1. You need to also set which subscription you will be working in. To do this run the following command but edit it to put in your Subscription ID: 

    ```powershell
    az account set --subscription <subscription id>
    ```

That is the Azure CLI all setup and ready to go! Do not close the Command Prompt window as we will be using it shortly.

## [Next]({{ site.baseurl }}/06loadbalancertrafficmanager/lbendpoint)