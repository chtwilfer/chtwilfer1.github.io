---
id: 242
title: 'Use the Azure DevOps Demo Generator for your own task planning &#8211; creation of a template &#8211; #AzureStackHub'
date: 2020-05-25T12:17:29+01:00
author: Mr.AzureStack
layout: post
guid: https://azurestack.info/?p=242
permalink: /azure-devops-demo-generator
rank_math_internal_links_processed:
  - "1"
rank_math_permalink:
  - azure-devops-demo-generator
rank_math_focus_keyword:
  - azure devops
rank_math_primary_category:
  - "19"
rank_math_seo_score:
  - "84"
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
  - "3"
categories:
  - Azure Stack Hub
  - Azure DevOps
tags:
  - Azure DevOps
  - Azure DevOps Generator
  - Azure Stack Hub
---
<div id="ez-toc-container" class="ez-toc-v2_0_11 counter-hierarchy counter-decimal ez-toc-grey">
  <div class="ez-toc-title-container">
    <p class="ez-toc-title">
      Table of content
    </p>
    
    <span class="ez-toc-title-toggle"><a class="ez-toc-pull-right ez-toc-btn ez-toc-btn-xs ez-toc-btn-default ez-toc-toggle"><i class="ez-toc-glyphicon ez-toc-icon-toggle"></i></a></span>
  </div><nav>
  
  <ul class="ez-toc-list ez-toc-list-level-1">
    <li class="ez-toc-page-1 ez-toc-heading-level-2">
      <a class="ez-toc-link ez-toc-heading-1" href="https://azurestack.info/azure-devops-demo-generator#General" title="General">General</a><ul class="ez-toc-list-level-3">
        <li class="ez-toc-heading-level-3">
          <a class="ez-toc-link ez-toc-heading-2" href="https://azurestack.info/azure-devops-demo-generator#Example_for_a_Story" title="Example for a Story">Example for a Story</a>
        </li>
        <li class="ez-toc-page-1 ez-toc-heading-level-3">
          <a class="ez-toc-link ez-toc-heading-3" href="https://azurestack.info/azure-devops-demo-generator#Example_for_a_Task" title="Example for a Task">Example for a Task</a>
        </li>
      </ul>
    </li>
    
    <li class="ez-toc-page-1 ez-toc-heading-level-2">
      <a class="ez-toc-link ez-toc-heading-4" href="https://azurestack.info/azure-devops-demo-generator#Source" title="Source">Source</a>
    </li>
    <li class="ez-toc-page-1 ez-toc-heading-level-2">
      <a class="ez-toc-link ez-toc-heading-5" href="https://azurestack.info/azure-devops-demo-generator#Template" title="Template">Template</a>
    </li>
  </ul></nav>
</div>

## <span class="ez-toc-section" id="General"></span>General<span class="ez-toc-section-end"></span>

In this post I would like to go into more detail about the Azure DevOps Demo (Project) Generator, because in my current activities as an Operator in an Azure Stack Hub project I am dealing with recurring tasks from the operation. That&#8217;s why I created my to do&#8217;s in Azure DevOps with stories and tasks and entered all information about websites and help in the stories.

These stories and tasks refer to the Azure Stack Hub Operator tasks associated with updates from Microsoft and the manufacturer. In my case, it is a Dell Technologies Azure Stack Hub 14G Integrated System.

One advantage of this Azure DevOps project is that individual people can be assigned different stories and tasks and thus get an overview of who is working on which tasks. In addition, it can be traced in retrospect, where there are problems with the tasks approaching. It is important that every employee maintains all the necessary information in his stories and tasks.

&nbsp;

<img loading="lazy" class="aligncenter size-full wp-image-243" src="https://azurestack.info/wp-content/uploads/2020/05/AzureDevOpsDemoGenerator.jpg" alt="Azure DevOps Generator" width="860" height="596" srcset="https://azurestack.info/wp-content/uploads/2020/05/AzureDevOpsDemoGenerator.jpg 860w, https://azurestack.info/wp-content/uploads/2020/05/AzureDevOpsDemoGenerator-300x208.jpg 300w, https://azurestack.info/wp-content/uploads/2020/05/AzureDevOpsDemoGenerator-768x532.jpg 768w" sizes="(max-width: 860px) 100vw, 860px" /> 

&nbsp;

### <span class="ez-toc-section" id="Example_for_a_Story"></span>Example for a Story<span class="ez-toc-section-end"></span>

The stories can easily be expanded or changed to personal needs.

<img loading="lazy" class="aligncenter size-full wp-image-244" src="https://azurestack.info/wp-content/uploads/2020/05/AzureDevOpsStories.jpg" alt="Azure DevOps Story" width="698" height="595" srcset="https://azurestack.info/wp-content/uploads/2020/05/AzureDevOpsStories.jpg 698w, https://azurestack.info/wp-content/uploads/2020/05/AzureDevOpsStories-300x256.jpg 300w" sizes="(max-width: 698px) 100vw, 698px" /> 

&nbsp;

### <span class="ez-toc-section" id="Example_for_a_Task"></span>Example for a Task<span class="ez-toc-section-end"></span>

The task can also be adapted according to personal needs.

<img loading="lazy" class="aligncenter size-full wp-image-245" src="https://azurestack.info/wp-content/uploads/2020/05/AzureDevOpsTasks.jpg" alt="Azure DevOps Task" width="464" height="641" srcset="https://azurestack.info/wp-content/uploads/2020/05/AzureDevOpsTasks.jpg 464w, https://azurestack.info/wp-content/uploads/2020/05/AzureDevOpsTasks-217x300.jpg 217w" sizes="(max-width: 464px) 100vw, 464px" /> 

&nbsp;

* * *

## <span class="ez-toc-section" id="Source"></span>Source<span class="ez-toc-section-end"></span>

Azure DevOps Demo Generator is available [here](https://azuredevopsdemogenerator.azurewebsites.net/).

A how-toto create a template and use it in a project can be found [here](https://vstsdemodata.visualstudio.com/AzureDevOpsDemoGenerator/_wiki/wikis/AzureDevOpsGenerator.wiki/58/Build-your-own-template).

* * *

## <span class="ez-toc-section" id="Template"></span>Template<span class="ez-toc-section-end"></span>

If you are interested in the template, please feel free to contact me. I would then make it available.

<div class='sfsi_Sicons' style='width: 100%; display: inline-block; vertical-align: middle; text-align:left'>
  <div style='margin:0px 8px 0px 0px; line-height: 24px'>
    <span>Please follow and like us:</span>
  </div>
  
  <div class='sfsi_socialwpr'>
    <div class='sf_fb sf_icon' style='text-align:left;vertical-align: middle;'>
      <div class="fb-like" data-href="https://azurestack.info/azure-devops-demo-generator?type=jekyll"  data-send="false" data-layout="button" >
      </div>
    </div>
    
    <div class='sf_fb_share sf_icon' style='text-align:left;vertical-align: middle;'>
      <a href='https://www.facebook.com/sharer/sharer.php?u=https%3A%2F%2Fazurestack.info%2Fazure-devops-demo-generator%3Ftype%3Djekyll' style='display:inline-block;'  > <img class='sfsi_wicon'  data-pin-nopin='true' width='auto' height='auto' alt='fb-share-icon' title='Facebook Share' src='https://azurestack.info/wp-content/plugins/ultimate-social-media-icons/images/visit_icons/fbshare_bck.png' /></a>
    </div>
    
    <div class='sf_twiter sf_icon' style='display: inline-block;vertical-align: middle;width: auto;margin-left: 7px;'>
      <a target='_blank' href='https://twitter.com/intent/tweet?text=Use+the+Azure+DevOps+Demo+Generator+for+your+own+task+planning+%26%238211%3B+creation+of+a+template+%26%238211%3B+%23AzureStackHub+https://azurestack.info/azure-devops-demo-generator?type=jekyll'style='display:inline-block' > <img data-pin-nopin= true width='auto' class='sfsi_wicon' src='https://azurestack.info/wp-content/plugins/ultimate-social-media-icons/images/visit_icons/en_US_Tweet.svg' alt='Tweet' title='Tweet' > </a>
    </div>
  </div>
</div>