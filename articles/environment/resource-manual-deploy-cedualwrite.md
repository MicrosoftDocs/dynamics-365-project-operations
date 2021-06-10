---
title: Manual deployment of Project Operations Dataverse app with Dual Write support 
description: This topic explains how to deploy the Project Operations Dataverse app with Dual Write support manually.
author: stsporen
ms.date: 06/10/2021
ms.topic: article
ms.reviewer: kfend 
ms.author: stsporen
---
# Manual deployment of Project Operations Dataverse app with Dual Write support 

_**Applies To:** Project Operations for resource/non-stocked based scenarios_

This document describes the steps required to deploy Project Operations in Dataverse with Dual Write support manually. Project Operations detects the environments configuration and adds additional support for Dual Write if the pre-requisites are available.
During LCS deployment, if you have followed this step then you are able to skip the Power Platform Environment (previously CDS) Setting, as you will have the correct setup already.

The followings four broad steps are required to deploy Project Operations in Dataverse with dual write support.

## 1. Creating a new environment in Dataverse with Dual Write support
1.	As the administrator login to Power [Platform Admin center](https://admin.powerplatform.com) and create a new environment.
2.	Add a *name* for the environment
3.	Choose a *type* of the environment, for users who have signed up for our trial offer select **Trial (subscription-based)** and not **Trial**.
4.	Confirm the *region* of the deployment
5.	Enable Create a database for this environment
6.	Confirm the *language*
7.	Confirm the *currency* matches the currency for Finance and Operations.
8.	Enable *Dynamics 365 apps*
9.	Ensure that Automatically deploy these apps is set to **None**
10.	Add a Security group if required
11.	Wait for the environment to provision

## 2. Adding Dual Write prerequisites to the environment
Dual write support includes additional fields that are added to key entities such as the Company field, if adding this to an existing environment you may have to update the data to enable support (see [bootstrap company data](https://docs.microsoft.com/en-us/dynamics365/fin-ops-core/dev-itpro/data-entities/dual-write/bootstrap-company-data) for how to bootstrap the data). For more details around Dual write see [Dual write system requirements](https://docs.microsoft.com/en-us/dynamics365/fin-ops-core/dev-itpro/data-entities/dual-write/dual-write-system-req).
1.	Select the newly created environment
2.	Open **Resource | Dynamics 365 apps** from the toolbar
3.	Install **Dual-write core solution** from the app list
4.	Wait for the installation to complete
5.	Install **Dual-write application orchestration solution** from the app list
6.	Wait for the installation to complete

## 3. Adding Project Operations Dataverse app
Be sure to have completed the above steps prior to installing Project Operations, during installation the system checks to see what the configuration is of the environment and adds support for dual write if required.
1.	Select the newly created environment
2.	Open **Resource | Dynamics 365** apps from the toolbar
3.	Install **Microsoft Dynamics 365 Project Operations** from the app list

## 4. Link your environments
After deployment of the Dataverse environment you will continue within F&O to setup the link. Follow these steps to establish the link using the Dual write wizard.
https://docs.microsoft.com/en-us/dynamics365/fin-ops-core/dev-itpro/data-entities/dual-write/link-your-environment
