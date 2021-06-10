---
title: Manually deploy Project Operations Dataverse with dual-write support 
description: This topic explains how to manually deploy the Project Operations Dataverse app with dual-write support.
author: stsporen
ms.date: 06/10/2021
ms.topic: article
ms.reviewer: kfend 
ms.author: stsporen
---
# Manually deploy Project Operations Dataverse with dual-write support

_**Applies To:** Project Operations for resource/non-stocked based scenarios_

This topic explains how to manually deploy Dynamics 365 Project Operations in Dynamics 365 Dataverse with dual-write support. Project Operations detects the environments configuration and adds additional support for Dual-write if the pre-requisites are available.
During LCS deployment, if you have followed the steps in this topic, you can skip the *Power Platform Environment Setting*, because you will already have the correct setup.

The following four procedures are required to deploy Project Operations in Dataverse with dual-write support:

  1. [Create a new environment in Dataverse with dual-write support](#create)
  2. [Add dual-write prerequisites to the environment](#prerequisites)
  3. [Add the Project Operations Dataverse app](#dataverse)
  4. [Link your environments](#link)

## <a name="create">Create a new environment in Dataverse with dual-write support</a>
To complete the following steps, log in as an administrator.
1.	Go to the [Power Platform Admin center](https://admin.powerplatform.com), and create a new environment.
2.	Name the environment and then select the environment type. If you signed up for the trial offer, select **Trial (subscription-based)**.
4.	Confirm the deployment region and then enable the field, **Create a database for this environment**. 
6.	Confirm the language and then confirm that the currency matches the currency for your Dynamics 365 Finance and Operations apps.
8.	Enable **Dynamics 365 apps** and verify that the **Automatically deploy these apps** field is set to **None**.
10.	Add a security group if required, and then wait for the environment to complete it's provision.


## <a name="prerequisites">Add dual-write prerequisites to the environment</a>
Dual-write support includes additional fields that are added to key entities, such as **Company**. If you are adding this support to an existing environment, you may have to update the data to enable the support. For information about how to bootstrap the data, see [Bootstrap company data](/dynamics365/fin-ops-core/dev-itpro/data-entities/dual-write/bootstrap-company-data). For more details about dual-write, see [Dual-write system requirements](/dynamics365/fin-ops-core/dev-itpro/data-entities/dual-write/dual-write-system-req). 

Complete the following steps to add the dual-write prerequisites to your environment. 

1.	Open the environment you just created and then go to **Resource** > **Dynamics 365 apps**.
2.	From the app list, select and install, **Dual-write core solution**.
3.	When the installation is complete, from the app list, select and install **Dual-write application orchestration solution**.

## <a name="dataverse">Add the Project Operations Dataverse app</a>
Before you complete the steps in this procedure, you must have completed the steps in the previous sections prior to installing Project Operations. During installation, the system checks to see what the environment configuration is and then adds support for dual-write if required.

1. Open the environment you just created and then go to **Resource** > **Dynamics 365 apps**.
2. From the app list, select and install, **Microsoft Dynamics 365 Project Operations**.

## <a name="link">Link your environments</a>
After the Dataverse environment is deployed, you will set up the link in your Finance and Operations apps. Complete the steps in the topic, [Use the dual-write wizard to link your environments](/dynamics365/fin-ops-core/dev-itpro/data-entities/dual-write/link-your-environment).

