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

<img loading="lazy" class="alignnone size-medium wp-image-1525" src="http://techblog.twilfer.net/wp-content/uploads/2020/09/anf-more-parameters-300x135.png" alt="more parameters anf azure netapp files" width="300" height="135" srcset="http://techblog.twilfer.net/wp-content/uploads/2020/09/anf-more-parameters-300x135.png 300w, http://techblog.twilfer.net/wp-content/uploads/2020/09/anf-more-parameters-768x345.png 768w, http://techblog.twilfer.net/wp-content/uploads/2020/09/anf-more-parameters-500x224.png 500w, http://techblog.twilfer.net/wp-content/uploads/2020/09/anf-more-parameters.png 916w" sizes="(max-width: 300px) 100vw, 300px" /> 

## Install Modules

Later, the script checks whether all necessary Az Powershell modules are available and are up to date. If not, they will be downloaded and installed.

<img loading="lazy" class="alignnone size-medium wp-image-1526" src="http://techblog.twilfer.net/wp-content/uploads/2020/09/install-module-anf-300x59.png" alt="install module anf azure netapp files" width="300" height="59" srcset="http://techblog.twilfer.net/wp-content/uploads/2020/09/install-module-anf-300x59.png 300w, http://techblog.twilfer.net/wp-content/uploads/2020/09/install-module-anf-1024x202.png 1024w, http://techblog.twilfer.net/wp-content/uploads/2020/09/install-module-anf-768x152.png 768w, http://techblog.twilfer.net/wp-content/uploads/2020/09/install-module-anf-500x99.png 500w, http://techblog.twilfer.net/wp-content/uploads/2020/09/install-module-anf.png 1515w" sizes="(max-width: 300px) 100vw, 300px" /> 

## Connect to Azure

The next step is to connect to Azure and the subscription.

<img loading="lazy" class="alignnone size-medium wp-image-1527" src="http://techblog.twilfer.net/wp-content/uploads/2020/09/connect-to-azure-anf-300x96.png" alt="connect to azure anf azure netapp files" width="300" height="96" srcset="http://techblog.twilfer.net/wp-content/uploads/2020/09/connect-to-azure-anf-300x96.png 300w, http://techblog.twilfer.net/wp-content/uploads/2020/09/connect-to-azure-anf-1024x328.png 1024w, http://techblog.twilfer.net/wp-content/uploads/2020/09/connect-to-azure-anf-768x246.png 768w, http://techblog.twilfer.net/wp-content/uploads/2020/09/connect-to-azure-anf-1536x492.png 1536w, http://techblog.twilfer.net/wp-content/uploads/2020/09/connect-to-azure-anf-2048x656.png 2048w, http://techblog.twilfer.net/wp-content/uploads/2020/09/connect-to-azure-anf-500x160.png 500w" sizes="(max-width: 300px) 100vw, 300px" /> 

## ANF Deployment

The next block deploys the ANF and dependent resources, even in the 2nd location.

<img loading="lazy" class="alignnone size-medium wp-image-1528" src="http://techblog.twilfer.net/wp-content/uploads/2020/09/first-location-anf-290x300.png" alt="first location anf azure netapp files" width="290" height="300" srcset="http://techblog.twilfer.net/wp-content/uploads/2020/09/first-location-anf-290x300.png 290w, http://techblog.twilfer.net/wp-content/uploads/2020/09/first-location-anf-768x794.png 768w, http://techblog.twilfer.net/wp-content/uploads/2020/09/first-location-anf.png 898w" sizes="(max-width: 290px) 100vw, 290px" /> 

<img loading="lazy" class="alignnone size-medium wp-image-1529" src="http://techblog.twilfer.net/wp-content/uploads/2020/09/second-location-anf-300x269.png" alt="second location anf azure netapp files" width="300" height="269" srcset="http://techblog.twilfer.net/wp-content/uploads/2020/09/second-location-anf-300x269.png 300w, http://techblog.twilfer.net/wp-content/uploads/2020/09/second-location-anf-1024x920.png 1024w, http://techblog.twilfer.net/wp-content/uploads/2020/09/second-location-anf-768x690.png 768w, http://techblog.twilfer.net/wp-content/uploads/2020/09/second-location-anf-334x300.png 334w, http://techblog.twilfer.net/wp-content/uploads/2020/09/second-location-anf.png 1050w" sizes="(max-width: 300px) 100vw, 300px" /> 

If desired, a snapshot of a volume can still be performed.

<img loading="lazy" class="alignnone size-medium wp-image-1530" src="http://techblog.twilfer.net/wp-content/uploads/2020/09/snapshot-anf-300x297.png" alt="snapshot anf azure netapp files" width="300" height="297" srcset="http://techblog.twilfer.net/wp-content/uploads/2020/09/snapshot-anf-300x297.png 300w, http://techblog.twilfer.net/wp-content/uploads/2020/09/snapshot-anf-150x150.png 150w, http://techblog.twilfer.net/wp-content/uploads/2020/09/snapshot-anf-303x300.png 303w, http://techblog.twilfer.net/wp-content/uploads/2020/09/snapshot-anf.png 484w" sizes="(max-width: 300px) 100vw, 300px" /> 

## Delete Resources

Once all the resources have been deployed, there will be costs.  
So if this is not desired, simply delete the voluem. or the entire Resource Group.

<img loading="lazy" class="alignnone size-medium wp-image-1531" src="http://techblog.twilfer.net/wp-content/uploads/2020/09/delete-resource-anf-300x77.png" alt="delete resources anf azure netapp files" width="300" height="77" srcset="http://techblog.twilfer.net/wp-content/uploads/2020/09/delete-resource-anf-300x77.png 300w, http://techblog.twilfer.net/wp-content/uploads/2020/09/delete-resource-anf.png 411w" sizes="(max-width: 300px) 100vw, 300px" /> 

Either you start the script block by block, or alternatively you can start one line of Powershell and specify the individual parameter values after the script.

## For the deployment in one region

.\ANF-PoC-Deployment.ps1 -location westeurope -resourcegroup anfwe &#8211; anfaccountname anfwe -creationtoken anfwetest -subnetaddressprefix 10.3.2.0/24 -networkaddressprefix 10.3.0.0/16

# Other Deployment method

## For the deployment in two regions

.\ANF-PoC-Deployment.ps1 -location westeurope -resourcegroup anfwe -anfaccountname anfwe -creationtoken anfwetest -subnetaddressprefix 10.3.2.0/24 -networkaddressprefix 10.3.0.0/16 -secondlocation northeurope -secondresourcegroup anfne -secondanfaccountname anfne -secondcreationtoken anfnetest -secondsubnetaddressprefix 10.4.2.0/24 -secondnetworkaddressprefix 10.4.0.0/16

# The End

There is certainly a lot to improve on the script, but I am constantly working on it.  
Next I would try a deployment via ARM Templates.

_Hashtags: #AzureNetAppFiles #Azure #cloudmigration #datacenters #storage #data #cloudstorage #hybridcloud #NetApp #Microsoft #workloads #applications_
