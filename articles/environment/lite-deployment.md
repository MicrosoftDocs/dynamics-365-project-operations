---
title: Deploy Project Operations  Core
description: Learn how to install Project Operations Core with step-by-step instructions for new or existing Dataverse environments. Start your deployment today!
author: stsporen
ms.date: 01/30/2026
ms.topic: how-to
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak
ms.author: rumant
---

# Deploy Project Operations  Core

[!INCLUDE[banner](../includes/banner.md)]

_**Applies To:** Project Operations Core_

Project Operations supports multiple deployment models. To determine the best deployment model, see [Deployment types](determine-deployment-type.md).

> [!IMPORTANT]
> This deployment, Project Operations Core – deal to proforma invoicing, results in a **Dataverse-only deployment of Project Operations**.

- [Install Project Operations into a new Dataverse environment](#new)
- [Install into an existing Dataverse environment](#existing)
- [Install into an existing Dataverse environment that has Dual write components](#existingdw)

## <a name="new"></a>Install Project Operations  Core to a new Dataverse environment

1. As the [Global or Power Platform Administrator](/power-platform/admin/global-service-administrators-can-administer-without-license) with a Project Operations license, create a new Dataverse environment in the [PowerPlatform admin center](https://admin.powerplatform.com). Make sure that **Create a database for this environment** and **Dynamics 365 Apps** are enabled. For more information, see [Create and manage environments in the Power Platform admin center](/power-platform/admin/create-environment#create-an-environment-in-the-power-platform-admin-center).
1. Select **Microsoft Dynamics 365 Project Operations** from the deployment list of Dynamics 365 apps.

## <a name="existing"></a>Install Project Operations  Core to an existing Dataverse environment

1. As the [Global or Power Platform Administrator](/power-platform/admin/global-service-administrators-can-administer-without-license) with a Project Operations license, locate the environment in the [PowerPlatform admin center](https://admin.powerplatform.com) where you want to install Project Operations.
1. Install **Microsoft Dynamics 365 Project Operations** from the deployment list of Dynamics 365 apps. For more information, see [Manage Dynamics 365 apps](/power-platform/admin/manage-apps).

## <a name="existingdw"></a>Install Project Operations  Core to an existing Dataverse environment where Dual write solutions are already present

If you want to continue running Project Operations in Project Operations Core mode, follow these steps:

1. As the [Global or Power Platform Administrator](/power-platform/admin/global-service-administrators-can-administer-without-license) with a Project Operations license, locate the environment in the [PowerPlatform admin center](https://admin.powerplatform.com) where you want to install Project Operations.
1. Install **Microsoft Dynamics 365 Project Operations** from the deployment list of Dynamics 365 apps. For more information, see [Manage Dynamics 365 apps](/power-platform/admin/manage-apps).
1. Because your environment has dual-write components that help with integration to finance and operations apps, the Project Operations installation also installs the capabilities and extensions required to integrate project related data to finance and operations apps. Since you want to run Project Operations in Core deployment, remove these integration components. Manually uninstall the solutions **Dynamics 365 Project Operations Dual Write** and **Dynamics 365 Project Operations Dual Write Entity Maps** to remove these components.
1. Go to **Project Operations -> Settings -> Parameters**. Open the **Project Parameter** details page and set the **Solution Upgrade Behavior** field to **Project Operations Core Only**. This setting ensures that any subsequent upgrades of Project Operations don't bring back the integration components into Project Operations.
1. Go to **Project Operations -> Settings -> Parameters**. Open the **Project Parameter** details page and open the tab **Pricing Dimensions**. Remove `msdyn_OwningCompany`, `msdyn_ResourcingCompany`, and `msdyn_IsInterCompany` records from the **Amount - based Pricing dimensions** grid. Deleting pricing dimensions records requires the **Role Prices** table to be empty. Export data from this table before attempting to delete pricing dimensions. After pricing dimension records are removed, re-import records to the **Role Prices** table.
1. Go to **Actuals Configuration** table and remove records for Owning Company and Resourcing Company.

> [!Note]
> Removing `msdyn_OwningCompany` and `msdyn_IsInterCompany` records from the pricing dimensions table requires plugin disablement. Submit a Microsoft support ticket to do this. Once the plugins are disabled, delete `msdyn_OwningCompany` and `msdyn_IsInterCompany` records from the pricing dimensions table and re-enable the plugins. Re-enabling the plugins is required for proper working of Project Operations applications.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
