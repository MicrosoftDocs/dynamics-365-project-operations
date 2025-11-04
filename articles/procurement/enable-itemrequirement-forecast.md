---
title: Managed item requirements using item forecasts for Project Operations integrated with ERP deployment.
description: Learn how to manage and generate item requirements for stocked products using item forecasts in Microsoft Dynamics 365 Project Operations integrated with ERP deployment.
author: mukumarm
ms.date: 11/04/2025
ms.topic: how-to
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak
ms.author: mukumarm
---
## Item requirements using project item forecasts

[!INCLUDE[banner](../includes/banner.md)]

_**Applies To:** Project Operations integrated deployments._

**Item requirements** enable the consumption of materials directly from stock through the **sales order** cycle. This functionality allows users to **generate** item requirements based on project **item forecasts** and subsequently 
execute the material consumption process using packing slips. 

**Item forecasts** are generated using the project material estimates in **Dynamics 365 Project operations** Dataverse.

## Prerequisites

### Features

To use the functionality, activate the following features:
- **Enable stocked products usage for project operations integrated deployments** in Dynamics 365 Finance
- **Enable stocked products usage for project operations integrated deployments** in Dynamics 365 Project Operations

### Minimum versions required

To use the feature for Project Operations integrated deployments, you must have the following versions:

- **Project Operations Dataverse** version 4.161.0.x or later
- **Dynamics 365 Finance** version 10.0.46 or later

### Run dual-write maps

This section provides information about the specific maps that are required for stocked products. These dual-write maps are related to the Dynamics 365 Supply Chain solution. Learn about dual-write entities for the Dynamics 365 Supply Chain solution in [Unified product experience](/dynamics365/fin-ops-core/dev-itpro/data-entities/dual-write/product-mapping).

| Dual-write map | Version |
|---|---|
| Project material usage create (msdyn_materialusagelogs) | 1.0.0.0 |

### Process flow
To generate item requirements from item forecasts, follow these steps:

1. Go to the **project** form and select the project.
   **Project management and accounting** > **Projects** > **All projects**
2. On the **Plan** action pane, **Click Item forecasts**.
3. Click **Create item requirements**.

To consume the material from stock for the item requirements, follow these steps:
1. Go to the **project** form and select the project.
   **Project management and accounting** > **Projects** > **All projects**
2. On the **Plan** action pane, **Item requirements**.
3. On the **Manage** action pane, click **Posting** > **Packing slip**.

For each **packing slip** posted against **item requirements** in **Dynamics 365 Finance**, a project subledger entry is created, and the associated project cost is recorded. 
Simultaneously, for every packing slip line, a corresponding **material usage entry** is automatically created using **dual write** and automatically approved in **Dynamics 365 Project Operations**. This process generates **project cost actuals** for the material usage, and if the project is linked to a project contract, it also creates **unbilled sales actuals**.

When the integration journal is created using the **Import from staging** process, no journal lines are generated for project cost actuals, as these costs have already been recorded during the packing slip posting in **Dynamics 365 Finance**.

> [!NOTE]
> Item requirements are exclusively generated for stocked products. Manual creation of item requirements is not supported or applicable within the system.
