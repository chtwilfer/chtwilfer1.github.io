---
title: One-Click Deployment for Azure NetApp Files (ANF)
date: 2020-09-16T12:21:00+01:00
layout: single
categories:
  - Azure NetApp Files
  - Azure Automation
  - Powershell
tags:
  - Azure NetApp Files
  - Azure Automation
  - Powershell
---

**Azure NetApp Files** (ANF for short) is no longer so new and has already proven in various projects where the advantages of this enterprise storage is.

In this blog entry, I want to talk less about the Use Cases. But give the proof-of-concept (PoC in short) the ability to simplify the ANF deployment,  
or via Powershell. Of course, you can do everything as usual via the Azure Portal (<a href="https://portal.azure.com" target="_blank" rel="nofollow noopener noreferrer">https://portal.azure.com</a>).

I have become accustomed to deploying ANF into the customer&#8217;s environment via Powershell for various PoC&#8217;s. For this reason, I would like to use my Powershellscript here for and explain in part.

# Basic requirements

  1. The first requirement to use ANF is to register the subscription for ANF. You can find the information in this article: <a href="https://aka.ms/azurenetappfiles" target="_blank" rel="noopener sponsored noreferrer">https://aka.ms/azurenetappfiles</a>
  2. Next, you should familiarize yourself with the documentation of ANF. Information can be found here: <a href="https://docs.microsoft.com/en-us/azure/azure-netapp-files/" target="_blank" rel="nofollow noopener noreferrer">https://docs.microsoft.com/en-us/azure/azure-netapp-files/</a>
  3. The next step is to download my Powershell Script from Github. You can find the script here: <a href="https://github.com/chtwilfer/AzureNetAppFiles" target="_blank" rel="noopener noreferrer">https://github.com/chtwilfer/AzureNetAppFiles</a>

# The Script
Before we start the deployment a few words to the script.

The script expects various paramters for the deployment, which are requested after start. Things like Location, ResourceGroup Name, VNet & Subnet are queried.  
With this script, an ANF account, pool & volume with all associated resources is deployed in the West Europe & North Europe region. You can also use  
Snapshots for an existing volume. If you want to deploy ANF only in one region, you can deactivate the lines in the script for the 2nd region.

## More Parameters

There are various parameters which I have entered firmly, but which can also be changed or adjusted as required.

![ANF More Parameters](/assets/images/anf-more-parameters-768x345.png)


## Install Modules

Later, the script checks whether all necessary Az Powershell modules are available and are up to date. If not, they will be downloaded and installed.

![Install Module ANF](/assets/images/install-module-anf-768x152.png)


## Connect to Azure

The next step is to connect to Azure and the subscription.

![Connect to Azure](/assets/images/connect-to-azure-anf-1536x492.png)


## ANF Deployment

The next block deploys the ANF and dependent resources, even in the 2nd location.

![First Location](/assets/images/first-location-anf-768x794.png)


![Second Location](/assets/images/second-location-anf-768x690.png)


If desired, a snapshot of a volume can still be performed.

![Snapshot ANF](/assets/images/snapshot-anf-300x297.png)


## Delete Resources

Once all the resources have been deployed, there will be costs.  
So if this is not desired, simply delete the voluem. or the entire Resource Group.

![Delete Ressources ANF](/assets/images/delete-resource-anf.png)


Either you start the script block by block, or alternatively you can start one line of Powershell and specify the individual parameter values after the script.

## For the deployment in one region

.\ANF-PoC-Deployment.ps1 
  -location westeurope 
  -resourcegroup anfwe 
  -anfaccountname anfwe 
  -creationtoken anfwetest 
  -subnetaddressprefix 10.3.2.0/24 
  -networkaddressprefix 10.3.0.0/16

# Other Deployment method

## For the deployment in two regions

.\ANF-PoC-Deployment.ps1 
  -location westeurope 
  -resourcegroup anfwe 
  -anfaccountname anfwe 
  -creationtoken anfwetest 
  -subnetaddressprefix 10.3.2.0/24 
  -networkaddressprefix 10.3.0.0/16 
  -secondlocation northeurope 
  -secondresourcegroup anfne 
  -secondanfaccountname anfne 
  -secondcreationtoken anfnetest 
  -secondsubnetaddressprefix 10.4.2.0/24 
  -secondnetworkaddressprefix 10.4.0.0/16

# The End

There is certainly a lot to improve on the script, but I am constantly working on it.  
Next I would try a deployment via ARM Templates.

Hashtags: #AzureNetAppFiles #Azure #cloudmigration #datacenters #storage #data #cloudstorage #hybridcloud #NetApp #Microsoft #workloads #applications_
