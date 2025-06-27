---
title: Move to the modern architecture
description: Learn how to use the modern architecture and move to the Project Operations Integrated with ERP deployment if you have a legal entity that currently uses the Project Operations for manufacturing order deployment.
#customer intent: As an IT admin, I want to enable the modern architecture for existing legal entities with project data so that I can improve project management capabilities.
author: ryansandness
ms.date: 03/11/2025
ms.topic: how-to
ms.custom:
  - bap-template
ms.reviewer: johnmichalak
ms.search.region: Global
ms.author: ryansandness
ms.search.validFrom: 2025-03-03T00:00:00.000Z
ms.dyn365.ops.version: null
---
# Move to the modern architecture

As of version 10.0.43, if you use the **Project management and accounting** module to manage your projects, you can use the modern architecture of Microsoft Dynamics 365 Project Operations to take advantage of the new functionality and modern technology stack.

Many customers who previously used the project capabilities of the **Project management and accounting** module in the finance and operations architecture could not turn on the capabilities of the modern architecture of Project Operations in the same legal entity. This option is now available.

In the 10.0.43 release, the **Use the modern architecture for existing legal entities with project data** feature lets you complete all existing transactions and close existing projects in the **Project management and accounting** module. You can then create new projects, project-based quotes, and contracts by using richer, modern experiences that bring together the project management capabilities of Dataverse and finance and operations apps into one orchestrated, seamless experience. Data from Dataverse is automatically integrated into the same legal entity in finance and operations apps. Likewise, data from finance and operations apps is automatically integrated into Dataverse. 

By adopting the modern architecture, you can take advantage of the following features without losing the benefit of the rich project accounting and invoicing capabilities of finance and operations apps:

- Project contract structure
- Sales process
- Project planning functionality that uses Microsoft Project for the web
- Resource management that uses Unified resource management
- Transaction models
- Subcontracting
- Proforma invoice processes

## Enable the modern architecture of Project Operations

At a minimum, you must follow these steps to enable the modern architecture in a legal entity that has project data.

> [!IMPORTANT]
> Before you complete this procedure in a production environment, you should complete it in a sandbox environment and thoroughly test all project-related functionality.

1. Turn on the **Use the modern architecture for existing legal entities with project data** feature to remove the restriction that blocks this change in the deployment type.
1. Complete all project transactions, and ensure that the following conditions are met:

    - There are no pending project transactions.
    - All invoices are completed.
    - Revenue recognition and eliminations are completed.
    - No open documents remain against a project.

1. Move all projects to a closed status.
1. On the **Global project management and accounting parameters** page, select the legal entity to opt in to.

    > [!IMPORTANT]
    > Ensure that all project transactions are completed before you complete this step, because projects can't be reopened after you opt in to the legal entity.

1. Enable the legal entity for dual-write. Then run the [appropriate maps](../environment/resource-dual-write-maps.md) in the initial synchronization, or ensure that new data is created as required to sync master data from either system.
1. Complete the required setup in both systems. Learn more about setup and configuration in [Project Operations Integrated with ERP deployment overview](../environment/project-operations-integrated-deployment-overview.md). For the finance and operations architecture, several areas of new setup are required. For example, you must create project categories, configure parameters, and create project cost and revenue profiles.

[!include [banner](../includes/banner.md)]

[!INCLUDE[footer-include](../includes/footer-banner.md)]
