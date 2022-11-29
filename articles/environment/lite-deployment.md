---
title: Deploy Project Operations Lite
description: This article provides information about how to install Project Operations lite deployment - deal to proforma invoicing.
author: stsporen
ms.date: 11/29/2022
ms.topic: article
ms.reviewer: johnmichalak
ms.author: stsporen
---

# Deploy Project Operations Lite

_**Applies To:** Lite deployment - deal to proforma invoicing_



Project Operations supports multiple deployment models. To determine the best deployment model, see [Deployment types](determine-deployment-type.md).


> [!IMPORTANT]
> This deployment, Lite deployment – deal to proforma invoicing, results in a **Dataverse-only deployment of Project Operations**.

- [Install Project Operations into a new Dataverse environment](#new)
- [Install into an existing Dataverse environment](#existing)
- [Install into an existing Dataverse environment that has Dual write components](#existingdw)



## <a name="new"></a>Install Project Operations Lite to a new Dataverse environment

1. As the [Global or Power Platform Administrator](/power-platform/admin/global-service-administrators-can-administer-without-license) with a Project Operations license, create a new Dataverse environment in the [PowerPlatform admin center](https://admin.powerplatform.com). Make sure that **Create a database for this environment** and **Dynamics 365 Apps** are enabled. For more information, see [Create and manage environments in the Power Platform admin center](/power-platform/admin/create-environment#create-an-environment-in-the-power-platform-admin-center).
1. Select **Microsoft Dynamics 365 Project Operations** from the deployment list of Dynamics 365 apps.


## <a name="existing"></a>Install Project Operations Lite to an existing Dataverse environment 
1. As the [Global or Power Platform Administrator](/power-platform/admin/global-service-administrators-can-administer-without-license) with a Project Operations license, locate the environment in the [PowerPlatform admin center](https://admin.powerplatform.com) where you want to install Project Operations.
1. Install **Microsoft Dynamics 365 Project Operations** from the deployment list of Dynamics 365 apps. For more information, see [Manage Dynamics 365 apps](/power-platform/admin/manage-apps).

## <a name="existingdw"></a>Install Project Operations Lite to an existing Dataverse environment where Dual write solutions are already present

If you want to continue running Project Operations in Lite Deployment mode, you should follow these steps:

1. As the [Global or Power Platform Administrator](/power-platform/admin/global-service-administrators-can-administer-without-license) with a Project Operations license, locate the environment in the [PowerPlatform admin center](https://admin.powerplatform.com) where you want to install Project Operations.
1. Install **Microsoft Dynamics 365 Project Operations** from the deployment list of Dynamics 365 apps. For more information, see [Manage Dynamics 365 apps](/power-platform/admin/manage-apps).
1. Because your environment has Dual write components that help with integration to finance and operations apps installed, Project Operations installation will also install the capabilities and extensions required to integrate Project related data to finance and operations apps. Since you want to run Project Operations in Lite deployment, these integration components should be removed as they will create restrictions and overhead for Lite deployment scenarios. Manually uninstall the solutions **Dynamics 365 Project Operations Dual Write** and **Dynamics 365 Project Operations Dual Write Entity Maps** to remove these components.
1. Go to **Project Operations -> Settings -> Parameters**. Open the **Project Parameter** details page and set the **Solution Upgrade Behavior** field to **Lite Only**. This ensures that any subsequent upgrades of Project Operations won't bring back the integration components into Project Operations.  

[!INCLUDE[footer-include](../includes/footer-banner.md)]
