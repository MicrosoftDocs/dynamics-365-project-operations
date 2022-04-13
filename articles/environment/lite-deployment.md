---
title: Deploy Project Operations - lite
description: This topic provides information about how to install Project Operations lite deployment - deal to proforma invoicing.
author: stsporen
ms.date: 02/28/2022
ms.topic: article
ms.reviewer: johnmichalak
ms.author: stsporen
---

# Deploy Project Operations - lite

_**Applies To:** Lite deployment - deal to proforma invoicing_



Project Operations supports multiple deployment models. To determine the best deployment model, see [Deployment types](determine-deployment-type.md).


> [!IMPORTANT]
> This deployment, Lite deployment – deal to proforma invoicing, results in a **Dataverse-only deployment of Project Operations**.

- [Install Project Operations into a new Dataverse environment](#new)
- [Install into an existing Dataverse environment](#existing)



## <a name="new"></a>Install Project Operations to a new Dataverse environment

1. As the [Global or Power Platform Administrator](/power-platform/admin/global-service-administrators-can-administer-without-license) with a Project Operations license, create a new Dataverse environment in the [PowerPlatform admin center](https://admin.powerplatform.com). Make sure that **Create a database for this environment** and **Dynamics 365 Apps** are enabled. For more information, see [Create and manage environments in the Power Platform admin center](/power-platform/admin/create-environment#create-an-environment-in-the-power-platform-admin-center).
2. Select **Microsoft Dynamics 365 Project Operations** from the deployment list of Dynamics 365 apps.


## <a name="existing"></a>Install Project Operations to an existing Dataverse environment
1. Ensure that the environment has not been configured with [dual-write](/dynamics365/fin-ops-core/dev-itpro/data-entities/dual-write/dual-write-overview) as installation will then install the [Project Operations for resource/non-stocked based scenarios](project-operations-integrated-deployment-overview.md) capabilties.
2. As the [Global or Power Platform Administrator](/power-platform/admin/global-service-administrators-can-administer-without-license) with a Project Operations license, locate the environment in the [PowerPlatform admin center](https://admin.powerplatform.com) where you want to install Project Operations.
3. Install **Microsoft Dynamics 365 Project Operations** from the deployment list of Dynamics 365 apps. For more information, see [Manage Dynamics 365 apps](/power-platform/admin/manage-apps).




[!INCLUDE[footer-include](../includes/footer-banner.md)]
