---
id: 253
title: 'Azure deployments with Powershell and Jupyter Notebook &#8211; Step-by-Step experience'
date: 2020-05-25T18:46:29+01:00
author: Mr.AzureStack
layout: post
guid: https://azurestack.info/?p=253
permalink: /azure-with-powershell-and-jupyter-notebook
rank_math_internal_links_processed:
  - "1"
rank_math_seo_score:
  - "81"
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
rank_math_permalink:
  - azure-with-powershell-and-jupyter-notebook
rank_math_focus_keyword:
  - jupyter notebook
rank_math_primary_category:
  - "25"
rank_math_schema_Article:
  - 'a:6:{s:5:"@type";s:11:"BlogPosting";s:8:"headline";s:11:"%seo_title%";s:13:"datePublished";s:20:"%date(Y-m-dTH:i:sP)%";s:12:"dateModified";s:24:"%modified(Y-m-dTH:i:sP)%";s:6:"author";a:2:{s:5:"@type";s:6:"Person";s:4:"name";s:13:"Mr.AzureStack";}s:8:"metadata";a:4:{s:5:"title";s:7:"Article";s:9:"isPrimary";b:1;s:4:"type";s:8:"template";s:14:"reviewLocation";s:6:"custom";}}'
rank_math_analytic_object_id:
  - "2"
categories:
  - Jupyter Notebook
  - Azure Stack Hub
  - Grundlagen
tags:
  - Azure
  - Azure Stack Hub
  - Jupyter
  - Powershell
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
      <a class="ez-toc-link ez-toc-heading-1" href="https://azurestack.info/azure-with-powershell-and-jupyter-notebook#General" title="General">General</a>
    </li>
    <li class="ez-toc-page-1 ez-toc-heading-level-2">
      <a class="ez-toc-link ez-toc-heading-2" href="https://azurestack.info/azure-with-powershell-and-jupyter-notebook#What_is" title="What is ?">What is ?</a>
    </li>
    <li class="ez-toc-page-1 ez-toc-heading-level-2">
      <a class="ez-toc-link ez-toc-heading-3" href="https://azurestack.info/azure-with-powershell-and-jupyter-notebook#Local_installation" title="Local installation">Local installation</a><ul class="ez-toc-list-level-3">
        <li class="ez-toc-heading-level-3">
          <a class="ez-toc-link ez-toc-heading-4" href="https://azurestack.info/azure-with-powershell-and-jupyter-notebook#What_you_need_to_install" title="What you need to install">What you need to install</a>
        </li>
        <li class="ez-toc-page-1 ez-toc-heading-level-3">
          <a class="ez-toc-link ez-toc-heading-5" href="https://azurestack.info/azure-with-powershell-and-jupyter-notebook#How_to_install" title="How to install">How to install</a>
        </li>
      </ul>
    </li>
    
    <li class="ez-toc-page-1 ez-toc-heading-level-2">
      <a class="ez-toc-link ez-toc-heading-6" href="https://azurestack.info/azure-with-powershell-and-jupyter-notebook#Configuration_of_Jupyter_Notebook_for_Powershell" title="Configuration of Jupyter Notebook for Powershell">Configuration of Jupyter Notebook for Powershell</a>
    </li>
    <li class="ez-toc-page-1 ez-toc-heading-level-2">
      <a class="ez-toc-link ez-toc-heading-7" href="https://azurestack.info/azure-with-powershell-and-jupyter-notebook#Connect_to_Azure_or_Azure_Stack_Hub" title="Connect to Azure or Azure Stack Hub">Connect to Azure or Azure Stack Hub</a>
    </li>
  </ul></nav>
</div>

## <span class="ez-toc-section" id="General"></span>General<span class="ez-toc-section-end"></span>

I love performing deployments in Azure via Powershell. This saves time and simplifies your daily work in the operation of customers. Above all, it is an asset for IT service providers. This makes it possible to automate recurring tasks. So far I have always worked with the Powershell Console. Since Build 2020 I also work with Windows Terminal and most recently with Jupyter Notebook. And that&#8217;s what this blog post is all about. As an alternative, Microsoft presented Visual Studio Codespaces at Build 2020. It&#8217;s going in the same direction. The goal is that Dev Teams can work on code at the same time.

## 

## <span class="ez-toc-section" id="What_is"></span>What is ?<span class="ez-toc-section-end"></span>

Jupyter Notebook is an open-source web application that allows you to create live code. to share with others, or to work on it at the same time. Jupyter Notebook does not support Powershell until March 2020. The tool is based on Python and can run both locally and in the cloud.

&nbsp;

## <span class="ez-toc-section" id="Local_installation"></span>Local installation<span class="ez-toc-section-end"></span>

### <span class="ez-toc-section" id="What_you_need_to_install"></span>What you need to install<span class="ez-toc-section-end"></span>

First I had [PowerShell 7](https://github.com/PowerShell/PowerShell/releases/tag/v7.0.0), [Pythen](https://www.python.org/downloads/windows/) 3.8 and the [.NET SDK](https://dotnet.microsoft.com/download/dotnet-core/3.1) installed.

The next steps are:

  * Install .NET Interactive
  * Install JupyterLab
  * Register .NET Interactive

&nbsp;

### <span class="ez-toc-section" id="How_to_install"></span>How to install<span class="ez-toc-section-end"></span>

You can use the command prompt (start as an admin):

<img loading="lazy" class="aligncenter size-full wp-image-258" src="https://azurestack.info/wp-content/uploads/2020/05/jupyter-notebook-install-net-interactive.jpg" alt="jupyter-notebook-install-net-interactive" width="729" height="157" srcset="https://azurestack.info/wp-content/uploads/2020/05/jupyter-notebook-install-net-interactive.jpg 729w, https://azurestack.info/wp-content/uploads/2020/05/jupyter-notebook-install-net-interactive-300x65.jpg 300w" sizes="(max-width: 729px) 100vw, 729px" /> 

After the installation close the command promt.

To install Jupyter Notebook with [PIP](https://jupyter.org/install.html) use Powershell (start as an admin):

<img loading="lazy" class="aligncenter size-full wp-image-259" src="https://azurestack.info/wp-content/uploads/2020/05/jupyter-notebook-install-jupyterlab.jpg" alt="jupyter-notebook-install-jupyterlab" width="467" height="128" srcset="https://azurestack.info/wp-content/uploads/2020/05/jupyter-notebook-install-jupyterlab.jpg 467w, https://azurestack.info/wp-content/uploads/2020/05/jupyter-notebook-install-jupyterlab-300x82.jpg 300w" sizes="(max-width: 467px) 100vw, 467px" /> 

After the installation close .Powershell

Now you must register the .NET Interactive with a command prompt (start as an admin):

<img loading="lazy" class="aligncenter size-full wp-image-261" src="https://azurestack.info/wp-content/uploads/2020/05/jupyter-notebook-register-net-interactive.jpg" alt="jupyter-notebook-register-net-interactive" width="614" height="147" srcset="https://azurestack.info/wp-content/uploads/2020/05/jupyter-notebook-register-net-interactive.jpg 614w, https://azurestack.info/wp-content/uploads/2020/05/jupyter-notebook-register-net-interactive-300x72.jpg 300w" sizes="(max-width: 614px) 100vw, 614px" /> 

&nbsp;

The last step is to start Jupyter Notebook.

I have got myself a shortcut on the desktop first:

<img loading="lazy" class="aligncenter size-full wp-image-262" src="https://azurestack.info/wp-content/uploads/2020/05/jupyter-notebook-desktop-symbol.jpg" alt="jupyter-notebook-desktop-symbol" width="398" height="508" srcset="https://azurestack.info/wp-content/uploads/2020/05/jupyter-notebook-desktop-symbol.jpg 398w, https://azurestack.info/wp-content/uploads/2020/05/jupyter-notebook-desktop-symbol-235x300.jpg 235w" sizes="(max-width: 398px) 100vw, 398px" /> 

&nbsp;

This is a shortcut to the command prompt. Add the extension &#8221; /C jupyter notebook&#8221; to target and give the shortcut a name.

This completes the installation.

&nbsp;

## <span class="ez-toc-section" id="Configuration_of_Jupyter_Notebook_for_Powershell"></span>Configuration of Jupyter Notebook for Powershell<span class="ez-toc-section-end"></span>

Next is the configuration of Jupyter Notebook for the use of Powershell Scripts, incl. all Az-Modules for this. To do this, start the created link. The web browser will open.

Next, we need to create a new notebook and specify the path to it.

&nbsp;

<img loading="lazy" class="aligncenter size-full wp-image-266" src="https://azurestack.info/wp-content/uploads/2020/05/jupyter-notebook-new-powershell-notebook.jpg" alt="jupyter-notebook-new-powershell-notebook" width="1210" height="369" srcset="https://azurestack.info/wp-content/uploads/2020/05/jupyter-notebook-new-powershell-notebook.jpg 1210w, https://azurestack.info/wp-content/uploads/2020/05/jupyter-notebook-new-powershell-notebook-300x91.jpg 300w, https://azurestack.info/wp-content/uploads/2020/05/jupyter-notebook-new-powershell-notebook-1024x312.jpg 1024w, https://azurestack.info/wp-content/uploads/2020/05/jupyter-notebook-new-powershell-notebook-768x234.jpg 768w" sizes="(max-width: 1210px) 100vw, 1210px" /> 

&nbsp;

<img loading="lazy" class="aligncenter size-full wp-image-269" src="https://azurestack.info/wp-content/uploads/2020/05/jupyter-notebook-powershell-notebook.jpg" alt="jupyter-notebook-powershell-notebook" width="1209" height="257" srcset="https://azurestack.info/wp-content/uploads/2020/05/jupyter-notebook-powershell-notebook.jpg 1209w, https://azurestack.info/wp-content/uploads/2020/05/jupyter-notebook-powershell-notebook-300x64.jpg 300w, https://azurestack.info/wp-content/uploads/2020/05/jupyter-notebook-powershell-notebook-1024x218.jpg 1024w, https://azurestack.info/wp-content/uploads/2020/05/jupyter-notebook-powershell-notebook-768x163.jpg 768w" sizes="(max-width: 1209px) 100vw, 1209px" /> 

Next step is to import the Azure Powersell Modules.

<img loading="lazy" class="aligncenter size-full wp-image-271" src="https://azurestack.info/wp-content/uploads/2020/05/jupyter-notebook-import-azure-powershell-modules.jpg" alt="jupyter-notebook-import-azure-powershell-modules" width="1199" height="230" srcset="https://azurestack.info/wp-content/uploads/2020/05/jupyter-notebook-import-azure-powershell-modules.jpg 1199w, https://azurestack.info/wp-content/uploads/2020/05/jupyter-notebook-import-azure-powershell-modules-300x58.jpg 300w, https://azurestack.info/wp-content/uploads/2020/05/jupyter-notebook-import-azure-powershell-modules-1024x196.jpg 1024w, https://azurestack.info/wp-content/uploads/2020/05/jupyter-notebook-import-azure-powershell-modules-768x147.jpg 768w" sizes="(max-width: 1199px) 100vw, 1199px" /> 

&nbsp;

Now klick &#8220;Run&#8221; and wait. In the line between [ ] there is now a &#8220;*&#8221;. That means, that this line is running.

<img loading="lazy" class="aligncenter size-full wp-image-272" src="https://azurestack.info/wp-content/uploads/2020/05/jupyter-notebook-installation-azure-powershell-modules.jpg" alt="jupyter-notebook-installation-azure-powershell-modules" width="1203" height="438" srcset="https://azurestack.info/wp-content/uploads/2020/05/jupyter-notebook-installation-azure-powershell-modules.jpg 1203w, https://azurestack.info/wp-content/uploads/2020/05/jupyter-notebook-installation-azure-powershell-modules-300x109.jpg 300w, https://azurestack.info/wp-content/uploads/2020/05/jupyter-notebook-installation-azure-powershell-modules-1024x373.jpg 1024w, https://azurestack.info/wp-content/uploads/2020/05/jupyter-notebook-installation-azure-powershell-modules-768x280.jpg 768w" sizes="(max-width: 1203px) 100vw, 1203px" /> 

&nbsp;

After that is ready you can use this Notebook with your Powershell Code.

&nbsp;

## <span class="ez-toc-section" id="Connect_to_Azure_or_Azure_Stack_Hub"></span>Connect to Azure or Azure Stack Hub<span class="ez-toc-section-end"></span>

When you run the next line with: &#8220;Connect-AzAccount&#8221; you can connect to Azure.

<img loading="lazy" class="aligncenter size-full wp-image-273" src="https://azurestack.info/wp-content/uploads/2020/05/jupyter-notebook-connect-to-azure.jpg" alt="jupyter-notebook-connect-to-azure" width="1193" height="323" srcset="https://azurestack.info/wp-content/uploads/2020/05/jupyter-notebook-connect-to-azure.jpg 1193w, https://azurestack.info/wp-content/uploads/2020/05/jupyter-notebook-connect-to-azure-300x81.jpg 300w, https://azurestack.info/wp-content/uploads/2020/05/jupyter-notebook-connect-to-azure-1024x277.jpg 1024w, https://azurestack.info/wp-content/uploads/2020/05/jupyter-notebook-connect-to-azure-768x208.jpg 768w" sizes="(max-width: 1193px) 100vw, 1193px" /> 

Go to the website and enter the code.

This is the hole guide for using Jupyter Notebook with Powershell.

At the end you can safe this Notebook to a folder in One Drive for Business, or MS Teams. Or you can install Jupyter Notebook in an Azure Virtual Machine.

Let your mind run wild&#8230;.. 😉

&nbsp;

<div class='sfsi_Sicons' style='width: 100%; display: inline-block; vertical-align: middle; text-align:left'>
  <div style='margin:0px 8px 0px 0px; line-height: 24px'>
    <span>Please follow and like us:</span>
  </div>
  
  <div class='sfsi_socialwpr'>
    <div class='sf_fb sf_icon' style='text-align:left;vertical-align: middle;'>
      <div class="fb-like" data-href="https://azurestack.info/azure-with-powershell-and-jupyter-notebook?type=jekyll"  data-send="false" data-layout="button" >
      </div>
    </div>
    
    <div class='sf_fb_share sf_icon' style='text-align:left;vertical-align: middle;'>
      <a href='https://www.facebook.com/sharer/sharer.php?u=https%3A%2F%2Fazurestack.info%2Fazure-with-powershell-and-jupyter-notebook%3Ftype%3Djekyll' style='display:inline-block;'  > <img class='sfsi_wicon'  data-pin-nopin='true' width='auto' height='auto' alt='fb-share-icon' title='Facebook Share' src='https://azurestack.info/wp-content/plugins/ultimate-social-media-icons/images/visit_icons/fbshare_bck.png' /></a>
    </div>
    
    <div class='sf_twiter sf_icon' style='display: inline-block;vertical-align: middle;width: auto;margin-left: 7px;'>
      <a target='_blank' href='https://twitter.com/intent/tweet?text=Azure+deployments+with+Powershell+and+Jupyter+Notebook+%26%238211%3B+Step-by-Step+experience+https://azurestack.info/azure-with-powershell-and-jupyter-notebook?type=jekyll'style='display:inline-block' > <img data-pin-nopin= true width='auto' class='sfsi_wicon' src='https://azurestack.info/wp-content/plugins/ultimate-social-media-icons/images/visit_icons/en_US_Tweet.svg' alt='Tweet' title='Tweet' > </a>
    </div>
  </div>
</div>