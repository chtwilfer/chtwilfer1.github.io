---

title: New Azure Stack HCI (20H2) with Azure Kubernetes Service and Arc-enabled Data Service
layout: single
categories:
  - Arc Data Service
  - Azure Kubernetes Service
  - Azure Stack HCI
tags:
  - Arc Data Services
  - Azure Kubernetes Service
  - Azure Stack HCI
---
**Azure Stack HCI** (20H2) and **Azure Kubernetes Service** (AKS) together brings the ability to keep your existing applications on-prem, but still use all the possibility of the cloud. Azure Stack HCI is registered to your Azure Subscription. This is also the reason why Azure is used for invoicing.

So let´s jump in the features and let me tell you what it is and when to use.


# What ist AKS on Azure Stack HCI?

Azure Kubernetes Service is an on-prem implementation, which automates running containerized applications at scale.

<img loading="lazy" class="aligncenter size-full wp-image-318" src="https://azurestack.info/wp-content/uploads/2020/11/AKS-on-HCI.png" alt="AKS on Azure Stack HCI" width="1167" height="561" srcset="https://azurestack.info/wp-content/uploads/2020/11/AKS-on-HCI.png 1167w, https://azurestack.info/wp-content/uploads/2020/11/AKS-on-HCI-300x144.png 300w, https://azurestack.info/wp-content/uploads/2020/11/AKS-on-HCI-1024x492.png 1024w, https://azurestack.info/wp-content/uploads/2020/11/AKS-on-HCI-768x369.png 768w" sizes="(max-width: 1167px) 100vw, 1167px" /> 

## 

## Consistent with AKS in Azure

means that it is an &#8220;All-inclusive&#8221; Kubernetes platform. AKS ist easy to deploy. You can use the GUI of Windows Admin Center or Powershell. And you can leverage our existing skills.

## Hybrid by design

means that AKS can be native integrated in Azure Arc. You pay what you use. In an Azure coonected mode ist is a consistent user experience. You can use the same codebase for AKS in Azure and AKS on Azure Stack HCI.

## Linux and Windows Containers

You can automatically manage Linux and Windows Containers in the same  Kubernetes Cluster.

## Built-in Security

Contianer Hostes are secured and serviced. And it is integrated in the Azure Security Ecosystem.


# Azure Stack HCI

Azure Stack HCI is a new hyperconverged infrastructure operating system that´s delivered as an Azure hybrid service.

  * new (Bare Metal) OS from Microsoft
  * no costs, automatically billed to your Azure Subscription
  * no seperate support number, use Azure Support in the Azure Portal
  * no version upgrade
  * continous feature updates



# Windows Admin Center

WAC is a locally deployed, browser-based app for managing Windows servers, cluster, hyerconverged infrastructure.

  * manage your Azure Stack HCI cluster
  * Deploy and manage your Azure Kubernetes cluster with an Azure Stack HCI Extension
  * Register Azure Stack HCI to Azure
  * Register AKS to Azure

<img loading="lazy" class="aligncenter size-full wp-image-321" src="https://azurestack.info/wp-content/uploads/2020/11/AKS-WAC.png" alt="aks-deployment" width="1047" height="478" srcset="https://azurestack.info/wp-content/uploads/2020/11/AKS-WAC.png 1047w, https://azurestack.info/wp-content/uploads/2020/11/AKS-WAC-300x137.png 300w, https://azurestack.info/wp-content/uploads/2020/11/AKS-WAC-1024x467.png 1024w, https://azurestack.info/wp-content/uploads/2020/11/AKS-WAC-768x351.png 768w" sizes="(max-width: 1047px) 100vw, 1047px" /> 

## 

## What happens during the Azure Stack HCI registration?

  * Create Azure AD app identity
  * establish certificates
  * creates Azure Resources
  * first sync

During syncronization some diagnostic data will be transmitted. So the Azure Stack HCI will keep secure, up-dated and working. No data, no configuration or content VM. no metadata and no names will be synchronized to Azure.

# Arc Data Services

Azure Arc makes it possible to run Azure data services on-premises, at the edge and in public clouds using Kubernetes and the infrastructure of your choice.

  * Always current
  * Elastic Scale
  * Unified Management
  * Integrated Security
  * Cloud Billing

<img loading="lazy" class="aligncenter size-full wp-image-323" src="https://azurestack.info/wp-content/uploads/2020/11/arcdataservices.png" alt="Arc Data Services" width="1152" height="593" srcset="https://azurestack.info/wp-content/uploads/2020/11/arcdataservices.png 1152w, https://azurestack.info/wp-content/uploads/2020/11/arcdataservices-300x154.png 300w, https://azurestack.info/wp-content/uploads/2020/11/arcdataservices-1024x527.png 1024w, https://azurestack.info/wp-content/uploads/2020/11/arcdataservices-768x395.png 768w" sizes="(max-width: 1152px) 100vw, 1152px" /> 



# Advantages

  * In combinition with Arc Data Services, Azure Kubernetes Service and Azure Stack HCI you can use SQL Managed Instances with scaling on Azure Stack HCI on-premises. Here is the [Link](https://docs.microsoft.com/en-us/azure/azure-arc/data/managed-instance-overview).
  * You can depoy Azure VMs or your VMs to your Azure Stack HCI.
  * With Azure Site Recovery you can use Azure for Disater Recovery.
  * Interate Azure Security on-premises.
  * Unified Management for On-Premises and Cloud
  * no Agent intallation for Azure Stack HCI or Azure Kubernetes Service

# Usefull links
Here are some interesting links for your Evaluation:

  * Register to [Azure Stack HCI](https://azure.microsoft.com/en-us/products/azure-stack/hci/hci-download/) Preview
  * Register to [AKS](https://azure.microsoft.com/de-de/products/azure-stack/hci/aks-download/) Preview
  * Register to [Arc Data Services](https://azure.microsoft.com/en-us/services/azure-arc/hybrid-data-services/) Preview
  * Azure Stack HCI [Evaluation Guide](https://github.com/Azure/AzureStackHCI-EvalGuide)
  * Microsoft / [WSLab](https://github.com/microsoft/WSLab/tree/master/Scenarios/AzSHCI%20and%20Kubernetes) for Evaluation
  * Microsoft Azure Stack HCI [Documentation](https://docs.microsoft.com/de-de/azure-stack/hci/overview)
  * Microsoft AKS on Azure Stack HCI [Documtention](https://docs.microsoft.com/de-de/azure-stack/aks-hci/)
  * Windows Admin Center [Documentation](https://docs.microsoft.com/en-us/windows-server/manage/windows-admin-center/overview)

# Evaluation

So if you want to test AKS on Azure Stack HCI there several possibilities. The first option is to use your own hyperconverged hardware with a minimum of two nodes. The second option ist to deploy an Azure VM with minimum of 64 GM RAM. Then use the Evaluation Guide from &#8220;Useful Links&#8221;. The third option is to deyploy a HCI Cluster with AKS on your own Notebook or PC.

So if you have questions you can come closer to me on LinkedIn, or Twitter.
