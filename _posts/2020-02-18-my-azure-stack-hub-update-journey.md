---
id: 214
title: 'My Azure Stack Hub update journey to Version 2002 &#8211; success'
date: 2020-02-18T22:32:55+01:00
author: Mr.AzureStack
layout: post
guid: http://azurestack.info/?p=214
permalink: /my-azure-stack-hub-update-journey
rank_math_internal_links_processed:
  - "1"
rank_math_title:
  - '%title% %sep% %sitename%'
rank_math_permalink:
  - my-azure-stack-hub-update-journey
rank_math_focus_keyword:
  - azure stack hub
rank_math_primary_category:
  - "0"
rank_math_seo_score:
  - "68"
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
  - "5"
categories:
  - Azure Stack Hub
  - AzureStack
  - Grundlagen
tags:
  - Azure Stack
  - Azure Stack Hub
  - Microsoft
---
I am currently on an Azure Stack Hub appliance update journey. I would like to share this project with you. It all started with an Azure Stack Hub 4-Node Appliance (Integrated System), which I technically took over at the customer.

The goal was to update the system to the current patch status in the “shortest&#8221; time. And that&#8217;s where my first problem started. 😊 I have known customer wishes, such as „can you just do it&#8221; from the past 25 years in IT, but „in the shortest time&#8221; for a complex IT infrastructure appliance consisting of individual hardware nodes assembled into a unit.

Oh, I thought it would be fun.

So I first had to get an overview and what interested me was the current state of the appliance. Then came the individual installation instructions (some up to 100 pages long) from the manufacturer. Then came the mental flow chart and this is exactly where we come to an enormously important point for the „Azure Stack Operator&#8221; <- He should have a plan and document every step!

As an Azure Stack Operator you have many tasks around the appliance. Here is a small list of what needs to be done:

<img loading="lazy" class="aligncenter size-full wp-image-215" src="https://azurestack.info/wp-content/uploads/2020/02/Operator-Tasks.png" alt="" width="938" height="525" srcset="https://azurestack.info/wp-content/uploads/2020/02/Operator-Tasks.png 938w, https://azurestack.info/wp-content/uploads/2020/02/Operator-Tasks-300x168.png 300w, https://azurestack.info/wp-content/uploads/2020/02/Operator-Tasks-768x430.png 768w" sizes="(max-width: 938px) 100vw, 938px" /> 

<span style="font-size: 8pt;">Source: Microsoft, Alexander Ortha</span>

However, we want to concentrate here primarily on the point of installing updates (Microsoft & Hardware Vendor). Various conditions must be fulfilled, or to be observed. In short, there are dependencies between MS & the hardware manufacturer updates.

In my case, the first thing I need to do is install the latest and most recent Azure Stack version-specific hotfix. Since this Azure Stack is currently running on version 1907 the hotfix 1.1907.18.56 must be applied. There are now two differences in the installation procedure. We distinguish here between Disconnected and Connected Mode.

In my case I have a disconnected mode, which means that the Azure Stack has no connection to the internet. Thus, the update packages must be downloaded from an internet-connected PC or server and uploaded to the Azure Stack. Only then can an update in the Azure Stack take place.

So we have to download the necessary MS Azure Stack hotfix and upload it to the storage account under Blobs in a container. Now we find the update in the Admin Portal &#8211; Dashboard under the item Update. This can now also be used for installation. This now takes some time and we can get acquainted with the next step.

Next, we will deal with the topic of hardware manufacturer updates, which for example, can be used to improve the performance of the hardware. eg. includes drivers and firmware.

Each manufacturer, briefly mentioned here, has its own process, or how to add BIOS and firmware updates to the Azure Stack. In my case, this is fortunately a simple variant of the installation. However, this can also become a problem if the updates cannot be automatically applied to the HLH as promised in the instructions. After a support call with the manufacturer, we agreed to install the updates manually, one by one. Which unfortunately took a lot of time. Seemed to be a special case, though.

After the HLH was fully patched with current updates on the hardware side, I was able to start the Update Tool for the rest of the appliance. This process went through as expected, cleanly and at the right time. The installation length always depends on the hardware configuration of the individual nodes in the appliance. After I had worked through the requirements of the OEM package version 1908, I immediately started (after a call with Microsoft) to install the OEM package version 1911.

Important note: This procedure described here is explicitly for my customer and my present Azure Stack System coordinated with Microsoft and the hardware manufacturer, so please do not adopt it. Remember your support contract. 😉

Now that we have installed the firmware and bios updates on the appliance hardware, the actual Azure Stack updates are ready to install.

Currently my system is on version 1.1907.18.56. Means we can install version 1908. Please have a look at the release notes, there you will find all information about what is required and when, so that further updates can be installed. From the MS website we download the Azure Stack Update Downloader.

Play this update again, as described above for the hotfix, with the xml file in the Update Storage account. Afterwards the update appears in the Admin Portal and we can start the installation. With a few hours patience, depending on the hardware equipment, the update is then installed without further problems and we have the Azure Stack version 1908. Following this, the last hotfix of the version, again with the same procedure. After that the 1910 update with a subsequent hotfix.

That´s it!

&nbsp;

Enclosed are two pictures I took during the installations.

<img loading="lazy" class="aligncenter size-full wp-image-216" src="https://azurestack.info/wp-content/uploads/2020/02/Update-Variante-1.png" alt="" width="945" height="853" srcset="https://azurestack.info/wp-content/uploads/2020/02/Update-Variante-1.png 945w, https://azurestack.info/wp-content/uploads/2020/02/Update-Variante-1-300x271.png 300w, https://azurestack.info/wp-content/uploads/2020/02/Update-Variante-1-768x693.png 768w" sizes="(max-width: 945px) 100vw, 945px" /> 

Figure Variant B: Update status &#8211; installation of OEM packages

&nbsp;

<img loading="lazy" class="aligncenter size-full wp-image-217" src="https://azurestack.info/wp-content/uploads/2020/02/Update-Variante-2.png" alt="" width="945" height="350" srcset="https://azurestack.info/wp-content/uploads/2020/02/Update-Variante-2.png 945w, https://azurestack.info/wp-content/uploads/2020/02/Update-Variante-2-300x111.png 300w, https://azurestack.info/wp-content/uploads/2020/02/Update-Variante-2-768x284.png 768w" sizes="(max-width: 945px) 100vw, 945px" /> 

Figure Variant B: Update-Status – installation of AzS Version 1908

&nbsp;

There are 2 ways to check the current update status. Variant A is available via the Admin Portal under Updates. I have worked with variant B. It is a Powershell Script, which displays the output as shown in the picture. This works for every update installation that is performed. Has the charming advantage that if the portals are not accessible during the installation phase, you still know what the update does. If you want to learn more about the script, I can contact you through the well-known social media channels.

**Conclusion:** All in all, a lengthy process with many subtasks, but I&#8217;m still impressed by how clean the updates are in the end. It is far from easy to harmonize and install hardware and software without errors in such a complex system. I&#8217;ve already forgotten the few individual steps at the beginning, but the manufacturer has been informed and can adapt his processes accordingly.

<div class='sfsi_Sicons' style='width: 100%; display: inline-block; vertical-align: middle; text-align:left'>
  <div style='margin:0px 8px 0px 0px; line-height: 24px'>
    <span>Please follow and like us:</span>
  </div>
  
  <div class='sfsi_socialwpr'>
    <div class='sf_fb sf_icon' style='text-align:left;vertical-align: middle;'>
      <div class="fb-like" data-href="https://azurestack.info/my-azure-stack-hub-update-journey?type=jekyll"  data-send="false" data-layout="button" >
      </div>
    </div>
    
    <div class='sf_fb_share sf_icon' style='text-align:left;vertical-align: middle;'>
      <a href='https://www.facebook.com/sharer/sharer.php?u=https%3A%2F%2Fazurestack.info%2Fmy-azure-stack-hub-update-journey%3Ftype%3Djekyll' style='display:inline-block;'  > <img class='sfsi_wicon'  data-pin-nopin='true' width='auto' height='auto' alt='fb-share-icon' title='Facebook Share' src='https://azurestack.info/wp-content/plugins/ultimate-social-media-icons/images/visit_icons/fbshare_bck.png' /></a>
    </div>
    
    <div class='sf_twiter sf_icon' style='display: inline-block;vertical-align: middle;width: auto;margin-left: 7px;'>
      <a target='_blank' href='https://twitter.com/intent/tweet?text=My+Azure+Stack+Hub+update+journey+to+Version+2002+%26%238211%3B+success+https://azurestack.info/my-azure-stack-hub-update-journey?type=jekyll'style='display:inline-block' > <img data-pin-nopin= true width='auto' class='sfsi_wicon' src='https://azurestack.info/wp-content/plugins/ultimate-social-media-icons/images/visit_icons/en_US_Tweet.svg' alt='Tweet' title='Tweet' > </a>
    </div>
  </div>
</div>