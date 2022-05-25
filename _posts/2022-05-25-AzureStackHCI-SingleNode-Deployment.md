---
title: 'Azure Stack HCI - Single Node - Deployment'
layout: single
categories:
  - Azure Stack HCI
  - Azure Arc
  - HybridCloud
tags:
  - Microsoft
  - Azure
  - AzureArc
  - Arc
  - HybridCloud
  - AzureStackHCI
  - Cloud
---

## News
At MS Build 2022 the Azure Stack HCI Single Node Cluster Announcement has been done.

Azure Stack HCI running on a single-node cluster behaves very similarly to Azure Stack HCI on a multi-node cluster: it brings native Azure Arc integration, you can add servers to scale out the cluster, and it includes the same Azure benefits.
It also supports the same workloads, such as Azure Virtual Desktop (AVD) and Azure Kubernetes Service (AKS) on Azure Stack HCI, and lastly it is supported and billed the same way. To learn more, see Using Azure Stack HCI on a single server.

At this time you cannot install a single cluster with Windows Admin Center. 

Therefore, I have collected the Powershell scripts for the deployment on my Github page.

You can find my Github page here: [Github/chtwilfer](https://github.com/chtwilfer/Azure-Stack-HCI-Single-Server-Deployment)

### Comparing singel-node and multi-node clusters
The following table compares attributes of a single-node cluster to multi-node clusters.

|Attributes|Single-Node|Multi-Node
|-|-|-|
| Full software-defined data center (SDDC) stack (hypervisor, storage, networking) | Yes | Yes |
| Storage Spaces Direct support |	Yes |	Yes |
| Software Defined Networking (SDN) support |	Yes	| Yes |
| Native Azure Arc integration | Yes |	Yes |
| Managed through Windows Admin Center and Azure portal |	Yes | Yes |
| Azure billing/registration | Yes | Yes |
| Charged per physical core | Yes |	Yes |
| Support through Azure |	Yes |	Yes |
| Connectivity (intermittent or connected)|	Yes |	Yes |
| Azure benefits on Azure Stack HCI |	Yes |	Yes |
| Activate Windows Server Subscriptions |	Yes |	Yes |
| Azure Defender and Secured-core |	Yes |	Yes |
| Azure Kubernetes Service on Azure Stack HCI (AKS-HCI) |	Yes |	Yes |
| Azure Virtual Desktop |	Yes |	Yes |
| Azure Site Recovery |	Yes |	Yes |
| Azure Stack HCI: Stretch cluster support |	No |	Yes |
| Use Graphics Processing Units (GPUs) with clustered VMs |	Yes |	Yes |


Please feel free to comment or come back to me with your thoughts. :-)
