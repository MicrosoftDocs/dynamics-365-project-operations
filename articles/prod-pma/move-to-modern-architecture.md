---
title: Moving to the modern architecture
description: Learn how to use the modern architecture and move to the resource/non-stocked deployment if you have a legal entity that is currently using the stocked/production order deployment. 
author: ryansandness 
ms.date: 03/03/2025
ms.topic: how-to
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak
ms.search.region: Global
ms.author: ryansandness
ms.search.validFrom: 2025-03-03 
ms.dyn365.ops.version: 
---
# Moving to the modern architecture

## Introduction

If you're currently using the Project Management and Accounting module for managing your projects, with  version 10.0.43 and later, it's now possible to use the modern architecture of Project Operations to take advantage of the new functionality and modern technology stack.

Many customers who had previously used the project capabilities as part of the Project Management and Accounting module in the finance and operations architecture weren't able to turn on capabilities of the modern architecture of Project Operations in the same legal entity. This option has now been enabled.

For the 10.0.43 release, the **Use the modern architecture for existing legal entities with project data** feature allows you to complete all existing transactions and close existing projects in the Project Management and Accounting module, and begin creating new projects, project-based quotes and contracts using the richer and modern experiences that bring together Dataverse and finance and operations apps capabilities for project management in an orchestrated seamless experience. Data from Dataverse is automatically integrated into the same legal entity in Finance and Operations and vice versa. Adopting the modern architecture allows you to take advantage of the new project contract structure, sales process, functionality in project planning using Microsoft Project for the Web, resource management using Unified Resource Management, transaction models, subcontracting, and proforma invoice processes without losing the value of the rich project accounting and invoicing capabilities in Finance and Operations.

## Enable the modern architecture of Project Operations

Enabling the modern architecture in a legal entity with project data requires, at a minimum, the following steps.

To Enable the modern architecture of Project Operations, follow these steps.

> [!NOTE]
> This should be done in a sandbox environment, and all project-related functions should be thoroughly tested before performing in production.

1. The **Use the modern architecture for existing legal entities with project data** feature needs to be enabled to remove the prior restriction that was in place that blocked this deployment type change.
2. All project transactions should be completed. There should be no remaining pending project transactions remaining, all invoices should be completed, revenue recognition and eliminations should be completed, and nothing should remain as an open document against a project.
3. All projects should be moved to a closed status.
4. In **Global project management and accounting parameters**, select the legal entity to opt in. As part of the process, a simple check is performed against the projects to ensure they have all been closed but do ensure that all project transactions have been completed prior to this step because projects can't be reopened once you have selected to opt into the Legal entity.
5. Enable the legal entity for **Dual write** and run the [appropriate maps](../environment/resource-dual-write-maps.md) in initial sync or ensure new data is created where necessary to sync master data from either system.
6. Perform the necessary setup in both systems. Learn more about setup and configuration in[Project Operations for resource/non-stocked based scenarios deployment overview](../environment/project-operations-integrated-deployment-overview.md). For the finance and operations architecture, there are several areas of new setup required, such as project category creation, configuring parameters, creating project cost and revenue profiles, and more.

[!include [banner](../includes/banner.md)]


[!INCLUDE[footer-include](../includes/footer-banner.md)]
