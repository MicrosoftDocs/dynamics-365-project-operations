---
title: Moving to the modern architecture
description: Learn how to use the modern architecture and move to the resource/non-stocked deployment if you have a legal entity that is currently using the stocked/production order deployment.
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
# Moving to the modern architecture

## Introduction

If you're using the Project Management and Accounting module for managing your projects, with version 10.0.43 and later, you can use the modern architecture of Project Operations to take advantage of the new functionality and modern technology stack.

Many customers who previously used the project capabilities as part of the Project Management and Accounting module in the finance and operations architecture couldn't turn on the capabilities of the modern architecture of Project Operations in the same legal entity. This option is now enabled.

For the 10.0.43 release, the **Use the modern architecture for existing legal entities with project data** feature lets you complete all existing transactions and close existing projects in the Project Management and Accounting module. You can then create new projects, project-based quotes, and contracts using the richer and modern experiences that bring together Dataverse and finance and operations apps capabilities for project management in an orchestrated seamless experience. Data from Dataverse is automatically integrated into the same legal entity in Finance and Operations and vice versa. Adopting the modern architecture lets you take advantage of the new project contract structure, sales process, functionality in project planning using Microsoft Project for the Web, resource management using Unified Resource Management, transaction models, subcontracting, and proforma invoice processes without losing the value of the rich project accounting and invoicing capabilities in Finance and Operations.

## Enable the modern architecture of Project Operations

Enabling the modern architecture in a legal entity with project data requires, at a minimum, the following steps.

To Enable the modern architecture of Project Operations, follow these steps.

> [!NOTE]
> This should be done in a sandbox environment, and all project-related functions should be thoroughly tested before performing in production.

1. Enable the **Use the modern architecture for existing legal entities with project data** feature to remove the prior restriction that blocked this deployment type change.
2. Complete all project transactions. Ensure there are no pending project transactions, all invoices are completed, revenue recognition and eliminations are completed, and no open documents remain against a project.
3. Move all projects to a closed status.
4. In **Global project management and accounting parameters**, select the legal entity to opt in. Ensure all project transactions are completed before this step because projects can't be reopened once you opt into the legal entity.
5. Enable the legal entity for **Dual write** and run the [appropriate maps](../environment/resource-dual-write-maps.md) in initial sync or ensure new data is created where necessary to sync master data from either system.
6. Perform the necessary setup in both systems. Learn more about setup and configuration in[Project Operations for resource/non-stocked based scenarios deployment overview](../environment/project-operations-integrated-deployment-overview.md). For the finance and operations architecture, there are several areas of new setup required, such as project category creation, configuring parameters, creating project cost and revenue profiles, and more.

[!include [banner](../includes/banner.md)]


[!INCLUDE[footer-include](../includes/footer-banner.md)]
