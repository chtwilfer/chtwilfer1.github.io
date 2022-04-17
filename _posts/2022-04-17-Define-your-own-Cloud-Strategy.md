---
title: 'Define your own Cloud Strategy'
layout: single
categories:
  - Azure Cloud Strategy
  - Azure Stack HCI
  - Azure Arc
tags:
  - Microsoft
  - Azure
  - AzureArc
  - Arc
  - HybridCloud
  - AzureStackHCI
  - CloudStrategy
  - Cloud
  - Strategy
---

## Introduction
With this article, I would like to give you a little help from cloud migration projects that I have carried out and the experience I have gained from them, so that your project is carried out successfully. First of all, we will deal with the two terms cloud and strategy and explain how the two words fit together. As we go along, we'll turn our attention to your wish list and then move on to your personal cloud strategy. Finally, I show how you can enrich your cloud strategy with Microsoft Azure products.

## Cloud & Strategy
Before we think about cloud strategy, we need to look at the two terms separately. 

Let's take a closer look at the term cloud. First and foremost, cloud means outsourcing. What you previously hosted in your own IT infrastructure, they move to the cloud. To do this, they use the cloud provider offering. Some examples are Microsoft Azure, Google Cloud Platform, Amazon Web Services or IBM Cloud. Here you have the option of moving your existing IT infrastructure 1:1, with a so-called lift & shift migration, or also with a re-design or re-architecture to bring your IT infrastructure up to speed.

**Info**
There is no right or wrong here. Because is your personal path to the cloud. Don't do it because others are doing it. Do it to achieve your operational goals.

But to ensure that this path does not end in disaster, you need a strategy. In this strategy, you define your operational goals. Create a wish list for this purpose. But keep your wish list down to earth and only define what seems realistic from your operational point of view. In the end, a wish list does not represent a strategy. It supports you in the creation of the strategy.

With a so-called "Cloud First" strategy, you would define that everything that has to be newly created is no longer made available on-premise, but is operated directly in the cloud. As an example, consider a hypervisor, such as VMware or Hyper-V, which would need to renew its hardware. This hosting system contains various Windows or Linux servers, but also application systems, which are then migrated directly to the cloud. Now you're probably thinking, that's thinking too short. You're right, because I didn't mention that there might not only be dependencies to other on-premise systems, because there definitely are. You realize, a migration is always something complicated as well. But this article is not about the systems to be migrated, but about your strategy, or rather about the strategy across to a successfully implemented overall project. No project without strategy. Should you still consider this, then you burn money and personnel.

## Defining your own cloud strategy
Make sensible decisions and set small interim goals. With priorities and a balanced plan and allocated resources, you will get to the desired result. Establish a Cloud Center of Excellence (abbreviated CCoE) and bring your most valuable domain expertise to this virtual team. This team can include IT professionals, product owners, the CDO, CIO / IT leader and others as you define. Most importantly, detach your professionals from operational tasks in the overall project. You will need your best IT Architects & Engineers to get you on the planned path to the cloud. Discuss with the CCoE team their wish list and operational goals. Stay disciplined and create a cloud roadmap over a period of several years. It doesn't matter whether you choose to work in an agile way or the traditional way. If you are not confident in this task, then bring in external help. With workshops of varying intensity in the round, you will quickly achieve initial results. Even if there is no noticeable progress, keep at it and continue on your overall path. In the end, you will be glad you took this path. You will also quickly realize that the strategy relates to your entire value chain. To do this, keep bringing key players from the individual areas on board. Present your (partial) results to the entire company at regular intervals. Then everyone will have the feeling of being part of it. Also check your results at regular intervals with a short review. This is due to the fact that your company does not stand still, but continues to operate.

## Hybrid Cloud for your cloud strategy
When creating a strategy, it is always a question of deciding whether to use hybrid, i.e. a mix of public and private clouds, or cloud-native, i.e. the public cloud. If you are now in the start-up phase with your company and have not yet deployed anything on-premise, then I would definitely advise a cloud-native strategy, in which you consume everything you need in terms of resources for your operation from the cloud. 
If you already own an on-premise IT infrastructure, whether in your own data center or colocation, and will be operating services both on-premise and in the cloud in the future, then we are talking about a hybrid cloud model. Whether you choose this hybrid model only for the period of migration to the cloud or beyond is up to you. As described above, you define this path. Because it is your path!

The public cloud defines different service models from which you can consume its services. The three most popular cloud service models are:

**IaaS** stands for "Infrastructure-as-a-Service" and includes things like, virtual machines, networking and storage.

**PaaS** stands for "Platform-as-a-Service" and includes things like Functions, Databases, Web Services, for example.

**SaaS** stands for "Software-as-a-Service" and here Microsoft 365 can be mentioned as an example.

The fourth model should also be said.

**XaaS** stands for "Anything-as-a-Service" and describes a general category of services related to cloud computing and remote access. This covers a large number of products, tools and technologies that are provided as a service to users via the Internet.

There are also many other "-as-a-service" offerings, but I won't go into them here. 

When combining several private & public cloud models, we usually speak of multi-cloud environments. These can also be part of your strategy. 

## Assessment, MVP and Proof-of-Concept
You have now thought about your future strategy and would now like to find out whether your personal strategy is feasible. Then it is time to pick out a few special cases, so-called use cases, which are to be migrated and subject them to an assessment. If you find that you would like to test this use case, then define a Minimum Viable Product (MVP for short) for this if you are from product development and otherwise carry out a Proof-of-Concept (PoC for short). Both will provide you with an end result where you will have learned a lot about yourself and the migration to the cloud in a very short time. You can now use all of this for the rest of your topics. Always make sure to transport knowledge to the other departments in your company. Document everything and every step. Also create a Statement of Work (SoW for short), partically the performance description of the MVP or PoC. Write down what was implemented and what was not, with reasons. Discuss the result in the CCoE team and give it some thought. Do you continue or does the overall strategy need to be adjusted. Do you need other cloud models, or can you continue on your planned path. Refine your overall roadmap with these results and work them into your strategy.

## Azure Services
In this section, I go into existing services from the cloud provider Microsoft. Based on my experience, I will show you in short points which service you can use for what. This article is about a cloud strategy, but I would also like to take the opportunity to give you a few more important points to consider in advance. Many companies are already using Microsoft products these days, so it's basically easier to take a closer look at the topics and see where you can combine the familiar with the new.

If you have Active Directory in use these days and want to move toward the cloud, you can turn to Microsoft's **Azure Active Directory** identity management. With this powerful service, you extend user and service control toward the cloud in the hybrid model. Things like **Single Sign-On**, or **Multi-Factor Authentication** become possible. With this, you have already implemented a building block for connecting your on-premise world with the cloud. In the further course we will deal with IaaS. For IaaS to work, you need a virtual network in the cloud where you can deploy your **virtual machines**. With **Privileged Identity Management** and **Just-in-time access**, you can control access to these machines. You also have the ability to configure the virtual machines via **Desired State Configuration**. With **Microsoft Defender for the Cloud**, you can secure the machines and services in Azure against attacks. 

And there are countless other ways to connect services to the on-premise infrastructure. As mentioned above, there are servers and applications that should not or cannot be moved to the cloud. But you still want to manage these servers and applications from the cloud. There are solutions for this as well.

**Azure Arc** is a comprehensive and relatively new Azure service designed for hybrid and multi-cloud models. It connects the different worlds and makes it possible to manage from within Azure. With Arc, for example, you install an agent on virtual machines (Windows or Linux). This then has a connection to Azure. This enables you to manage topics such as configuration management, automation, monitoring, security & policy towards on-premise infrastructure. You can also connect existing Kubernetes clusters to Azure Arc, or integrate your existing VMware environment. In addition, there are **Arc-enabled data services**, such as **SQL managed instances**, but also **Arc-enabled application services** are possible, such as **App Services**, or **Functions**.

With **Azure Stack HCI**, as an integrated service from various vendors, even more options come into your IT infrastructure to manage Azure services on-premises in conjunction with Azure Arc. You have the ability to deploy and manage **Azure Kubernetes Service** on Azure Stack HCI in your data center or colocation location via the Arc management console. However, you can also deploy Azure Stack HCI as an on-premise hypervisor and provision virtual machine. The management of the Azure Stack HCI is done by the **Windows Admin Center**. You can also register the HCI Stack in Azure via WAC. Alternatively, Powershell is available. Registration is required because billing is done via the **Azure subscription**.

It is also possible to use the Microsoft licensing cost advantage via **Azure Hybrid Benefit**. This gives you more freedom in the area of overall licensing from Microsoft. This includes licenses for Windows Server, but also SQL Server and others.

## Summary
In conclusion, without a clearly defined strategy for you, you will not move forward. If you just start migrating services to the cloud in the blue, I promise you that you will not be happy. The likelihood that you will go through the migration again is very high. Believe me, it burns energy, personnel and costs enormous money.
