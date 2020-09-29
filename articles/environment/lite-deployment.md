---
# required metadata

title: Lite Deployment
description: This topic provides information about how to install the lite deployment model for Project Operations.
author: stsporen
manager: gurkans
ms.date: 06/19/2020
ms.topic: article
ms.prod: 
ms.service: dynamics-project-operations
ms.technology: 

# optional metadata

# ms.search.form: 
# ROBOTS: 
audience: ItPro; Developer
# ms.devlang: 
ms.reviewer: kfend
ms.search.scope: 
# ms.tgt_pltfrm: 
ms.custom: 
ms.assetid: 
ms.search.region: 
ms.search.industry: 
ms.author: v-radsh
ms.dyn365.ops.version: 
ms.search.validFrom: 2020-10-01
---
# Deploying Project Operations Lite deployment – deal to proforma invoicing

Project Operations supports multiple deployment models, determine the best deployment model by reviewing [deployment types](deployment-types.md).


> [!IMPORTANT]
> This deployment results in a **Common Data Service only deployment of Project Operations**.

- [Installing Project Operations into a new CDS environment](##Installing-Project-Operations-into-a-new-CDS-environment)
- [Installing into an existing CDS environment](##Installing-Project-Operations-into-an-existing-CDS-environment)



## Installing Project Operations into a new CDS environment
1. As the Global Administrator or the Power Platform Administrator (see [Global admins and Power Platform admins](https://docs.microsoft.com/en-us/power-platform/admin/global-service-administrators-can-administer-without-license)) with a Project Operations license create a new CDS environment in the PowerPlatform admin center ([https://admin.powerplatform.com](https://admin.powerplatform.com)) with a **CDS database** and **Dynamics 365 Apps** enabled. (see [Create and manage environments in the Power Platform admin center](https://docs.microsoft.com/en-us/power-platform/admin/create-environment#create-an-environment-in-the-power-platform-admin-center))
2. Select **Microsoft Dynamics 365 Project Operations** from the deployment list of Dynamcis 365 apps.


## Installing Project Operations into an existing CDS environment
> []!NOTE]
>The Project Operations application will check to see of you have enabled dual write, if you have we will install the Project Operations dualwrite capabilities (see [Dual-write](https://docs.microsoft.com/en-us/dynamics365/fin-ops-core/dev-itpro/data-entities/dual-write/dual-write-home-page) for details about dual write)

1. As the Global Administrator or the Power Platform Administrator (see [Global admins and Power Platform admins](https://docs.microsoft.com/en-us/power-platform/admin/global-service-administrators-can-administer-without-license)) with a Project Operations license locate the environment where you would like to install Project Operations in 
the PowerPlatform admin center ([https://admin.powerplatform.com](https://admin.powerplatform.com)).
2. Install the **Microsoft Dynamics 365 Project Operations** from the deployment list of Dynamics 365 apps (see [Manage Dynamics 365 apps](https://docs.microsoft.com/en-us/power-platform/admin/manage-apps) for more details).


