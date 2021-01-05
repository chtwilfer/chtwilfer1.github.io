---
title: New Azure Stack HCI (20H2) with Azure Kubernetes Service and Arc-enabled Data Service
date: 2020-11-24 10:12:56 +0100
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

![AKS on AzS HCI](/assets/images/AKS-on-HCI-1024x492.png)


## 

## Consistent with AKS in Azure

means that it is an "All-inclusive" Kubernetes platform. AKS ist easy to deploy. You can use the GUI of Windows Admin Center or Powershell. And you can leverage our existing skills.

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

![AKS WAC](/assets/images/AKS-WAC-1024x467.png)


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

![ARC Data Services](/assets/images/arcdataservices-1024x527.png)


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
