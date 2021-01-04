---
id: 233
title: 'Azure Stack Hub &#8211; Detailed Usage Summary in Disconnected Mode'
date: 2020-05-07T16:36:27+01:00
author: Mr.AzureStack
layout: post
guid: https://azurestack.info/?p=233
permalink: /azsh-usage-disconnected-mode
rank_math_internal_links_processed:
  - "1"
rank_math_permalink:
  - azsh-usage-disconnected-mode
rank_math_focus_keyword:
  - azure stack hub,usage summary
rank_math_primary_category:
  - "0"
rank_math_seo_score:
  - "75"
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
rank_math_schema_Article:
  - 'a:6:{s:5:"@type";s:11:"BlogPosting";s:8:"headline";s:11:"%seo_title%";s:13:"datePublished";s:20:"%date(Y-m-dTH:i:sP)%";s:12:"dateModified";s:24:"%modified(Y-m-dTH:i:sP)%";s:6:"author";a:2:{s:5:"@type";s:6:"Person";s:4:"name";s:13:"Mr.AzureStack";}s:8:"metadata";a:4:{s:5:"title";s:7:"Article";s:9:"isPrimary";b:1;s:4:"type";s:8:"template";s:14:"reviewLocation";s:6:"custom";}}'
rank_math_analytic_object_id:
  - "4"
categories:
  - Azure Stack Hub
---
For an Azure Stack Hub in a Disconnected Scenario, I am faced with the challenge of reading the detailed usage values of the individual services and exporting them to a file.

During my research I came across two possible approaches. One of them is reading the information via the management API interface of the Azure Stack Hub and the other is reading with Powershell scripts.

I&#8217;ll explain the Powershell way a little bit more here.

&nbsp;

<div id="ez-toc-container" class="ez-toc-v2_0_11 counter-hierarchy counter-decimal ez-toc-grey">
  <div class="ez-toc-title-container">
    <p class="ez-toc-title">
      Table of content
    </p>
    
    <span class="ez-toc-title-toggle"><a class="ez-toc-pull-right ez-toc-btn ez-toc-btn-xs ez-toc-btn-default ez-toc-toggle"><i class="ez-toc-glyphicon ez-toc-icon-toggle"></i></a></span>
  </div><nav>
  
  <ul class="ez-toc-list ez-toc-list-level-1">
    <li class="ez-toc-page-1 ez-toc-heading-level-3">
      <a class="ez-toc-link ez-toc-heading-1" href="https://azurestack.info/azsh-usage-disconnected-mode#The_Powershell_variation" title="The Powershell variation">The Powershell variation</a>
    </li>
    <li class="ez-toc-page-1 ez-toc-heading-level-3">
      <a class="ez-toc-link ez-toc-heading-2" href="https://azurestack.info/azsh-usage-disconnected-mode#The_scripts" title="The scripts">The scripts</a>
    </li>
    <li class="ez-toc-page-1 ez-toc-heading-level-3">
      <a class="ez-toc-link ez-toc-heading-3" href="https://azurestack.info/azsh-usage-disconnected-mode#What_to_do" title="What to do">What to do</a>
    </li>
    <li class="ez-toc-page-1 ez-toc-heading-level-3">
      <a class="ez-toc-link ez-toc-heading-4" href="https://azurestack.info/azsh-usage-disconnected-mode#Review" title="Review">Review</a>
    </li>
    <li class="ez-toc-page-1 ez-toc-heading-level-3">
      <a class="ez-toc-link ez-toc-heading-5" href="https://azurestack.info/azsh-usage-disconnected-mode#Next_steps" title="Next steps">Next steps</a>
    </li>
  </ul></nav>
</div>

### <span class="ez-toc-section" id="The_Powershell_variation"></span>**The Powershell variation**<span class="ez-toc-section-end"></span>

During my further research I came across the following Powershell function: Get-AzsSubscriberUsage. This is part of the Powershell module Azs.Commerce.Admin.  
(For more information see [here](https://docs.microsoft.com/en-us/powershell/module/azs.commerce.admin/?view=azurestackps-1.8.1) and also [here](https://www.powershellgallery.com/packages/Azs.Commerce.Admin/0.9.0-preview))

As an Azure Stack Hub operator, you inevitably end up with a &#8220;toolset&#8221; with additional Powershell [scripts](https://github.com/Azure/AzureStack-Tools) . Under &#8220;Usage&#8221; you will find everything you need to evaluate the usage.

&nbsp;

<img loading="lazy" class="aligncenter wp-image-234" src="https://azurestack.info/wp-content/uploads/2020/05/azstools-1024x794.jpg" alt="Azure Stack Tools" width="776" height="602" srcset="https://azurestack.info/wp-content/uploads/2020/05/azstools-1024x794.jpg 1024w, https://azurestack.info/wp-content/uploads/2020/05/azstools-300x233.jpg 300w, https://azurestack.info/wp-content/uploads/2020/05/azstools-768x595.jpg 768w, https://azurestack.info/wp-content/uploads/2020/05/azstools.jpg 1028w" sizes="(max-width: 776px) 100vw, 776px" /> 

&nbsp;

Remember the Pre-Reqs, please. The installation of the correct Powershell modules is required.

&nbsp;

### <span class="ez-toc-section" id="The_scripts"></span>**The scripts**<span class="ez-toc-section-end"></span>

The script &#8220;UsageSummary. ps1&#8221; provides all usage values, without quotation. The granularity of the utilisation values can be changed between hourly and daily.

&nbsp;

<img loading="lazy" class="aligncenter size-full wp-image-235" src="https://azurestack.info/wp-content/uploads/2020/05/appservicescript.jpg" alt="AppService Script" width="1006" height="252" srcset="https://azurestack.info/wp-content/uploads/2020/05/appservicescript.jpg 1006w, https://azurestack.info/wp-content/uploads/2020/05/appservicescript-300x75.jpg 300w, https://azurestack.info/wp-content/uploads/2020/05/appservicescript-768x192.jpg 768w" sizes="(max-width: 1006px) 100vw, 1006px" /> 

&nbsp;

The script &#8220;Get-AppServicesSubscriptionUsage. ps1&#8221; brings the desired usage values for App Services, including the stored prices from the script. This script loads two more Powershell scripts in the background. First the &#8220;Common.ps1&#8221; and then the &#8220;Get-AppServicesBillingRecords.ps1.

In addition, it should be noted that depending on the selection of the period (date) quite a lot of usage values are read out. Notice, the export file can be several MB in size.

&nbsp;

### <span class="ez-toc-section" id="What_to_do"></span>**What to do**<span class="ez-toc-section-end"></span>

After you have logged into the Azure Stack hub as Admin / Cloudadmin (Operator) via Powershell, you connect to the Default Provider Subscription. It is not necessary to connect to the PEP.

Then you can run one or both scripts described above. After the start of the script you will be greeted after the start time and the end time. These are date values and can be specified as: 01.03.2020. The file is exported to the directory from where you started the Powershell script.

&nbsp;

### <span class="ez-toc-section" id="Review"></span>**Review**<span class="ez-toc-section-end"></span>

To look at the content I use a text editor.

&nbsp;

### <span class="ez-toc-section" id="Next_steps"></span>**Next steps**<span class="ez-toc-section-end"></span>

The file can now be imported to another program. Further processing is also possible if the file is stored in e. g. for example, MS Excel is imported and formatted.

Anyone who is on the road as a service provider can now &#8220;simply&#8221; charge for the use.

<div class='sfsi_Sicons' style='width: 100%; display: inline-block; vertical-align: middle; text-align:left'>
  <div style='margin:0px 8px 0px 0px; line-height: 24px'>
    <span>Please follow and like us:</span>
  </div>
  
  <div class='sfsi_socialwpr'>
    <div class='sf_fb sf_icon' style='text-align:left;vertical-align: middle;'>
      <div class="fb-like" data-href="https://azurestack.info/azsh-usage-disconnected-mode?type=jekyll"  data-send="false" data-layout="button" >
      </div>
    </div>
    
    <div class='sf_fb_share sf_icon' style='text-align:left;vertical-align: middle;'>
      <a href='https://www.facebook.com/sharer/sharer.php?u=https%3A%2F%2Fazurestack.info%2Fazsh-usage-disconnected-mode%3Ftype%3Djekyll' style='display:inline-block;'  > <img class='sfsi_wicon'  data-pin-nopin='true' width='auto' height='auto' alt='fb-share-icon' title='Facebook Share' src='https://azurestack.info/wp-content/plugins/ultimate-social-media-icons/images/visit_icons/fbshare_bck.png' /></a>
    </div>
    
    <div class='sf_twiter sf_icon' style='display: inline-block;vertical-align: middle;width: auto;margin-left: 7px;'>
      <a target='_blank' href='https://twitter.com/intent/tweet?text=Azure+Stack+Hub+%26%238211%3B+Detailed+Usage+Summary+in+Disconnected+Mode+https://azurestack.info/azsh-usage-disconnected-mode?type=jekyll'style='display:inline-block' > <img data-pin-nopin= true width='auto' class='sfsi_wicon' src='https://azurestack.info/wp-content/plugins/ultimate-social-media-icons/images/visit_icons/en_US_Tweet.svg' alt='Tweet' title='Tweet' > </a>
    </div>
  </div>
</div>