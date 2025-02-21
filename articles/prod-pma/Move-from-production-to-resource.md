---
title: Moving from stocked/production-based to resource/non-stocked
description: Learn how you can use the modern architecture and move to the resource/non-stocked deployment if you have a legal entity that is currently using the stocked/production-based deployment. 
author: ryansandness 
ms.date: 02/24/2025
ms.topic: how-to
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak
ms.search.region: Global
ms.author: ryansandness
ms.search.validFrom: 2025-02-24 
ms.dyn365.ops.version: 
---
# Moving from stocked/production-based deployment to resource/non-stocked

## Introduction

With the 10.0.43 release and later, it is now possible to use the modern architecture and take advantage of all of the new capabilities and experiences in this deployment if you previously had used the Project Management and Accounting module.

Many customers had previously used some capabilities within the finance and operations architecture which prevented them from enabling the resource/non-stocked deployment in that legal entity. Customers now the ability to adopt the modern architecture where previously this wasn't possible.

The **Use the modern architecture for existing legal entities with project data** feature allows for scenarios where you can complete all existing transactions and close existing projects, and then create new projects and contracts in Dataverse within that same legal entity. By adopting the modern architecture, users benefit from great user experiences, deep functionality in project planning using Microsoft Project for the Web, and resource management using Unified Resource Management.

## Changing deployment types

Changing to a resource/non-stocked deployment will require at a minimum the following steps. This should be done in a sandbox and all project-related functions should be thoroughly tested before performing in production.

1. The **Use the modern architecture for existing legal entities with project data** feature needs to be enabled to remove the prior restriction that was in place that blocked this deployment type change.
2. All project transactions should be completed. There should be no remaining pending project transactions remaining, all invoices should be completed, revenue recognition and eliminations should be completed, and nothing should remain as an open document against a project.
3. All projects should be moved to a closed status. 
4. In **Global project management and accounting parameters**, select the legal entity to opt in. As part of the process, a simple check will be performed against the projects to ensure they have all been closed, but do ensure that all project transactions have been completed prior to this step as projects will not be able to be re-opened.
5. Enable the legal entity for **Dual write** and run the appropriate maps in initial sync or ensure new data is created where necessary to sync master data from either system.
6. Perform the necessary setup in both systems. For the finance and operations architecture, there will be several areas of new setup required such as project category creation, configuring parameters, creating project cost and revenue profiles, and more.

In the future, we plan to expand functionality to allow for limited transaction entry against long running projects and allow for continued project work on existing projects in a limited fashion including invoicing and revenue recognition.


[!include [banner](../includes/banner.md)]


[!INCLUDE[footer-include](../includes/footer-banner.md)]
