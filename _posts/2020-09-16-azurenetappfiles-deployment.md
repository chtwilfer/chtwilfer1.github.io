---
id: 1524
title: One-Click Deployment for Azure NetApp Files (ANF)
date: 2020-09-16T12:21:00+01:00
author: AzureCris
layout: post
guid: http://techblog.twilfer.net/?p=1524
permalink: /azurenetappfiles-deployment
rank_math_internal_links_processed:
  - "1"
rank_math_permalink:
  - azurenetappfiles-deployment
rank_math_focus_keyword:
  - azure netapp files
rank_math_primary_category:
  - "85"
rank_math_seo_score:
  - "80"
rank_math_robots:
  - 'a:1:{i:0;s:5:"index";}'
rank_math_advanced_robots:
  - 'a:3:{s:11:"max-snippet";s:2:"-1";s:17:"max-video-preview";s:2:"-1";s:17:"max-image-preview";s:5:"large";}'
rank_math_rich_snippet:
  - article
rank_math_snippet_location:
  - custom
rank_math_snippet_article_type:
  - BlogPosting
rank_math_snippet_book_rating:
  - "0"
rank_math_snippet_book_rating_min:
  - "0"
rank_math_snippet_book_rating_max:
  - "0"
rank_math_snippet_book_editions:
  - 'a:1:{i:0;a:1:{s:11:"book_format";s:9:"Hardcover";}}'
rank_math_snippet_course_provider_type:
  - Organization
rank_math_snippet_course_rating:
  - "0"
rank_math_snippet_course_rating_min:
  - "0"
rank_math_snippet_course_rating_max:
  - "0"
rank_math_snippet_event_type:
  - Event
rank_math_snippet_event_attendance_mode:
  - offline
rank_math_snippet_event_performer_type:
  - Person
rank_math_snippet_event_price:
  - "0"
rank_math_snippet_event_inventory:
  - "0"
rank_math_snippet_event_rating:
  - "0"
rank_math_snippet_event_rating_min:
  - "0"
rank_math_snippet_event_rating_max:
  - "0"
rank_math_snippet_jobposting_unpublish:
  - 'on'
rank_math_snippet_music_type:
  - MusicGroup
rank_math_snippet_product_price:
  - "0"
rank_math_snippet_product_instock:
  - 'on'
rank_math_snippet_product_rating:
  - "0"
rank_math_snippet_product_rating_min:
  - "0"
rank_math_snippet_product_rating_max:
  - "0"
rank_math_snippet_recipe_rating:
  - "0"
rank_math_snippet_recipe_rating_min:
  - "0"
rank_math_snippet_recipe_rating_max:
  - "0"
rank_math_snippet_recipe_instruction_type:
  - SingleField
rank_math_snippet_review_worst_rating:
  - "1"
rank_math_snippet_review_best_rating:
  - "5"
rank_math_snippet_review_location:
  - bottom
rank_math_snippet_software_price:
  - "0"
rank_math_snippet_software_rating:
  - "0"
rank_math_snippet_software_rating_min:
  - "0"
rank_math_snippet_software_rating_max:
  - "0"
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
rank_math_schema_Article:
  - 'a:6:{s:5:"@type";s:11:"BlogPosting";s:8:"headline";s:11:"%seo_title%";s:13:"datePublished";s:20:"%date(Y-m-dTH:i:sP)%";s:12:"dateModified";s:24:"%modified(Y-m-dTH:i:sP)%";s:6:"author";a:2:{s:5:"@type";s:6:"Person";s:4:"name";s:9:"AzureCris";}s:8:"metadata";a:4:{s:5:"title";s:7:"Article";s:9:"isPrimary";b:1;s:4:"type";s:8:"template";s:14:"reviewLocation";s:6:"custom";}}'
rank_math_analytic_object_id:
  - "1"
categories:
  - Azure NetApp Files
  - Azure Automation
  - Powershell
tags:
  - Azure NetApp Files
---
<div id="ez-toc-container" class="ez-toc-v2_0_11 counter-hierarchy counter-decimal ez-toc-grey">
  <div class="ez-toc-title-container">
    <p class="ez-toc-title">
      Inhaltsverzeichnis
    </p>
    
    <span class="ez-toc-title-toggle"><a class="ez-toc-pull-right ez-toc-btn ez-toc-btn-xs ez-toc-btn-default ez-toc-toggle"><i class="ez-toc-glyphicon ez-toc-icon-toggle"></i></a></span>
  </div><nav>
  
  <ul class="ez-toc-list ez-toc-list-level-1">
    <li class="ez-toc-page-1 ez-toc-heading-level-1">
      <a class="ez-toc-link ez-toc-heading-1" href="http://techblog.twilfer.net/azurenetappfiles-deployment#General" title="General">General</a>
    </li>
    <li class="ez-toc-page-1 ez-toc-heading-level-1">
      <a class="ez-toc-link ez-toc-heading-2" href="http://techblog.twilfer.net/azurenetappfiles-deployment#Basic_requirements" title="Basic requirements">Basic requirements</a>
    </li>
    <li class="ez-toc-page-1 ez-toc-heading-level-1">
      <a class="ez-toc-link ez-toc-heading-3" href="http://techblog.twilfer.net/azurenetappfiles-deployment#The_Script" title="The Script">The Script</a><ul class="ez-toc-list-level-2">
        <li class="ez-toc-heading-level-2">
          <a class="ez-toc-link ez-toc-heading-4" href="http://techblog.twilfer.net/azurenetappfiles-deployment#More_Parameters" title="More Parameters">More Parameters</a>
        </li>
        <li class="ez-toc-page-1 ez-toc-heading-level-2">
          <a class="ez-toc-link ez-toc-heading-5" href="http://techblog.twilfer.net/azurenetappfiles-deployment#Install_Modules" title="Install Modules">Install Modules</a>
        </li>
        <li class="ez-toc-page-1 ez-toc-heading-level-2">
          <a class="ez-toc-link ez-toc-heading-6" href="http://techblog.twilfer.net/azurenetappfiles-deployment#Connect_to_Azure" title="Connect to Azure">Connect to Azure</a>
        </li>
        <li class="ez-toc-page-1 ez-toc-heading-level-2">
          <a class="ez-toc-link ez-toc-heading-7" href="http://techblog.twilfer.net/azurenetappfiles-deployment#ANF_Deployment" title="ANF Deployment">ANF Deployment</a>
        </li>
        <li class="ez-toc-page-1 ez-toc-heading-level-2">
          <a class="ez-toc-link ez-toc-heading-8" href="http://techblog.twilfer.net/azurenetappfiles-deployment#Delete_Resources" title="Delete Resources">Delete Resources</a>
        </li>
        <li class="ez-toc-page-1 ez-toc-heading-level-2">
          <a class="ez-toc-link ez-toc-heading-9" href="http://techblog.twilfer.net/azurenetappfiles-deployment#For_the_deployment_in_one_region" title="For the deployment in one region">For the deployment in one region</a>
        </li>
      </ul>
    </li>
    
    <li class="ez-toc-page-1 ez-toc-heading-level-1">
      <a class="ez-toc-link ez-toc-heading-10" href="http://techblog.twilfer.net/azurenetappfiles-deployment#Other_Deployment_method" title="Other Deployment method">Other Deployment method</a><ul class="ez-toc-list-level-2">
        <li class="ez-toc-heading-level-2">
          <a class="ez-toc-link ez-toc-heading-11" href="http://techblog.twilfer.net/azurenetappfiles-deployment#For_the_deployment_in_two_regions" title="For the deployment in two regions">For the deployment in two regions</a>
        </li>
      </ul>
    </li>
    
    <li class="ez-toc-page-1 ez-toc-heading-level-1">
      <a class="ez-toc-link ez-toc-heading-12" href="http://techblog.twilfer.net/azurenetappfiles-deployment#The_End" title="The End">The End</a>
    </li>
  </ul></nav>
</div>

# <span class="ez-toc-section" id="General"></span>General<span class="ez-toc-section-end"></span>

Azure NetApp Files (ANF for short) is no longer so new and has already proven in various projects where the advantages of this enterprise storage is.

In this blog entry, I want to talk less about the Use Cases. But give the proof-of-concept (PoC in short) the ability to simplify the ANF deployment,  
or via Powershell. Of course, you can do everything as usual via the Azure Portal (<a href="https://portal.azure.com" target="_blank" rel="nofollow noopener noreferrer">https://portal.azure.com</a>).

I have become accustomed to deploying ANF into the customer&#8217;s environment via Powershell for various PoC&#8217;s. For this reason, I would like to use my Powershellscript here for and explain in part.

# <span class="ez-toc-section" id="Basic_requirements"></span>Basic requirements<span class="ez-toc-section-end"></span>

  1. The first requirement to use ANF is to register the subscription for ANF. You can find the information in this article: <a href="https://aka.ms/azurenetappfiles" target="_blank" rel="noopener sponsored noreferrer">https://aka.ms/azurenetappfiles</a>
  2. Next, you should familiarize yourself with the documentation of ANF. Information can be found here: <a href="https://docs.microsoft.com/en-us/azure/azure-netapp-files/" target="_blank" rel="nofollow noopener noreferrer">https://docs.microsoft.com/en-us/azure/azure-netapp-files/</a>
  3. The next step is to download my Powershell Script from Github. You can find the script here: <a href="https://github.com/chtwilfer/AzureNetAppFiles" target="_blank" rel="noopener noreferrer">https://github.com/chtwilfer/AzureNetAppFiles</a>

# <span class="ez-toc-section" id="The_Script"></span>The Script<span class="ez-toc-section-end"></span>

Before we start the deployment a few words to the script.

The script expects various paramters for the deployment, which are requested after start. Things like Location, ResourceGroup Name, VNet & Subnet are queried.  
With this script, an ANF account, pool & volume with all associated resources is deployed in the West Europe & North Europe region. You can also use  
Snapshots for an existing volume. If you want to deploy ANF only in one region, you can deactivate the lines in the script for the 2nd region.

## <span class="ez-toc-section" id="More_Parameters"></span>More Parameters<span class="ez-toc-section-end"></span>

There are various parameters which I have entered firmly, but which can also be changed or adjusted as required.

<img loading="lazy" class="alignnone size-medium wp-image-1525" src="http://techblog.twilfer.net/wp-content/uploads/2020/09/anf-more-parameters-300x135.png" alt="more parameters anf azure netapp files" width="300" height="135" srcset="http://techblog.twilfer.net/wp-content/uploads/2020/09/anf-more-parameters-300x135.png 300w, http://techblog.twilfer.net/wp-content/uploads/2020/09/anf-more-parameters-768x345.png 768w, http://techblog.twilfer.net/wp-content/uploads/2020/09/anf-more-parameters-500x224.png 500w, http://techblog.twilfer.net/wp-content/uploads/2020/09/anf-more-parameters.png 916w" sizes="(max-width: 300px) 100vw, 300px" /> 

## <span class="ez-toc-section" id="Install_Modules"></span>Install Modules<span class="ez-toc-section-end"></span>

Later, the script checks whether all necessary Az Powershell modules are available and are up to date. If not, they will be downloaded and installed.

<img loading="lazy" class="alignnone size-medium wp-image-1526" src="http://techblog.twilfer.net/wp-content/uploads/2020/09/install-module-anf-300x59.png" alt="install module anf azure netapp files" width="300" height="59" srcset="http://techblog.twilfer.net/wp-content/uploads/2020/09/install-module-anf-300x59.png 300w, http://techblog.twilfer.net/wp-content/uploads/2020/09/install-module-anf-1024x202.png 1024w, http://techblog.twilfer.net/wp-content/uploads/2020/09/install-module-anf-768x152.png 768w, http://techblog.twilfer.net/wp-content/uploads/2020/09/install-module-anf-500x99.png 500w, http://techblog.twilfer.net/wp-content/uploads/2020/09/install-module-anf.png 1515w" sizes="(max-width: 300px) 100vw, 300px" /> 

## <span class="ez-toc-section" id="Connect_to_Azure"></span>Connect to Azure<span class="ez-toc-section-end"></span>

The next step is to connect to Azure and the subscription.

<img loading="lazy" class="alignnone size-medium wp-image-1527" src="http://techblog.twilfer.net/wp-content/uploads/2020/09/connect-to-azure-anf-300x96.png" alt="connect to azure anf azure netapp files" width="300" height="96" srcset="http://techblog.twilfer.net/wp-content/uploads/2020/09/connect-to-azure-anf-300x96.png 300w, http://techblog.twilfer.net/wp-content/uploads/2020/09/connect-to-azure-anf-1024x328.png 1024w, http://techblog.twilfer.net/wp-content/uploads/2020/09/connect-to-azure-anf-768x246.png 768w, http://techblog.twilfer.net/wp-content/uploads/2020/09/connect-to-azure-anf-1536x492.png 1536w, http://techblog.twilfer.net/wp-content/uploads/2020/09/connect-to-azure-anf-2048x656.png 2048w, http://techblog.twilfer.net/wp-content/uploads/2020/09/connect-to-azure-anf-500x160.png 500w" sizes="(max-width: 300px) 100vw, 300px" /> 

## <span class="ez-toc-section" id="ANF_Deployment"></span>ANF Deployment<span class="ez-toc-section-end"></span>

The next block deploys the ANF and dependent resources, even in the 2nd location.

<img loading="lazy" class="alignnone size-medium wp-image-1528" src="http://techblog.twilfer.net/wp-content/uploads/2020/09/first-location-anf-290x300.png" alt="first location anf azure netapp files" width="290" height="300" srcset="http://techblog.twilfer.net/wp-content/uploads/2020/09/first-location-anf-290x300.png 290w, http://techblog.twilfer.net/wp-content/uploads/2020/09/first-location-anf-768x794.png 768w, http://techblog.twilfer.net/wp-content/uploads/2020/09/first-location-anf.png 898w" sizes="(max-width: 290px) 100vw, 290px" /> 

<img loading="lazy" class="alignnone size-medium wp-image-1529" src="http://techblog.twilfer.net/wp-content/uploads/2020/09/second-location-anf-300x269.png" alt="second location anf azure netapp files" width="300" height="269" srcset="http://techblog.twilfer.net/wp-content/uploads/2020/09/second-location-anf-300x269.png 300w, http://techblog.twilfer.net/wp-content/uploads/2020/09/second-location-anf-1024x920.png 1024w, http://techblog.twilfer.net/wp-content/uploads/2020/09/second-location-anf-768x690.png 768w, http://techblog.twilfer.net/wp-content/uploads/2020/09/second-location-anf-334x300.png 334w, http://techblog.twilfer.net/wp-content/uploads/2020/09/second-location-anf.png 1050w" sizes="(max-width: 300px) 100vw, 300px" /> 

If desired, a snapshot of a volume can still be performed.

<img loading="lazy" class="alignnone size-medium wp-image-1530" src="http://techblog.twilfer.net/wp-content/uploads/2020/09/snapshot-anf-300x297.png" alt="snapshot anf azure netapp files" width="300" height="297" srcset="http://techblog.twilfer.net/wp-content/uploads/2020/09/snapshot-anf-300x297.png 300w, http://techblog.twilfer.net/wp-content/uploads/2020/09/snapshot-anf-150x150.png 150w, http://techblog.twilfer.net/wp-content/uploads/2020/09/snapshot-anf-303x300.png 303w, http://techblog.twilfer.net/wp-content/uploads/2020/09/snapshot-anf.png 484w" sizes="(max-width: 300px) 100vw, 300px" /> 

## <span class="ez-toc-section" id="Delete_Resources"></span>Delete Resources<span class="ez-toc-section-end"></span>

Once all the resources have been deployed, there will be costs.  
So if this is not desired, simply delete the voluem. or the entire Resource Group.

<img loading="lazy" class="alignnone size-medium wp-image-1531" src="http://techblog.twilfer.net/wp-content/uploads/2020/09/delete-resource-anf-300x77.png" alt="delete resources anf azure netapp files" width="300" height="77" srcset="http://techblog.twilfer.net/wp-content/uploads/2020/09/delete-resource-anf-300x77.png 300w, http://techblog.twilfer.net/wp-content/uploads/2020/09/delete-resource-anf.png 411w" sizes="(max-width: 300px) 100vw, 300px" /> 

Either you start the script block by block, or alternatively you can start one line of Powershell and specify the individual parameter values after the script.

## <span class="ez-toc-section" id="For_the_deployment_in_one_region"></span>For the deployment in one region<span class="ez-toc-section-end"></span>

.\ANF-PoC-Deployment.ps1 -location westeurope -resourcegroup anfwe &#8211; anfaccountname anfwe -creationtoken anfwetest -subnetaddressprefix 10.3.2.0/24 -networkaddressprefix 10.3.0.0/16

# <span class="ez-toc-section" id="Other_Deployment_method"></span>Other Deployment method<span class="ez-toc-section-end"></span>

## <span class="ez-toc-section" id="For_the_deployment_in_two_regions"></span>For the deployment in two regions<span class="ez-toc-section-end"></span>

.\ANF-PoC-Deployment.ps1 -location westeurope -resourcegroup anfwe &#8211; anfaccountname anfwe -creationtoken anfwetest -subnetaddressprefix 10.3.2.0/24 -networkaddressprefix 10.3.0.0/16 -secondlocation northeurope -secondresourcegroup anfne &#8211; secondanfaccountname anfne -secondcreationtoken anfnetest -secondsubnetaddressprefix 10.4.2.0/24 -secondnetworkaddressprefix 10.4.0.0/16

# <span class="ez-toc-section" id="The_End"></span>The End<span class="ez-toc-section-end"></span>

There is certainly a lot to improve on the script, but I&#8217;m constantly working on it.  
Next I would try a deployment via ARM Templates.

For more infromation about the Use Cases use this Link: <a href="http://techblog.twilfer.net/azure-netapp-files" target="_blank" rel="noopener noreferrer">http://techblog.twilfer.net/p/1455</a>

_Hashtags: #AzureNetAppFiles #Azure #cloudmigration #datacenters #storage #data #cloudstorage #hybridcloud #NetApp #Microsoft #workloads #applications_