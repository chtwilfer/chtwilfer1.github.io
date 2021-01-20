---
title: 'NetApp Cloud Services Demo Infrastructure in Azure'
layout: single
categories:
  - Azure NetApp Files
  - Cloud Volumes ONTAP
  - Global File Cache
  - Azure
tags:
  - Azure NetApp Files
  - Cloud Volumes ONTAP
  - Global File Cache
  - Azure
---

## **NetApp Cloud Services Demo Infrastructure in Azure**

![ANF](/assets/images/Azure-NetApp-Files-Icon.png) ![CVO](/assets/images/Cloud-Volumes-ONTAP-Icon.png)
 ![GFC](/assets/images/Global-File-Cache-Icon.png) ![CloudManager](/assets/images/Cloud-Manager-Icon.png)

It's time to present something new. I made the effort and created a Powershell script, which I can use for demo purposes at customer meetings.
The idea was born in a customer meeting. We presented Azure NetApp Files and the customer wanted to see how fast and easy it is to deploy ANF in Azure.

So what came out of that now. In short, **Azure NetApp Files** is deployed in two regions. These two regions are connected via VNet peering.
With a virtual machine and Active Directory Services on it, SMB shares can also be deployed in the ANF pool. In the same way I present the topic Snapshot / Backup.

If you still don't have enough of this, you can deploy **Cloud Volumes ONTAP** and **Global File Cache** via two additional switches in two further resource groups.
The final configuration of CVO and GFC is then done via the NetApp Cloud Manager. This means that there must be a connector to Azure here.
Inevitably then also an access (login) to the Cloud Manager. 

What is missing is the topic "Cross-Region Replication". Here, if necessary, can be manually reworked in Azure. Because CRR is in Preview.

With this script you will be able to create a complete demo scenario for your customer within one to two hours.
Which you can then use for customer meetings, or also for proof-of-concept scenarios. 

Within the scope of your usage, however, you should adapt this script to the customer's requirements.

If there are any suggestions for improvement, please contact me. 


### **Link to the Script on Github**
- [Github Repository](https://github.com/chtwilfer/NetApp-Cloud-Service-Demo-Infrastrutcture-in-Azure)
