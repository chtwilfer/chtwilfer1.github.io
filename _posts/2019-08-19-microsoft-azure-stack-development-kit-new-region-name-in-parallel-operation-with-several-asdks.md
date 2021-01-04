---
title: 'Microsoft Azure Stack Development Kit - new Region Name in parallel operation with several ASDKs'
layout: single
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
- several ASDKs in the same network  
- Different configurations of the ASDKs  
- Connected and Disconnected Mode  
- with and without App Services  
- with Kubernetes  
- with and without AD FS and AAD  
- Access from the customer&#8217;s local network with various Clients


<img loading="lazy" class="aligncenter size-large wp-image-193" src="https://azurestack.info/wp-content/uploads/2019/08/ASDK1_1-1024x542.jpg" alt="" width="1024" height="542" srcset="https://azurestack.info/wp-content/uploads/2019/08/ASDK1_1-1024x542.jpg 1024w, https://azurestack.info/wp-content/uploads/2019/08/ASDK1_1-300x159.jpg 300w, https://azurestack.info/wp-content/uploads/2019/08/ASDK1_1-768x407.jpg 768w, https://azurestack.info/wp-content/uploads/2019/08/ASDK1_1.jpg 2048w" sizes="(max-width: 1024px) 100vw, 1024px" /> 


<img loading="lazy" class="aligncenter size-large wp-image-194" src="https://azurestack.info/wp-content/uploads/2019/08/ASDK2_1-1024x514.jpg" alt="" width="1024" height="514" srcset="https://azurestack.info/wp-content/uploads/2019/08/ASDK2_1-1024x514.jpg 1024w, https://azurestack.info/wp-content/uploads/2019/08/ASDK2_1-300x151.jpg 300w, https://azurestack.info/wp-content/uploads/2019/08/ASDK2_1-768x386.jpg 768w, https://azurestack.info/wp-content/uploads/2019/08/ASDK2_1.jpg 2048w" sizes="(max-width: 1024px) 100vw, 1024px" /> 


With Powershell, we were able to adapt the Config XML of the ASDK to the desired customer scenarios. It is important to know that an ASDK has 62 IP addresses available, from which 31 IP addresses are already subtracted by the pure installation. Each additional resource provider installation requires IP addresses from this pool. There&#8217;s not much left in the end. With the well known subnetting you can get the desired result here.



<img loading="lazy" class="aligncenter size-large wp-image-195" src="https://azurestack.info/wp-content/uploads/2019/08/ASDK3_1-1024x558.jpg" alt="" width="1024" height="558" srcset="https://azurestack.info/wp-content/uploads/2019/08/ASDK3_1-1024x558.jpg 1024w, https://azurestack.info/wp-content/uploads/2019/08/ASDK3_1-300x163.jpg 300w, https://azurestack.info/wp-content/uploads/2019/08/ASDK3_1-768x418.jpg 768w, https://azurestack.info/wp-content/uploads/2019/08/ASDK3_1.jpg 2048w" sizes="(max-width: 1024px) 100vw, 1024px" /> 



In the next step, additional parameter values are added to the InstallPOC. ps1 script in the front section of the parameters. These serve to adapt the region names of the respective ASDKs. E. g. from &#8220;local&#8221;; to &#8220;hamburg&#8221;; or &#8220;RZ1&#8221;. The decision lies in the customer configuration in which the ASDks are added.



<img loading="lazy" class="aligncenter size-large wp-image-196" src="https://azurestack.info/wp-content/uploads/2019/08/ASDK4_1-1024x501.jpg" alt="" width="1024" height="501" srcset="https://azurestack.info/wp-content/uploads/2019/08/ASDK4_1-1024x501.jpg 1024w, https://azurestack.info/wp-content/uploads/2019/08/ASDK4_1-300x147.jpg 300w, https://azurestack.info/wp-content/uploads/2019/08/ASDK4_1-768x376.jpg 768w, https://azurestack.info/wp-content/uploads/2019/08/ASDK4_1.jpg 2048w" sizes="(max-width: 1024px) 100vw, 1024px" /> 



Since the ASDK has now adapted the RegionName, the custom DomainSuffix must also be specified if a Post Deploymennt is used for the installation of App Services (Script Matt McSpirit). It is the same name as the RegionName of the ASDK.



<img loading="lazy" class="aligncenter size-large wp-image-197" src="https://azurestack.info/wp-content/uploads/2019/08/ASDK5_1-1024x608.jpg" alt="" width="1024" height="608" srcset="https://azurestack.info/wp-content/uploads/2019/08/ASDK5_1-1024x608.jpg 1024w, https://azurestack.info/wp-content/uploads/2019/08/ASDK5_1-300x178.jpg 300w, https://azurestack.info/wp-content/uploads/2019/08/ASDK5_1-768x456.jpg 768w, https://azurestack.info/wp-content/uploads/2019/08/ASDK5_1.jpg 2048w" sizes="(max-width: 1024px) 100vw, 1024px" /> 



Since the network IP address range of the ASDK has been adapted, it must also be adapted either in the firewall, or the router where the various ASDKs are located. Just like setting up or configuring a DNS delegation.



<img loading="lazy" class="aligncenter size-large wp-image-198" src="https://azurestack.info/wp-content/uploads/2019/08/ASDK6_1-1024x556.jpg" alt="" width="1024" height="556" srcset="https://azurestack.info/wp-content/uploads/2019/08/ASDK6_1-1024x556.jpg 1024w, https://azurestack.info/wp-content/uploads/2019/08/ASDK6_1-300x163.jpg 300w, https://azurestack.info/wp-content/uploads/2019/08/ASDK6_1-768x417.jpg 768w, https://azurestack.info/wp-content/uploads/2019/08/ASDK6_1.jpg 2048w" sizes="(max-width: 1024px) 100vw, 1024px" /> 



The last hurdle is importing the ASDK certificates to all clients interacting with the systems.



<img loading="lazy" class="aligncenter size-large wp-image-199" src="https://azurestack.info/wp-content/uploads/2019/08/ASDK7_1-1024x525.jpg" alt="" width="1024" height="525" srcset="https://azurestack.info/wp-content/uploads/2019/08/ASDK7_1-1024x525.jpg 1024w, https://azurestack.info/wp-content/uploads/2019/08/ASDK7_1-300x154.jpg 300w, https://azurestack.info/wp-content/uploads/2019/08/ASDK7_1-768x394.jpg 768w, https://azurestack.info/wp-content/uploads/2019/08/ASDK7_1.jpg 2048w" sizes="(max-width: 1024px) 100vw, 1024px" /> 



The way to this overall configuration was not an easy one, but the time invested was worth it. This makes it possible to provide customers with differently configured systems for a Proof-of-Concept (PoC). The total running time of the PoC may also be reduced in the positive decision towards the Azure Stack Integrated System.

Questions, suggestions and wishes are very welcome.
