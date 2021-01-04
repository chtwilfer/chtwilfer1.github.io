---

title: 'Azure Stack Hub &#8211; Detailed Usage Summary in Disconnected Mode'
layout: Single
categories:
  - Azure Stack Hub
---
For an Azure Stack Hub in a Disconnected Scenario, I am faced with the challenge of reading the detailed usage values of the individual services and exporting them to a file.

During my research I came across two possible approaches. One of them is reading the information via the management API interface of the Azure Stack Hub and the other is reading with Powershell scripts.

I will explain the Powershell way a little bit more here.

### **The Powershell variation**

During my further research I came across the following Powershell function: Get-AzsSubscriberUsage. This is part of the Powershell module Azs.Commerce.Admin.  
(For more information see [here](https://docs.microsoft.com/en-us/powershell/module/azs.commerce.admin/?view=azurestackps-1.8.1) and also [here](https://www.powershellgallery.com/packages/Azs.Commerce.Admin/0.9.0-preview))

As an Azure Stack Hub operator, you inevitably end up with a toolset with additional Powershell [scripts](https://github.com/Azure/AzureStack-Tools) . Under the link you will find everything you need to evaluate the usage.


<img loading="lazy" class="aligncenter wp-image-234" src="https://azurestack.info/wp-content/uploads/2020/05/azstools-1024x794.jpg" alt="Azure Stack Tools" width="776" height="602" srcset="https://azurestack.info/wp-content/uploads/2020/05/azstools-1024x794.jpg 1024w, https://azurestack.info/wp-content/uploads/2020/05/azstools-300x233.jpg 300w, https://azurestack.info/wp-content/uploads/2020/05/azstools-768x595.jpg 768w, https://azurestack.info/wp-content/uploads/2020/05/azstools.jpg 1028w" sizes="(max-width: 776px) 100vw, 776px" /> 


Remember the Pre-Reqs, please. The installation of the correct Powershell modules is required.


### **The scripts**

The script UsageSummary.ps1 provides all usage values, without quotation. The granularity of the utilisation values can be changed between hourly and daily.



<img loading="lazy" class="aligncenter size-full wp-image-235" src="https://azurestack.info/wp-content/uploads/2020/05/appservicescript.jpg" alt="AppService Script" width="1006" height="252" srcset="https://azurestack.info/wp-content/uploads/2020/05/appservicescript.jpg 1006w, https://azurestack.info/wp-content/uploads/2020/05/appservicescript-300x75.jpg 300w, https://azurestack.info/wp-content/uploads/2020/05/appservicescript-768x192.jpg 768w" sizes="(max-width: 1006px) 100vw, 1006px" /> 


The script Get-AppServicesSubscriptionUsage.ps1 brings the desired usage values for App Services, including the stored prices from the script. This script loads two more Powershell scripts in the background. First the Common.ps1 and then the Get-AppServicesBillingRecords.ps1.

In addition, it should be noted that depending on the selection of the period (date) quite a lot of usage values are read out. Notice, the export file can be several MB in size.



### **What to do**

After you have logged into the Azure Stack hub as Admin / Cloudadmin (Operator) via Powershell, you connect to the Default Provider Subscription. It is not necessary to connect to the PEP.

Then you can run one or both scripts described above. After the start of the script you will be greeted after the start time and the end time. These are date values and can be specified as: 01.03.2020. The file is exported to the directory from where you started the Powershell script.



### **Review**

To look at the content I use a text editor.



### **Next steps**

The file can now be imported to another program. Further processing is also possible if the file is stored in e. g. for example, MS Excel is imported and formatted.

Anyone who is on the road as a service provider can now simply charge for the use.
