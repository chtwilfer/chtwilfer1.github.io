---
id: 304
title: New Azure Stack HCI (20H2) with Azure Kubernetes Service and Arc-enabled Data Service
date: 2020-11-24T10:12:56+01:00
author: Mr.AzureStack
layout: post
guid: https://azurestack.info/?p=304
permalink: /aks-on-azure-stack-hci
rank_math_internal_links_processed:
  - "1"
rank_math_permalink:
  - aks-on-azure-stack-hci
rank_math_focus_keyword:
  - azure stack hci
rank_math_primary_category:
  - "0"
rank_math_seo_score:
  - "81"
rank_math_robots:
  - 'a:1:{i:0;s:5:"index";}'
rank_math_advanced_robots:
  - 'a:3:{s:11:"max-snippet";s:2:"-1";s:17:"max-video-preview";s:2:"-1";s:17:"max-image-preview";s:5:"large";}'
rank_math_facebook_enable_image_overlay:
  - 'off'
rank_math_facebook_image_overlay:
  - play
rank_math_twitter_use_facebook:
  - 'on'
rank_math_twitter_card_type:
  - summary_large_image
rank_math_twitter_enable_image_overlay:
  - 'off'
rank_math_twitter_image_overlay:
  - play
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

<div id="ez-toc-container" class="ez-toc-v2_0_11 counter-hierarchy counter-decimal ez-toc-grey">
  <div class="ez-toc-title-container">
    <p class="ez-toc-title">
      Table of content
    </p>
    
    <span class="ez-toc-title-toggle"><a class="ez-toc-pull-right ez-toc-btn ez-toc-btn-xs ez-toc-btn-default ez-toc-toggle"><i class="ez-toc-glyphicon ez-toc-icon-toggle"></i></a></span>
  </div><nav>
  
  <ul class="ez-toc-list ez-toc-list-level-1">
    <li class="ez-toc-page-1 ez-toc-heading-level-1">
      <a class="ez-toc-link ez-toc-heading-1" href="https://azurestack.info/aks-on-azure-stack-hci#What_ist_AKS_on_Azure_Stack_HCI" title="What ist AKS on Azure Stack HCI?">What ist AKS on Azure Stack HCI?</a><ul class="ez-toc-list-level-2">
        <li class="ez-toc-heading-level-2">
          <a class="ez-toc-link ez-toc-heading-2" href="https://azurestack.info/aks-on-azure-stack-hci#Consistent_with_AKS_in_Azure" title="Consistent with AKS in Azure">Consistent with AKS in Azure</a>
        </li>
        <li class="ez-toc-page-1 ez-toc-heading-level-2">
          <a class="ez-toc-link ez-toc-heading-3" href="https://azurestack.info/aks-on-azure-stack-hci#Hybrid_by_design" title="Hybrid by design">Hybrid by design</a>
        </li>
        <li class="ez-toc-page-1 ez-toc-heading-level-2">
          <a class="ez-toc-link ez-toc-heading-4" href="https://azurestack.info/aks-on-azure-stack-hci#Linux_and_Windows_Containers" title="Linux and Windows Containers">Linux and Windows Containers</a>
        </li>
        <li class="ez-toc-page-1 ez-toc-heading-level-2">
          <a class="ez-toc-link ez-toc-heading-5" href="https://azurestack.info/aks-on-azure-stack-hci#Builtin_Security" title="Built-in Security">Built-in Security</a>
        </li>
      </ul>
    </li>
    
    <li class="ez-toc-page-1 ez-toc-heading-level-1">
      <a class="ez-toc-link ez-toc-heading-6" href="https://azurestack.info/aks-on-azure-stack-hci#Azure_Stack_HCI" title="Azure Stack HCI">Azure Stack HCI</a>
    </li>
    <li class="ez-toc-page-1 ez-toc-heading-level-1">
      <a class="ez-toc-link ez-toc-heading-7" href="https://azurestack.info/aks-on-azure-stack-hci#Windows_Admin_Center" title="Windows Admin Center">Windows Admin Center</a><ul class="ez-toc-list-level-2">
        <li class="ez-toc-heading-level-2">
          <a class="ez-toc-link ez-toc-heading-8" href="https://azurestack.info/aks-on-azure-stack-hci#What_happens_during_the_Azure_Stack_HCI_registration" title="What happens during the Azure Stack HCI registration?">What happens during the Azure Stack HCI registration?</a>
        </li>
      </ul>
    </li>
    
    <li class="ez-toc-page-1 ez-toc-heading-level-1">
      <a class="ez-toc-link ez-toc-heading-9" href="https://azurestack.info/aks-on-azure-stack-hci#Arc_Data_Services" title="Arc Data Services">Arc Data Services</a>
    </li>
    <li class="ez-toc-page-1 ez-toc-heading-level-1">
      <a class="ez-toc-link ez-toc-heading-10" href="https://azurestack.info/aks-on-azure-stack-hci#Advantages" title="Advantages">Advantages</a>
    </li>
    <li class="ez-toc-page-1 ez-toc-heading-level-1">
      <a class="ez-toc-link ez-toc-heading-11" href="https://azurestack.info/aks-on-azure-stack-hci#Usefull_links" title="Usefull links">Usefull links</a>
    </li>
    <li class="ez-toc-page-1 ez-toc-heading-level-1">
      <a class="ez-toc-link ez-toc-heading-12" href="https://azurestack.info/aks-on-azure-stack-hci#Evaluation" title="Evaluation">Evaluation</a>
    </li>
  </ul></nav>
</div>

# <span class="ez-toc-section" id="What_ist_AKS_on_Azure_Stack_HCI"></span>What ist AKS on Azure Stack HCI?<span class="ez-toc-section-end"></span>

Azure Kubernetes Service is an on-prem implementation, which automates running containerized applications at scale.

<li style="list-style-type: none;">
</li>

<img loading="lazy" class="aligncenter size-full wp-image-318" src="https://azurestack.info/wp-content/uploads/2020/11/AKS-on-HCI.png" alt="AKS on Azure Stack HCI" width="1167" height="561" srcset="https://azurestack.info/wp-content/uploads/2020/11/AKS-on-HCI.png 1167w, https://azurestack.info/wp-content/uploads/2020/11/AKS-on-HCI-300x144.png 300w, https://azurestack.info/wp-content/uploads/2020/11/AKS-on-HCI-1024x492.png 1024w, https://azurestack.info/wp-content/uploads/2020/11/AKS-on-HCI-768x369.png 768w" sizes="(max-width: 1167px) 100vw, 1167px" /> 

## 

## <span class="ez-toc-section" id="Consistent_with_AKS_in_Azure"></span>Consistent with AKS in Azure<span class="ez-toc-section-end"></span>

means that it is an &#8220;All-inclusive&#8221; Kubernetes platform. AKS ist easy to deploy. You can use the GUI of Windows Admin Center or Powershell. And you can leverage our existing skills.

## <span class="ez-toc-section" id="Hybrid_by_design"></span>Hybrid by design<span class="ez-toc-section-end"></span>

means that AKS can be native integrated in Azure Arc. You pay what you use. In an Azure coonected mode ist is a consistent user experience. You can use the same codebase for AKS in Azure and AKS on Azure Stack HCI.

## <span class="ez-toc-section" id="Linux_and_Windows_Containers"></span>Linux and Windows Containers<span class="ez-toc-section-end"></span>

You can automatically manage Linux and Windows Containers in the same  Kubernetes Cluster.

## <span class="ez-toc-section" id="Builtin_Security"></span>Built-in Security<span class="ez-toc-section-end"></span>

Contianer Hostes are secured and serviced. And it is integrated in the Azure Security Ecosystem.

&nbsp;

# <span class="ez-toc-section" id="Azure_Stack_HCI"></span>Azure Stack HCI<span class="ez-toc-section-end"></span>

Azure Stack HCI is a new hyperconverged infrastructure operating system that´s delivered as an Azure hybrid service.

  * new (Bare Metal) OS from Microsoft
  * no costs, automatically billed to your Azure Subscription
  * no seperate support number, use Azure Support in the Azure Portal
  * no version upgrade
  * continous feature updates

&nbsp;

# <span class="ez-toc-section" id="Windows_Admin_Center"></span>Windows Admin Center<span class="ez-toc-section-end"></span>

WAC is a locally deployed, browser-based app for managing Windows servers, cluster, hyerconverged infrastructure.

  * manage your Azure Stack HCI cluster
  * Deploy and manage your Azure Kubernetes cluster with an Azure Stack HCI Extension
  * Register Azure Stack HCI to Azure
  * Register AKS to Azure

<img loading="lazy" class="aligncenter size-full wp-image-321" src="https://azurestack.info/wp-content/uploads/2020/11/AKS-WAC.png" alt="aks-deployment" width="1047" height="478" srcset="https://azurestack.info/wp-content/uploads/2020/11/AKS-WAC.png 1047w, https://azurestack.info/wp-content/uploads/2020/11/AKS-WAC-300x137.png 300w, https://azurestack.info/wp-content/uploads/2020/11/AKS-WAC-1024x467.png 1024w, https://azurestack.info/wp-content/uploads/2020/11/AKS-WAC-768x351.png 768w" sizes="(max-width: 1047px) 100vw, 1047px" /> 

## 

## <span class="ez-toc-section" id="What_happens_during_the_Azure_Stack_HCI_registration"></span>What happens during the Azure Stack HCI registration?<span class="ez-toc-section-end"></span>

  * Create Azure AD app identity
  * establish certificates
  * creates Azure Resources
  * first sync

During syncronization some diagnostic data will be transmitted. So the Azure Stack HCI will keep secure, up-dated and working. No data, no configuration or content VM. no metadata and no names will be synchronized to Azure.

# <span class="ez-toc-section" id="Arc_Data_Services"></span>Arc Data Services<span class="ez-toc-section-end"></span>

Azure Arc makes it possible to run Azure data services on-premises, at the edge and in public clouds using Kubernetes and the infrastructure of your choice.

  * Always current
  * Elastic Scale
  * Unified Management
  * Integrated Security
  * Cloud Billing

<img loading="lazy" class="aligncenter size-full wp-image-323" src="https://azurestack.info/wp-content/uploads/2020/11/arcdataservices.png" alt="Arc Data Services" width="1152" height="593" srcset="https://azurestack.info/wp-content/uploads/2020/11/arcdataservices.png 1152w, https://azurestack.info/wp-content/uploads/2020/11/arcdataservices-300x154.png 300w, https://azurestack.info/wp-content/uploads/2020/11/arcdataservices-1024x527.png 1024w, https://azurestack.info/wp-content/uploads/2020/11/arcdataservices-768x395.png 768w" sizes="(max-width: 1152px) 100vw, 1152px" /> 

&nbsp;

# <span class="ez-toc-section" id="Advantages"></span>Advantages<span class="ez-toc-section-end"></span>

  * In combinition with Arc Data Services, Azure Kubernetes Service and Azure Stack HCI you can use SQL Managed Instances with scaling on Azure Stack HCI on-premises. Here is the [Link](https://docs.microsoft.com/en-us/azure/azure-arc/data/managed-instance-overview).
  * You can depoy Azure VMs or your VMs to your Azure Stack HCI.
  * With Azure Site Recovery you can use Azure for Disater Recovery.
  * Interate Azure Security on-premises.
  * Unified Management for On-Premises and Cloud
  * no Agent intallation for Azure Stack HCI or Azure Kubernetes Service

# <span class="ez-toc-section" id="Usefull_links"></span>Usefull links<span class="ez-toc-section-end"></span>

Here are some interesting links for your Evaluation:

  * Register to [Azure Stack HCI](https://azure.microsoft.com/en-us/products/azure-stack/hci/hci-download/) Preview
  * Register to [AKS](https://azure.microsoft.com/de-de/products/azure-stack/hci/aks-download/) Preview
  * Register to [Arc Data Services](https://azure.microsoft.com/en-us/services/azure-arc/hybrid-data-services/) Preview
  * Azure Stack HCI [Evaluation Guide](https://github.com/Azure/AzureStackHCI-EvalGuide)
  * Microsoft / [WSLab](https://github.com/microsoft/WSLab/tree/master/Scenarios/AzSHCI%20and%20Kubernetes) for Evaluation
  * Microsoft Azure Stack HCI [Documentation](https://docs.microsoft.com/de-de/azure-stack/hci/overview)
  * Microsoft AKS on Azure Stack HCI [Documtention](https://docs.microsoft.com/de-de/azure-stack/aks-hci/)
  * Windows Admin Center [Documentation](https://docs.microsoft.com/en-us/windows-server/manage/windows-admin-center/overview)

# <span class="ez-toc-section" id="Evaluation"></span>Evaluation<span class="ez-toc-section-end"></span>

So if you want to test AKS on Azure Stack HCI there several possibilities. The first option is to use your own hyperconverged hardware with a minimum of two nodes. The second option ist to deploy an Azure VM with minimum of 64 GM RAM. Then use the Evaluation Guide from &#8220;Useful Links&#8221;. The third option is to deyploy a HCI Cluster with AKS on your own Notebook or PC.

So if you have questions you can come closer to me on LinkedIn, or Twitter.

<div class='sfsi_Sicons' style='width: 100%; display: inline-block; vertical-align: middle; text-align:left'>
  <div style='margin:0px 8px 0px 0px; line-height: 24px'>
    <span>Please follow and like us:</span>
  </div>
  
  <div class='sfsi_socialwpr'>
    <div class='sf_fb sf_icon' style='text-align:left;vertical-align: middle;'>
      <div class="fb-like" data-href="https://azurestack.info/aks-on-azure-stack-hci?type=jekyll"  data-send="false" data-layout="button" >
      </div>
    </div>
    
    <div class='sf_fb_share sf_icon' style='text-align:left;vertical-align: middle;'>
      <a href='https://www.facebook.com/sharer/sharer.php?u=https%3A%2F%2Fazurestack.info%2Faks-on-azure-stack-hci%3Ftype%3Djekyll' style='display:inline-block;'  > <img class='sfsi_wicon'  data-pin-nopin='true' width='auto' height='auto' alt='fb-share-icon' title='Facebook Share' src='https://azurestack.info/wp-content/plugins/ultimate-social-media-icons/images/visit_icons/fbshare_bck.png' /></a>
    </div>
    
    <div class='sf_twiter sf_icon' style='display: inline-block;vertical-align: middle;width: auto;margin-left: 7px;'>
      <a target='_blank' href='https://twitter.com/intent/tweet?text=New+Azure+Stack+HCI+%2820H2%29+with+Azure+Kubernetes+Service+and+Arc-enabled+Data+Service+https://azurestack.info/aks-on-azure-stack-hci?type=jekyll'style='display:inline-block' > <img data-pin-nopin= true width='auto' class='sfsi_wicon' src='https://azurestack.info/wp-content/plugins/ultimate-social-media-icons/images/visit_icons/en_US_Tweet.svg' alt='Tweet' title='Tweet' > </a>
    </div>
  </div>
</div>