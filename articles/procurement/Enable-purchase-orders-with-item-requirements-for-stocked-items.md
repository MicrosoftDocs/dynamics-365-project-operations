---
title: Enable project purchase orders with item requirements for stocked items in Project Operations Integrated with ERP
description: Learn how to manage auto-creation of item requirements for stocked products using project purchase orders in Dynamics 365 Project Operations integrated with ERP deployment.
author: sarangkusare
ms.date: 10/22/2026
ms.topic: how-to
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak
ms.author: sarangkusare
---

# Manage project purchase orders with auto-created item requirements for stock items 

[!INCLUDE [banner](../includes/banner.md)]

_**Applies To:** Project Operations Integrated with ERP_

This feature streamlines the procurement and material consumption process for stocked items by automatically generating item requirements from purchase orders. The feature uses the configuration of the **Create Item Requirement** and **Item Consumption** parameters to determine how to generate these item requirements.

When you enable the feature, it creates item requirements from purchase orders in finance and operations apps, reducing manual effort and minimizing delays in project procurement activities. In addition, when you post a packing slip for an item requirement in finance and operations apps, the system automatically creates a corresponding **Material Usage** transaction on the project in Project Operations through dual-write synchronization.

This integration helps ensure that project material consumption is accurately tracked across applications without requiring manual updates.

Organizations that use stocked materials in project-based work can improve operational efficiency by automating the flow of procurement and material consumption data between finance and operations apps and Project Operations. This automation helps maintain accurate project costing while reducing the risk of manual errors and delayed updates.

## Key benefits

- Reduces manual data entry and administrative effort.
- Accelerates procurement and material tracking processes.
- Improves accuracy by synchronizing material consumption between finance and operations apps and Project Operations.
- Ensures project costs and material usage are reflected in real time.
- Eliminates the need for duplicate transaction entry across applications.

## Prerequisites

Before using this feature, ensure you meet the following prerequisites.

### Features

To use this functionality, activate **Enable purchase orders with item requirements for stocked items in Project Operations integrated with ERP** in Dynamics 365 Finance.

### Minimum versions required

To use this feature for Project Operations integrated deployments, have the following versions:

- **Project Operations Dataverse** version 4.171.0.x or later
- **Finance** version 10.0.49 or later

### Dual-write configuration requirements

To ensure successful synchronization of Project Vendor Invoice Lines between Project Operations and Finance, verify that the required dual-write map is deployed, active, and running the latest supported version.

- Enable and run successfully the **Project Operations Integration Project Vendor Invoice Line Export Entity (msdyn_projectvendorinvoicelines)** dual-write map.
- Use version **1.0.0.10 or later** of the dual-write map.
- Upgrade to the latest available version if you deployed an earlier version of the map before enabling this functionality.
- Validate that the dual-write map is in a **Running** state with no synchronization errors before testing or production use.

## How it works

1. Create a purchase order for stocked items you need for a project.
1. Based on the **Create Item Requirement** and **Item Consumption** settings, the system automatically generates the associated item requirements.
1. Receive the purchased items and post a packing slip in finance and operations apps.
1. Dual-write synchronizes the transaction with Project Operations.
1. A Material Usage transaction is automatically created against the project in Project Operations.
1. Project managers and accountants can track material consumption directly from the project.

## Example scenario

Contoso Construction is managing a building renovation project and needs 100 bags of cement for project execution.

- A procurement manager creates a purchase order for 100 bags of cement in finance and operations apps.
- The system automatically generates the required item requirement for the project.
- The supplier delivers the cement, and the warehouse posts the packing slip in finance and operations apps.
- Once the packing slip is posted, dual-write automatically creates a Material Usage transaction in Project Operations.
- The project team can immediately see that the cement is consumed by the project without manually recording the material usage.

As a result, procurement, inventory, and project accounting processes remain synchronized, providing more accurate project cost tracking and reducing operational overhead.
