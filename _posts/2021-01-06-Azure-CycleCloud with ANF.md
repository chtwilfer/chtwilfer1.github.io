---
title: 'Azure CycleCloud with ANF'
layout: single
categories:
  - Azure CycleCloud
  - High Performance Computing
  - Azure NetApp Files
tags:
  - Azure CycleCloud
  - High Performance Computing
  - Azure NetApp Files
---

**What is Azure CycleCloud and what does it have to do with Azure NetApp FIles (ANF)?**

Azure CycleCloud is an enterprise-friendly tool for orchestrating and managing High Performance Computing (HPC) environments on Azure. With CycleCloud, users can provision infrastructure for HPC systems, deploy familiar HPC schedulers, and automatically scale the infrastructure to run jobs efficiently at any scale. Through CycleCloud, users can create different types of file systems and mount them to the compute cluster nodes to support HPC workloads.
CycleCloud is the sister product to Azure Batch, which provides a Scheduler as a Service on Azure.


**CycleCloud Environment**

![CycleCloud Environment](/assets/images/CycleCloud Environment.PNG)

An entire CycleCloud HPC system can be deployed on Azure infrastructure. CycleCloud itself is installed as an application server on a VM in Azure that requires outbound access to Azure Resource Provider APIs. 
CycleCloud then starts and manages VMs that form the HPC systems — these typically consist of the HPC scheduler head node(s) and compute nodes, but may also include VM based Network Attached Storage such as
an NFS server or BeeGFS cluster, login nodes, bastion hosts, and other components needed to support an HPC infrastructure. The makeup of the HPC system is defined entirely through CycleCloud templates.
Additionally, CycleCloud HPC environments can utilize other PaaS services such as Azure NetApp Files, Azure HPC Cache, and Azure Active Directory Domain Service.


**Integrate Azure NetApp Files to customized Cluster**

![Integrate ANF](/assets/images/Integrate ANF.PNG)

Azure CycleCloud provides built-in support for mounting a simple Network File System (NFS).
If the External NFS option is specified, additional fields appear for specifying the IP address (or hostname) of the NFS server, as well as other NFS mount options.
This External NFS option can be used to mount endpoints such as Azure HPC Cache, **Azure NetApp Files**, or NFS on Azure Blob Storage.


**Decission for Azure NetApp Files**
- Azure NetApp Files is a crucial enabler for high performance, low latency enterprise file based NAS workloads.
- Azure NetApp Files has shared storage for HPC on Azure.
- The massive on demand scalability of Azure NetApp Files, to deal with continually changing workload demands.

**Benefits**
- Simple Management: Native Azure experience
- Performance: Better than on-prem
- Lift & Shift: Flexible data transfer


**More informationen** about these Azure Services:
- [Azure CycleCloud] (https://docs.microsoft.com/de-de/azure/cyclecloud/?view=cyclecloud-8)
- Azure CycleCloud Version 8.1: https://techcommunity.microsoft.com/t5/azure-compute/azure-cyclecloud-8-1-is-now-available/ba-p/1898011
- High Performance Computing (HPC) on Azure: https://docs.microsoft.com/en-us/azure/architecture/topics/high-performance-computing
- Azure NetApp Files: https://docs.microsoft.com/en-us/azure/azure-netapp-files/azure-netapp-files-introduction
- ANF Solutions: https://docs.microsoft.com/en-us/azure/azure-netapp-files/azure-netapp-files-solution-architectures
