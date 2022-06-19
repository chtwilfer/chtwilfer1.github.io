---
title: 'ArcEnabled-Windows-Server-Demo-Lab'
layout: single
categories:
  - Microsoft
  - Azure
  - Azure Arc
  - HybridCloud
tags:
  - Microsoft
  - Azure
  - AzureArc
  - Arc
  - HybridCloud
  - Cloud
---

## Azure Arc On-Prem Demo environment in Azure

In my daily work with customers, I often find myself in situation where the customer asks if I can "give a quick demonstration".

Sure I can! :-)

I took the opportunity to create exactly such a scenario for Azure Arc.
Unfortunately, I don't have any hardware available On-Prem, so I use Azure to map the scenario. 

So what I have done?
With my new repository on Github [Github](https://github.com/chtwilfer/Arc-enabledWinServersDemoLab/blob/main/README.md) I create a mini Hub & Spoke landing zone. Where the Spoke here is to represent the on-prem world.
I connect the Hub to the Spoke via an appropriate VPN gateway. I also deploy an Azure Bastion and a Virtual Machine in the Spoke. The virtual machine represents the VM On-Prem.
With the Azure Bastion (Jumphost) I access the VM via the Azure Portal, so that the virtual machine is not on the Internet with a public IP address.
So it's a self-contained system, just like we would use in production. 

To simplify things, I now access the VM via Bastion and copy the corresponding script "install_arc_agent.ps1" over. This is started with appropriate admin rights.
With this an additional script "OnboardArc.ps1" is created in "C:\temp". After "install_arc_agant.ps1" was started seven parameter values are requested.
These are necessary to enable the onboarding of the VM in Azure Arc. If this is done, the script "OnboardArc.ps1" can be started with admin rights.
A small moment further and the VM is visible in Azure Arc.

Now there is the possibility to show the customer the individual Arc-related possibilities. I do not configure the service, but only go through them once in the portal with the customer. 

At this point it should be said that I did not create the landing zone model and the install_arc_agent.ps1 script myself.

I just combined really good existing work and adapted it slightly for my needs.

The original version of the Landing Zone is from [Github](https://github.com/PieterbasNagengast/Azure-HubSpoke-LabBuilder).
The original version of Install Arc is from [Arc Jumpstart](https://azurearcjumpstart.io/azure_arc_jumpstart/azure_arc_servers/azure/azure_arm_template_win/).

Thanks a lot for your really good work. :-)
