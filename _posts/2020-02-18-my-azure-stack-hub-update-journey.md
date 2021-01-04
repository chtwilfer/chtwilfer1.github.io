---
title: 'My Azure Stack Hub update journey to Version 2002 - success'
layout: post
categories:
  - Azure Stack Hub
  - Azure Stack
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
Picture Source: Microsoft, Alexander Ortha

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

Enclosed are two pictures I took during the installations.

<img loading="lazy" class="aligncenter size-full wp-image-216" src="https://azurestack.info/wp-content/uploads/2020/02/Update-Variante-1.png" alt="" width="945" height="853" srcset="https://azurestack.info/wp-content/uploads/2020/02/Update-Variante-1.png 945w, https://azurestack.info/wp-content/uploads/2020/02/Update-Variante-1-300x271.png 300w, https://azurestack.info/wp-content/uploads/2020/02/Update-Variante-1-768x693.png 768w" sizes="(max-width: 945px) 100vw, 945px" /> 

Figure Variant B: Update status - installation of OEM packages


<img loading="lazy" class="aligncenter size-full wp-image-217" src="https://azurestack.info/wp-content/uploads/2020/02/Update-Variante-2.png" alt="" width="945" height="350" srcset="https://azurestack.info/wp-content/uploads/2020/02/Update-Variante-2.png 945w, https://azurestack.info/wp-content/uploads/2020/02/Update-Variante-2-300x111.png 300w, https://azurestack.info/wp-content/uploads/2020/02/Update-Variante-2-768x284.png 768w" sizes="(max-width: 945px) 100vw, 945px" /> 

Figure Variant B: Update-Status – installation of AzS Version 1908


There are 2 ways to check the current update status. Variant A is available via the Admin Portal under Updates. I have worked with variant B. It is a Powershell Script, which displays the output as shown in the picture. This works for every update installation that is performed. Has the charming advantage that if the portals are not accessible during the installation phase, you still know what the update does. If you want to learn more about the script, I can contact you through the well-known social media channels.

**Conclusion:** All in all, a lengthy process with many subtasks, but I´m still impressed by how clean the updates are in the end. It is far from easy to harmonize and install hardware and software without errors in such a complex system. I&#8217;ve already forgotten the few individual steps at the beginning, but the manufacturer has been informed and can adapt his processes accordingly.
