---
title: 'Azure deployments with Powershell and Jupyter Notebook - Step-by-Step experience'
permalink: /azure-with-powershell-and-jupyter-notebook
layout: single
categories:
  - Jupyter Notebook
  - Azure Stack Hub
  - Grundlagen
tags:
  - Azure
  - Azure Stack Hub
  - Jupyter
  - Powershell
---

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

![Install Net](/assets/images/jupyter-notebook-install-net-interactive-300x65.jpg)


After the installation close the command promt.

To install Jupyter Notebook with [PIP](https://jupyter.org/install.html) use Powershell (start as an admin):

![Install Jupiterlab](/assets/images/jupyter-notebook-install-jupyterlab-300x82.jpg)


After the installation close .Powershell

Now you must register the .NET Interactive with a command prompt (start as an admin):

![Register Net](/assets/images/jupyter-notebook-register-net-interactive-300x72.jpg)


The last step is to start Jupyter Notebook.

I have got myself a shortcut on the desktop first:

![Desktop Symbol](/assets/images/jupyter-notebook-desktop-symbol-235x300.jpg)


This is a shortcut to the command prompt. Add the extension &#8221; /C jupyter notebook&#8221; to target and give the shortcut a name.

This completes the installation.

## Configuration of Jupyter Notebook for Powershell

Next is the configuration of Jupyter Notebook for the use of Powershell Scripts, incl. all Az-Modules for this. To do this, start the created link. The web browser will open.

Next, we need to create a new notebook and specify the path to it.


![New Powershell Notebook](/assets/images/jupyter-notebook-new-powershell-notebook-1024x312.jpg)


![Powershell Notebook](/assets/images/jupyter-notebook-powershell-notebook-1024x218.jpg)


Next step is to import the Azure Powersell Modules.

![Import Powershell Modules](/assets/images/jupyter-notebook-import-azure-powershell-modules-1024x196.jpg)


Now klick Run and wait. In the line between [ ] there is now a *. That means, that this line is running.

![Install Powershell Modules](/assets/images/jupyter-notebook-installation-azure-powershell-modules-1024x373.jpg)


After that is ready you can use this Notebook with your Powershell Code.


## Connect to Azure or Azure Stack Hub

When you run the next line with: Connect-AzAccount you can connect to Azure.

![Connect to Azure](/assets/images/jupyter-notebook-connect-to-azure-1024x277.jpg)


Go to the website and enter the code.

This is the hole guide for using Jupyter Notebook with Powershell.

At the end you can safe this Notebook to a folder in One Drive for Business, or MS Teams. Or you can install Jupyter Notebook in an Azure Virtual Machine.

Let your mind run wild... 😉

