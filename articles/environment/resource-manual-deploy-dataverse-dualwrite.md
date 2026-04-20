---
title: Manually deploy the Project Operations Dataverse app with dual-write support
description: This article explains how to manually deploy the Project Operations Dataverse app so that it supports dual-write.
author: mukumarm
ms.author: mukumarm
ms.date: 02/27/2026
ms.topic: how-to
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak

---

# Manually deploy the Project Operations Dataverse app with dual-write support

[!INCLUDE[banner](../includes/banner.md)]

_**Applies To:** Project Operations Integrated with ERP_

This article explains how to manually deploy Microsoft Dynamics 365 Project Operations in Microsoft Dataverse so that it supports dual-write. Project Operations detects the environment's configuration and adds extra support for dual-write if the prerequisites are met.

If you follow the instructions in this article, you can skip the deployment of the Microsoft Power Platform integration (previously known as the Common Data Service environment) during deployment through Microsoft Dynamics Lifecycle Services.

The process of deploying Project Operations in Dataverse so that it supports dual-write has four main steps:

1. [Create a new environment in Dataverse that supports dual-write](#create).
1. [Add dual-write prerequisites to the environment](#prerequisites).
1. [Add the Project Operations Dataverse app](#dataverse).
1. [Link your environments](#link).

## <a name="create"></a>Create a new environment in Dataverse that supports dual-write

To complete this procedure, you must sign in as an administrator.

1. Open the [Power Platform admin center](https://admin.powerplatform.com), and sign in as an administrator.
1. Create a new environment, and name it.
1. Select the environment type. If you signed up for the trial offer, select **Trial (subscription-based)**.
1. Confirm the deployment region.
1. Enable the **Create a database for this environment** option. 
1. Confirm the language, and then confirm that the currency matches the currency for your finance and operations apps.
1. Enable the **Dynamics 365 apps** option, and confirm that the **Automatically deploy these apps** field is set to **None**.
1. Add a security group, if a security group is required.
1. Select **Save** to create the environment.
1. Wait until the deployment is completed and the environment reaches the **Ready** state.

## <a name="prerequisites"></a>Add dual-write prerequisites to the environment

Dual-write support includes extra fields that are added to key entities, such as the **Company** entity. If you're adding dual-write support to an existing environment, you might need to update the data to enable the support. For information about how to bootstrap the data, see [Bootstrap company data](/dynamics365/fin-ops-core/dev-itpro/data-entities/dual-write/bootstrap-company-data). For more information about dual-write, see [Dual-write system requirements](/dynamics365/fin-ops-core/dev-itpro/data-entities/dual-write/dual-write-system-req).

Complete this procedure to add the dual-write prerequisites to your environment.

1. Open the environment that you created, and then go to **Resource** \> **Dynamics 365 apps**.
1. Select **Dual-write core solution** in the app list, and install it.
1. Wait until the installation is complete. Then select each of the following packages in the app list and install them.
   - Dual-write Application Core package
   - Dual-write Finance package
   - Dual-write Supply Chain package
   - Dual-write Asset Management package
   - Dual-write Human Resources package

    For more information about the Separated Dual-write Application Orchestration package and the packages required for Project Operations, see [Separated Dual-write Application Orchestration package](/dynamics365/fin-ops-core/dev-itpro/data-entities/dual-write/separated-solutions#Packages-required-for-project-operations).

## <a name="dataverse"></a>Add the Project Operations Dataverse app

You can complete this procedure only if you completed the previous procedures before you installed Project Operations. During installation, the system analyzes the environment configuration and adds support for dual-write if it's required.

1. Open the environment that you created earlier, and then go to **Resource** \> **Dynamics 365 apps**.
1. Select **Microsoft Dynamics 365 Project Operations** in the app list, and install it.

## <a name="link"></a>Link your environments

After the Dataverse environment is deployed, you can set up the link in your finance and operations apps. Follow the steps in [Enable Power Platform Integration](/dynamics365/fin-ops-core/dev-itpro/power-platform/enable-power-platform-integration).
