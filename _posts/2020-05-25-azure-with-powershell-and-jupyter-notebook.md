---
id: 253
title: 'Azure deployments with Powershell and Jupyter Notebook - Step-by-Step experience'
date: 2020-05-25T18:46:29+01:00
author: Mr.AzureStack
layout: blog
guid: https://azurestack.info/?p=253
permalink: /azure-with-powershell-and-jupyter-notebook
categories:
  - Blog
  - Jupyter Notebook
  - Azure Stack Hub
  - Grundlagen
tags:
  - Azure
  - Azure Stack Hub
  - Jupyter
  - Powershell
---

## General

I love performing deployments in Azure via Powershell. This saves time and simplifies your daily work in the operation of customers. Above all, it is an asset for IT service providers. This makes it possible to automate recurring tasks. So far I have always worked with the Powershell Console. Since Build 2020 I also work with Windows Terminal and most recently with Jupyter Notebook. And that&#8217;s what this blog post is all about. As an alternative, Microsoft presented Visual Studio Codespaces at Build 2020. It&#8217;s going in the same direction. The goal is that Dev Teams can work on code at the same time.

## 

## What is ?

Jupyter Notebook is an open-source web application that allows you to create live code. to share with others, or to work on it at the same time. Jupyter Notebook does not support Powershell until March 2020. The tool is based on Python and can run both locally and in the cloud.


## Local installation

### What you need to install

First I had [PowerShell 7](https://github.com/PowerShell/PowerShell/releases/tag/v7.0.0), [Pythen](https://www.python.org/downloads/windows/) 3.8 and the [.NET SDK](https://dotnet.microsoft.com/download/dotnet-core/3.1) installed.

The next steps are:

  * Install .NET Interactive
  * Install JupyterLab
  * Register .NET Interactive

### How to install

You can use the command prompt (start as an admin):

<img loading="lazy" class="aligncenter size-full wp-image-258" src="https://azurestack.info/wp-content/uploads/2020/05/jupyter-notebook-install-net-interactive.jpg" alt="jupyter-notebook-install-net-interactive" width="729" height="157" srcset="https://azurestack.info/wp-content/uploads/2020/05/jupyter-notebook-install-net-interactive.jpg 729w, https://azurestack.info/wp-content/uploads/2020/05/jupyter-notebook-install-net-interactive-300x65.jpg 300w" sizes="(max-width: 729px) 100vw, 729px" /> 

After the installation close the command promt.

To install Jupyter Notebook with [PIP](https://jupyter.org/install.html) use Powershell (start as an admin):

<img loading="lazy" class="aligncenter size-full wp-image-259" src="https://azurestack.info/wp-content/uploads/2020/05/jupyter-notebook-install-jupyterlab.jpg" alt="jupyter-notebook-install-jupyterlab" width="467" height="128" srcset="https://azurestack.info/wp-content/uploads/2020/05/jupyter-notebook-install-jupyterlab.jpg 467w, https://azurestack.info/wp-content/uploads/2020/05/jupyter-notebook-install-jupyterlab-300x82.jpg 300w" sizes="(max-width: 467px) 100vw, 467px" /> 

After the installation close .Powershell

Now you must register the .NET Interactive with a command prompt (start as an admin):

<img loading="lazy" class="aligncenter size-full wp-image-261" src="https://azurestack.info/wp-content/uploads/2020/05/jupyter-notebook-register-net-interactive.jpg" alt="jupyter-notebook-register-net-interactive" width="614" height="147" srcset="https://azurestack.info/wp-content/uploads/2020/05/jupyter-notebook-register-net-interactive.jpg 614w, https://azurestack.info/wp-content/uploads/2020/05/jupyter-notebook-register-net-interactive-300x72.jpg 300w" sizes="(max-width: 614px) 100vw, 614px" /> 


The last step is to start Jupyter Notebook.

I have got myself a shortcut on the desktop first:

<img loading="lazy" class="aligncenter size-full wp-image-262" src="https://azurestack.info/wp-content/uploads/2020/05/jupyter-notebook-desktop-symbol.jpg" alt="jupyter-notebook-desktop-symbol" width="398" height="508" srcset="https://azurestack.info/wp-content/uploads/2020/05/jupyter-notebook-desktop-symbol.jpg 398w, https://azurestack.info/wp-content/uploads/2020/05/jupyter-notebook-desktop-symbol-235x300.jpg 235w" sizes="(max-width: 398px) 100vw, 398px" /> 


This is a shortcut to the command prompt. Add the extension &#8221; /C jupyter notebook&#8221; to target and give the shortcut a name.

This completes the installation.

## Configuration of Jupyter Notebook for Powershell

Next is the configuration of Jupyter Notebook for the use of Powershell Scripts, incl. all Az-Modules for this. To do this, start the created link. The web browser will open.

Next, we need to create a new notebook and specify the path to it.


<img loading="lazy" class="aligncenter size-full wp-image-266" src="https://azurestack.info/wp-content/uploads/2020/05/jupyter-notebook-new-powershell-notebook.jpg" alt="jupyter-notebook-new-powershell-notebook" width="1210" height="369" srcset="https://azurestack.info/wp-content/uploads/2020/05/jupyter-notebook-new-powershell-notebook.jpg 1210w, https://azurestack.info/wp-content/uploads/2020/05/jupyter-notebook-new-powershell-notebook-300x91.jpg 300w, https://azurestack.info/wp-content/uploads/2020/05/jupyter-notebook-new-powershell-notebook-1024x312.jpg 1024w, https://azurestack.info/wp-content/uploads/2020/05/jupyter-notebook-new-powershell-notebook-768x234.jpg 768w" sizes="(max-width: 1210px) 100vw, 1210px" /> 


<img loading="lazy" class="aligncenter size-full wp-image-269" src="https://azurestack.info/wp-content/uploads/2020/05/jupyter-notebook-powershell-notebook.jpg" alt="jupyter-notebook-powershell-notebook" width="1209" height="257" srcset="https://azurestack.info/wp-content/uploads/2020/05/jupyter-notebook-powershell-notebook.jpg 1209w, https://azurestack.info/wp-content/uploads/2020/05/jupyter-notebook-powershell-notebook-300x64.jpg 300w, https://azurestack.info/wp-content/uploads/2020/05/jupyter-notebook-powershell-notebook-1024x218.jpg 1024w, https://azurestack.info/wp-content/uploads/2020/05/jupyter-notebook-powershell-notebook-768x163.jpg 768w" sizes="(max-width: 1209px) 100vw, 1209px" /> 

Next step is to import the Azure Powersell Modules.

<img loading="lazy" class="aligncenter size-full wp-image-271" src="https://azurestack.info/wp-content/uploads/2020/05/jupyter-notebook-import-azure-powershell-modules.jpg" alt="jupyter-notebook-import-azure-powershell-modules" width="1199" height="230" srcset="https://azurestack.info/wp-content/uploads/2020/05/jupyter-notebook-import-azure-powershell-modules.jpg 1199w, https://azurestack.info/wp-content/uploads/2020/05/jupyter-notebook-import-azure-powershell-modules-300x58.jpg 300w, https://azurestack.info/wp-content/uploads/2020/05/jupyter-notebook-import-azure-powershell-modules-1024x196.jpg 1024w, https://azurestack.info/wp-content/uploads/2020/05/jupyter-notebook-import-azure-powershell-modules-768x147.jpg 768w" sizes="(max-width: 1199px) 100vw, 1199px" /> 


Now klick Run and wait. In the line between [ ] there is now a *. That means, that this line is running.

<img loading="lazy" class="aligncenter size-full wp-image-272" src="https://azurestack.info/wp-content/uploads/2020/05/jupyter-notebook-installation-azure-powershell-modules.jpg" alt="jupyter-notebook-installation-azure-powershell-modules" width="1203" height="438" srcset="https://azurestack.info/wp-content/uploads/2020/05/jupyter-notebook-installation-azure-powershell-modules.jpg 1203w, https://azurestack.info/wp-content/uploads/2020/05/jupyter-notebook-installation-azure-powershell-modules-300x109.jpg 300w, https://azurestack.info/wp-content/uploads/2020/05/jupyter-notebook-installation-azure-powershell-modules-1024x373.jpg 1024w, https://azurestack.info/wp-content/uploads/2020/05/jupyter-notebook-installation-azure-powershell-modules-768x280.jpg 768w" sizes="(max-width: 1203px) 100vw, 1203px" /> 


After that is ready you can use this Notebook with your Powershell Code.


## Connect to Azure or Azure Stack Hub

When you run the next line with: Connect-AzAccount you can connect to Azure.

<img loading="lazy" class="aligncenter size-full wp-image-273" src="https://azurestack.info/wp-content/uploads/2020/05/jupyter-notebook-connect-to-azure.jpg" alt="jupyter-notebook-connect-to-azure" width="1193" height="323" srcset="https://azurestack.info/wp-content/uploads/2020/05/jupyter-notebook-connect-to-azure.jpg 1193w, https://azurestack.info/wp-content/uploads/2020/05/jupyter-notebook-connect-to-azure-300x81.jpg 300w, https://azurestack.info/wp-content/uploads/2020/05/jupyter-notebook-connect-to-azure-1024x277.jpg 1024w, https://azurestack.info/wp-content/uploads/2020/05/jupyter-notebook-connect-to-azure-768x208.jpg 768w" sizes="(max-width: 1193px) 100vw, 1193px" /> 

Go to the website and enter the code.

This is the hole guide for using Jupyter Notebook with Powershell.

At the end you can safe this Notebook to a folder in One Drive for Business, or MS Teams. Or you can install Jupyter Notebook in an Azure Virtual Machine.

Let your mind run wild... 😉

