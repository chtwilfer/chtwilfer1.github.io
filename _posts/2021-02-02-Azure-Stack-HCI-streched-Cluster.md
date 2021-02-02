---
title: 'Azure Stack HCI streched Cluster for DR & BC'
layout: single
categories:
  - Azure Stack HCI
  - Streched Cluster
  - Azure
  - Disaster Recovery
  - Business Continuity
tags:
  - Azure Stack HCI
  - Streched Cluster
  - Azure
  - Disaster Recovery
  - Business Continuity
---

## **Azure Stack HCI stretched cluster solution for DR & BC**

With the new Azure Stack HCI (20H2) Version Microsoft brings the streched cluster solution for disaster recovery (DR) and business continuity (BC) to the customers.

The streched cluster and storage replica works hand in hand with the storage replication of the volumes across the configured sites for disaster recovery. 
While the streched cluster provides automatic fail-over the VMs are in sync. There ist no need to manaual intervention.

![HCI Solution](/assets/images/HCISolution.jpg)
[Quelle](https://docs.microsoft.com/en-us/azure-stack/hci/overview)

## **Storage Replication**
Storage Replica supports sychronous and asynchronous replication. The dessicion for synchronous replication is when you have a low-latency network with crash-consistent
volumes to ensure data loss at the files-system level during the failure. With asynchronous replication the system mirrors data across your configured sites over a network
with higher latencies. 

## **Cluster types**
Streched cluster comes across with two types. Active-Active and Active-Passiv. 

With an Active-Active cluster all configured sites has an active replication to the other site. In case of an error the cluster provides an automatic fail-over to the other site.

With an Active-passiv cluster you have a preferred site and a direction for replication. In case of an error the cluster replicates the storage and moves the VMs to the other site. 

![cluster types](/assets/images/HCIClusterType.jpg)
[Quelle](https://docs.microsoft.com/en-us/azure/architecture/hybrid/azure-stack-hci-dr)

## **Hardware considerations**
A standrad HCI cluster requires a minimum of two servers (cluster nodes) an d a maximium of 16 servers. For a streched cluster with 2 seperate sites in different countries, or cities,
floors or rooms the cluster requires am minimun of four servers (two per site) and a maximum of 16 servers (8 per site). 

You can find the whole reuiremtns at this site: https://docs.microsoft.com/en-us/azure-stack/hci/concepts/system-requirements

## **Windows Admin Center**
Windows Admin Center is a locally deployed, browser-based app for managing Windows Servers, clusters, hyper-converged infrastructure and  Windows 10.
With WAC cluster wizard you can create the streched cluster that uses Storage Spaces Direct. You have a choice between a standard cluster or a streched cluster.

## **Protect HCI VMs using Azure Site Recovery**
With a streched cluster you have a disaster recovery plan on the hardware level. If you think, that your datacenters both can shut down you could use Azure as another fail-over site for your VMs.
To able to use this there is an Azure Service called Azure Site Recovery. ASR replicates your running VMs on an Hyper-V or Azure Stack HCI cluster to Azure
For more information look into this article: https://docs.microsoft.com/en-us/azure-stack/hci/manage/azure-site-recovery

So you can see there are different ways for disaster recovery and business continuity.

## **Conclusion**
With the possibilities of Azure Stack HCI streched cluster and Azure Site Recovery you are able to transform your digital tasks into an new dimension.

## **Usefull Links**

  * ArchitectureCenter [Azure Stack HCI streched cluster for DR](https://azure.microsoft.com/en-us/products/azure-stack/hci/hci-download/)
  * Documentation [Azure Stack HCI documentation](https://docs.microsoft.com/en-us/azure-stack/hci/)
  * Streched Cluster Concept [Azure Stack HCI streched cluster concept](https://docs.microsoft.com/en-us/azure-stack/hci/concepts/stretched-clusters)
  * Cluster creation with WAC [Cluster creation with WAC](https://docs.microsoft.com/en-us/azure-stack/hci/deploy/create-cluster)


