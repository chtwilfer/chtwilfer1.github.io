---
title: 'Azure Stack HCI Infrastructure deployment overview'
layout: single
categories:
  - Azure Stack HCI
  - Azure
tags:
  - Azure Stack HCI
  - Azure
---

## **Azure Stack HCI  - Infrastructure deployment overview**

In this small contribution I would like to point out to you, which there is everything for possibilities in connection with the hardware and the network, based on Dell Technologies Hardware.

You have a choice between three deployment models for your Azure Stack HCI project.
Deployment models are:
- Scalable model
- Switchless model
- Strechted Cluster (disaster recovery solution)


![HCI Infrastructure deployment](/assets/images/DellAzSHCIinfrastructuredeployments.jpg)


With the scalable model you can use 2 (minimum) to  16 (maximum) Nodes. There are also top-of-rack switches for managment and storage traffic.
The scalable model can be deployed in two network topologies.
- fully-converged
- non-converged

In the fully-converged network topology all storage ports from the same server are connected to the same network fabric. Within the host OS, the NIC ports are used for both storage and management / VM traffic. 

In the non-converged network topology the storage traffic is seperated from the management / VM traffic using dedicated storage netowrk adapters.
There are two different variants of the non-converged topology with storage on physical apadapters. 
In the first variant one port per network adapater is used for the physical storage links and the rest from each NIC are used for management / VM traffic. This topology helps in scenarios where you require higher bandwidth for VMs whilst not compromising on bandwidth for storage traffic.
The second variant one port of the two 2-port adapters is for the storage traffic. The second port of the two 2-port adapter will set in a Switch Embedded Teaming (SET) for management / VM  and host OS traffic.


With the switchless model you can use 2 (minimum) to 4 (maximum) Nodes. The full mesh topology differs in:
- single link full mesh (with 3 to 4 Nodes)
- dual link full mesh (with 2 to 4 Nodes)


With the strechted cluster cdeployment you can use 4 to 16 Nodes (that means 2 / 8 Nodes per site). If you want to use storage replica across WAN you cannot use RDMA. Furthermore there are the following additional possibilities:
- synchronous / asynchronous replication
- active - active / active - passive
- 2 sites
- 2 storage pools


If you want to deploy a 2-Node HCI, then this is important for you:
- re-deployment when you want to expand the nodes
- best for Proof-of-Concept and Testing
- switchless with Dual Link network adapters for redundancy


Deployment requirements for the Infrastructure Management (possibly already present in your environment)
- Active Directory
- Domain Name Service
- Windows Update Service (WSUS) - optional
- Windows Admin Center (WAC)
- System Center Operations Manager - optional
- System Cetern Virtual Machine Manager - optional


Node OS requirements, after you have installed the HCI OS
- Hyper-V Service
- Failover Clustering
- BitLocker (optional)
- File Server (optional)
- Data Center Bridging (DBC) required in a fully converged network topology


Best practices are:
- disable SMB signing
- Update the hardware timeout for the Spaces port
- Enable jumbo frames
- Persistent Memory


LAST STEP BEFORE OPERATION STARTS
- Run 'Test-Cluster' cmdlet for validation report


Another requirements for the networks Adapters in:
A fully-converged network configuration with Mellanox Nics with RDMA over Converged Ethernet (RoCE) means:
- Data Center Bridging (DCB) -> required
- Priority Flow Control (PTS) -> required
- Enhanced Transmission Selection (ETS) -> required
- DcbxMode property to "Host in charge"

A switchless network configuration with QLogic Fast LinQ 41262 dual port 25 GbE means:
- configured with iWARP
- Data Center Bridging (DBC) not required


So let us check what you have learned ;-)

How many nodes do you want to use? Answer: 8 Nodes
-> So you can deploy your HCI as a scalable model or a strechted cluster

Do you have two Data Center Regions?
-> So you can deploy a strechted cluster of HCI

You want to test Azure Stack HCI in a Proof-ofconecpt?
-> So you use a 2-node switchless model

What is the best switchless 2-node model for a PoC?
-> A switchless model with dual link full mesh


Conclusion
I prefered the scalable model with a non-converged netowrk topology. That means one Azure Stack HCI with 2 to 16 Nodes in one Data Center. For Disaster Recovery you can use different Azure Services, such as Azure Site Recovery and Azure Backup.

And if you still don't have enough information, or you are planning to implement Azure Stack HCI but don't know exactly how, feel free to contact me.
