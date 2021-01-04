---
id: 167
title: 'Microsoft Azure Stack Development Kit &#8211; new Region Name in parallel operation with several ASDKs'
date: 2019-08-19T11:53:16+01:00
author: Mr.AzureStack
layout: post
guid: http://azurestack.info/?p=167
permalink: /microsoft-azure-stack-development-kit-new-region-name-in-parallel-operation-with-several-asdks
rank_math_internal_links_processed:
  - "1"
rank_math_title:
  - '%title% %sep% %sitename%'
rank_math_permalink:
  - microsoft-azure-stack-development-kit-new-region-name-in-parallel-operation-with-several-asdks
rank_math_focus_keyword:
  - azure stack development kit
rank_math_primary_category:
  - "0"
rank_math_seo_score:
  - "63"
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
rank_math_snippet_book_rating_min:
  - "1"
rank_math_snippet_book_rating_max:
  - "5"
rank_math_snippet_book_editions:
  - 'a:1:{i:0;a:1:{s:11:"book_format";s:9:"Hardcover";}}'
rank_math_snippet_course_provider_type:
  - Organization
rank_math_snippet_course_rating_min:
  - "1"
rank_math_snippet_course_rating_max:
  - "5"
rank_math_snippet_event_type:
  - Event
rank_math_snippet_event_attendance_mode:
  - offline
rank_math_snippet_event_performer_type:
  - Person
rank_math_snippet_event_rating_min:
  - "1"
rank_math_snippet_event_rating_max:
  - "5"
rank_math_snippet_jobposting_unpublish:
  - 'on'
rank_math_snippet_music_type:
  - MusicGroup
rank_math_snippet_product_instock:
  - 'on'
rank_math_snippet_product_rating_min:
  - "1"
rank_math_snippet_product_rating_max:
  - "5"
rank_math_snippet_recipe_rating_min:
  - "1"
rank_math_snippet_recipe_rating_max:
  - "5"
rank_math_snippet_recipe_instruction_type:
  - SingleField
rank_math_snippet_review_worst_rating:
  - "1"
rank_math_snippet_review_best_rating:
  - "5"
rank_math_snippet_review_location:
  - bottom
rank_math_snippet_software_rating_min:
  - "1"
rank_math_snippet_software_rating_max:
  - "5"
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
rank_math_pillar_content:
  - 'on'
rank_math_schema_Article:
  - 'a:6:{s:5:"@type";s:11:"BlogPosting";s:8:"headline";s:11:"%seo_title%";s:13:"datePublished";s:20:"%date(Y-m-dTH:i:sP)%";s:12:"dateModified";s:24:"%modified(Y-m-dTH:i:sP)%";s:6:"author";a:2:{s:5:"@type";s:6:"Person";s:4:"name";s:13:"Mr.AzureStack";}s:8:"metadata";a:4:{s:5:"title";s:7:"Article";s:9:"isPrimary";b:1;s:4:"type";s:8:"template";s:14:"reviewLocation";s:6:"custom";}}'
rank_math_analytic_object_id:
  - "6"
categories:
  - Architektur
  - Azure Stack Development Kit
  - Azure Stack Hub
  - AzureStack
  - Grundlagen
  - Infrastructure-as-a-Service
  - Plattform-as-a-Service
tags:
  - Azure Stack
  - Azure Stack Hub
  - Grundlagen
---
In various customer discussions, it emerged that a single Azure Stack Development Kit (ASDK) did not correspond to the desired test scenarios. Especially since new ASDK versions should be deployed at regular intervals due to updates (monthly).  
This customer scenario is exclusively an ASDK system, which is located in the customer&#8217;s internal network. However, there is certainly also a possibility to set up the system in such a way that it can be used by Managed Service Providers.

This gave us the idea to get more involved with the network configuration of the ASDK and, if possible, to make changes to it. Because if one speaks of a parallel operation of ASDKs, then one also talks about Tenant VPN access. The review of various blog posts on the net did not lead to the desired customer request.

Customer wishes were defined in the following form:  
&#8211; several ASDKs in the same network  
&#8211; Different configurations of the ASDKs  
&#8211; Connected and Disconnected Mode  
&#8211; with and without App Services  
&#8211; with Kubernetes  
&#8211; with and without AD FS and AAD  
&#8211; Access from the customer&#8217;s local network with various Clients

&nbsp;

<img loading="lazy" class="aligncenter size-large wp-image-193" src="https://azurestack.info/wp-content/uploads/2019/08/ASDK1_1-1024x542.jpg" alt="" width="1024" height="542" srcset="https://azurestack.info/wp-content/uploads/2019/08/ASDK1_1-1024x542.jpg 1024w, https://azurestack.info/wp-content/uploads/2019/08/ASDK1_1-300x159.jpg 300w, https://azurestack.info/wp-content/uploads/2019/08/ASDK1_1-768x407.jpg 768w, https://azurestack.info/wp-content/uploads/2019/08/ASDK1_1.jpg 2048w" sizes="(max-width: 1024px) 100vw, 1024px" /> 

&nbsp;

&nbsp;

<img loading="lazy" class="aligncenter size-large wp-image-194" src="https://azurestack.info/wp-content/uploads/2019/08/ASDK2_1-1024x514.jpg" alt="" width="1024" height="514" srcset="https://azurestack.info/wp-content/uploads/2019/08/ASDK2_1-1024x514.jpg 1024w, https://azurestack.info/wp-content/uploads/2019/08/ASDK2_1-300x151.jpg 300w, https://azurestack.info/wp-content/uploads/2019/08/ASDK2_1-768x386.jpg 768w, https://azurestack.info/wp-content/uploads/2019/08/ASDK2_1.jpg 2048w" sizes="(max-width: 1024px) 100vw, 1024px" /> 

&nbsp;

With Powershell, we were able to adapt the Config XML of the ASDK to the desired customer scenarios. It is important to know that an ASDK has 62 IP addresses available, from which 31 IP addresses are already subtracted by the pure installation. Each additional resource provider installation requires IP addresses from this pool. There&#8217;s not much left in the end. With the well known subnetting you can get the desired result here.

&nbsp;

<img loading="lazy" class="aligncenter size-large wp-image-195" src="https://azurestack.info/wp-content/uploads/2019/08/ASDK3_1-1024x558.jpg" alt="" width="1024" height="558" srcset="https://azurestack.info/wp-content/uploads/2019/08/ASDK3_1-1024x558.jpg 1024w, https://azurestack.info/wp-content/uploads/2019/08/ASDK3_1-300x163.jpg 300w, https://azurestack.info/wp-content/uploads/2019/08/ASDK3_1-768x418.jpg 768w, https://azurestack.info/wp-content/uploads/2019/08/ASDK3_1.jpg 2048w" sizes="(max-width: 1024px) 100vw, 1024px" /> 

&nbsp;

In the next step, additional parameter values are added to the InstallPOC. ps1 script in the front section of the parameters. These serve to adapt the region names of the respective ASDKs. E. g. from &#8220;local&#8221;; to &#8220;hamburg&#8221;; or &#8220;RZ1&#8221;. The decision lies in the customer configuration in which the ASDks are added.

&nbsp;

<img loading="lazy" class="aligncenter size-large wp-image-196" src="https://azurestack.info/wp-content/uploads/2019/08/ASDK4_1-1024x501.jpg" alt="" width="1024" height="501" srcset="https://azurestack.info/wp-content/uploads/2019/08/ASDK4_1-1024x501.jpg 1024w, https://azurestack.info/wp-content/uploads/2019/08/ASDK4_1-300x147.jpg 300w, https://azurestack.info/wp-content/uploads/2019/08/ASDK4_1-768x376.jpg 768w, https://azurestack.info/wp-content/uploads/2019/08/ASDK4_1.jpg 2048w" sizes="(max-width: 1024px) 100vw, 1024px" /> 

&nbsp;

Since the ASDK has now adapted the RegionName, the custom DomainSuffix must also be specified if a Post Deploymennt is used for the installation of App Services (Script Matt McSpirit). It is the same name as the RegionName of the ASDK.

&nbsp;

<img loading="lazy" class="aligncenter size-large wp-image-197" src="https://azurestack.info/wp-content/uploads/2019/08/ASDK5_1-1024x608.jpg" alt="" width="1024" height="608" srcset="https://azurestack.info/wp-content/uploads/2019/08/ASDK5_1-1024x608.jpg 1024w, https://azurestack.info/wp-content/uploads/2019/08/ASDK5_1-300x178.jpg 300w, https://azurestack.info/wp-content/uploads/2019/08/ASDK5_1-768x456.jpg 768w, https://azurestack.info/wp-content/uploads/2019/08/ASDK5_1.jpg 2048w" sizes="(max-width: 1024px) 100vw, 1024px" /> 

&nbsp;

Since the network IP address range of the ASDK has been adapted, it must also be adapted either in the firewall, or the router where the various ASDKs are located. Just like setting up or configuring a DNS delegation.

&nbsp;

<img loading="lazy" class="aligncenter size-large wp-image-198" src="https://azurestack.info/wp-content/uploads/2019/08/ASDK6_1-1024x556.jpg" alt="" width="1024" height="556" srcset="https://azurestack.info/wp-content/uploads/2019/08/ASDK6_1-1024x556.jpg 1024w, https://azurestack.info/wp-content/uploads/2019/08/ASDK6_1-300x163.jpg 300w, https://azurestack.info/wp-content/uploads/2019/08/ASDK6_1-768x417.jpg 768w, https://azurestack.info/wp-content/uploads/2019/08/ASDK6_1.jpg 2048w" sizes="(max-width: 1024px) 100vw, 1024px" /> 

&nbsp;

The last hurdle is importing the ASDK certificates to all clients interacting with the systems.

&nbsp;

<img loading="lazy" class="aligncenter size-large wp-image-199" src="https://azurestack.info/wp-content/uploads/2019/08/ASDK7_1-1024x525.jpg" alt="" width="1024" height="525" srcset="https://azurestack.info/wp-content/uploads/2019/08/ASDK7_1-1024x525.jpg 1024w, https://azurestack.info/wp-content/uploads/2019/08/ASDK7_1-300x154.jpg 300w, https://azurestack.info/wp-content/uploads/2019/08/ASDK7_1-768x394.jpg 768w, https://azurestack.info/wp-content/uploads/2019/08/ASDK7_1.jpg 2048w" sizes="(max-width: 1024px) 100vw, 1024px" /> 

&nbsp;

&nbsp;

The way to this overall configuration was not an easy one, but the time invested was worth it. This makes it possible to provide customers with differently configured systems for a Proof-of-Concept (PoC). The total running time of the PoC may also be reduced in the positive decision towards the Azure Stack Integrated System.

Questions, suggestions and wishes are very welcome.

<div class='sfsi_Sicons' style='width: 100%; display: inline-block; vertical-align: middle; text-align:left'>
  <div style='margin:0px 8px 0px 0px; line-height: 24px'>
    <span>Please follow and like us:</span>
  </div>
  
  <div class='sfsi_socialwpr'>
    <div class='sf_fb sf_icon' style='text-align:left;vertical-align: middle;'>
      <div class="fb-like" data-href="https://azurestack.info/microsoft-azure-stack-development-kit-new-region-name-in-parallel-operation-with-several-asdks?type=jekyll"  data-send="false" data-layout="button" >
      </div>
    </div>
    
    <div class='sf_fb_share sf_icon' style='text-align:left;vertical-align: middle;'>
      <a href='https://www.facebook.com/sharer/sharer.php?u=https%3A%2F%2Fazurestack.info%2Fmicrosoft-azure-stack-development-kit-new-region-name-in-parallel-operation-with-several-asdks%3Ftype%3Djekyll' style='display:inline-block;'  > <img class='sfsi_wicon'  data-pin-nopin='true' width='auto' height='auto' alt='fb-share-icon' title='Facebook Share' src='https://azurestack.info/wp-content/plugins/ultimate-social-media-icons/images/visit_icons/fbshare_bck.png' /></a>
    </div>
    
    <div class='sf_twiter sf_icon' style='display: inline-block;vertical-align: middle;width: auto;margin-left: 7px;'>
      <a target='_blank' href='https://twitter.com/intent/tweet?text=Microsoft+Azure+Stack+Development+Kit+%26%238211%3B+new+Region+Name+in+parallel+operation+with+several+ASDKs+https://azurestack.info/microsoft-azure-stack-development-kit-new-region-name-in-parallel-operation-with-several-asdks?type=jekyll'style='display:inline-block' > <img data-pin-nopin= true width='auto' class='sfsi_wicon' src='https://azurestack.info/wp-content/plugins/ultimate-social-media-icons/images/visit_icons/en_US_Tweet.svg' alt='Tweet' title='Tweet' > </a>
    </div>
  </div>
</div>