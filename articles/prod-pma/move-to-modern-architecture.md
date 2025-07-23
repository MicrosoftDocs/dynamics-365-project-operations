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

As of version 10.0.43, if you use the **Project management and accounting** (PMA) module to manage your projects, you can use the modern architecture of Microsoft Dynamics 365 Project Operations to take advantage of the new functionality and modern technology stack.

Many customers who previously used the project capabilities of the **Project management and accounting** module in the finance and operations architecture could not turn on the capabilities of the modern architecture of Project Operations in the same legal entity. This option is now available.

In the 10.0.43 release, the **Use the modern architecture for existing legal entities with project data** feature lets you complete all existing transactions and close existing projects in the **Project management and accounting** module. Functionality is further enhanced in the 10.0.45 release, where a subset of transactions and processes are available to allow users to continue to create and post transactions, invoice, and perform revenue recogntion, and close the project as they complete.You can then create new projects, project-based quotes, and contracts by using richer, modern experiences that bring together the project management capabilities of Dataverse and finance and operations apps into one orchestrated, seamless experience. Data from Dataverse is automatically integrated into the same legal entity in finance and operations apps. Likewise, data from finance and operations apps is automatically integrated into Dataverse.

By adopting the modern architecture, you can take advantage of the following features without losing the benefit of the rich project accounting and invoicing capabilities of finance and operations apps:

- Project contract structure
- Sales process
- Project planning functionality that uses Microsoft Project for the web
- Resource management that uses Unified resource management
- Transaction models
- Subcontracting
- Proforma invoice processes

## Enable the modern architecture of Project Operations (10.0.45 and later)

Here is a summary of functionality available. These changes are all additive. No changes are made if the legal entity isn't opted in to become an integrated company. If you don't see a document or a process is available in this list, then it is not available in the user interface and is not enabled. Any documents or processes not available should be in a state where they are finalized before enabling the feature in production.

| Functionality                  | Area                | Availibility | Release Version |
|-------------------------------|---------------------|--------------|-----------------|
| Projects         | Project Setup  | Limited     | 10.0.45         |
| Project contracts         | Project Setup  | Limited     | 10.0.45         |
| Pricing Setup                | Project Setup  | Partial*     | 10.0.45         |
| Project Resources            | Project Setup       | In Dataverse*    | 10.0.45         |
| Project Parameters           | Project Setup       | Complete     | 10.0.45         |
| Project Stage Rules          | Project Setup       | Complete     | 10.0.45         |
| F&O Expense Reports          | Expense management  | Complete     | 10.0.45         |
| F&O Journals (Hour, Expense, Item, Fee)     | Project Financials  | Complete     | 10.0.45        |
| On-Account transactions                    | Project Financials   | Complete     | 10.0.45         |
| Invoicing & credit notes     | Project Financials  | Complete     | 10.0.45         |
| Invoicing Billing Rules      | Project Financials  | Limited*     | 10.0.45         |
| Post invoices                | Project Financials  | Complete     | 10.0.45         |
| Multiple funding sources invoicing | Project Financials | Partial* | 10.0.45         |
| Revenue Recognition          | Project Financials  | Complete     | 10.0.45         |

---

**Footnotes:**

- *Multiple funding sources invoicing*: Multiple funding sources can be invoiced, but no changes to funding sources, funding limits, allocations, etc.
- *Revenue Recognition*: UI is not at 100% parity, but it is possible to complete for a PMA project.
- *Invoicing Billing Rules*: Can be done for transactions marked with a unit or milestone to invoice. The contract is read-only, so no future amounts can be invoiced as of this release.

---

**Detailed changes by area:**

| Functionality                  | Details                                             |
|------------------------------|-----------------------------------------------------|
| Projects                     | The Project list page shows both integrated and PMA projects together in a single list. Behavior will differ on what items in the ribbon show based on the type of project. PMA projects can be opened to see the details page, but they don't allow for editing of details. |
| Project contracts            | The Project contracts list page shows both integrated and PMA contracts together in a single list. Behavior will differ on what items in the ribbon show based on the type of project. PMA project contracts can be opened to see the details page, but they don't allow for editing of details. |
| Pricing setup                | Pricing for hours, expenses, or fees can be configured from the ribbon when in the context of a project or contract. Transfer prices is also enabled in the ribbon, but is read-only. |
| Project resources            | The resources list page is not enabled. New resources can be configured using the HR to URS Dataverse feature. New resources can be created linking the employee record to the bookable resource in Dataverse. A transaction for the bookable resource to an integrated project such as a zero cost journal that is posted through the integration journal is required for the resource to be created on the finance and operations architecture.|
| Project parameters           | Project parameters are no longer reset on opting-in a legal entity. All PMA parameters are enabled and editable, but all parameters may not be compatable with integrated projects. Once all PMA projects are closed then the PMA parameters will be hidden in the UI since they are no longer applicable. |
| Project Stage Rules          | Project stage rules are available in the list page and details page. PMA Projects can change stages and move to closed. |
| F&O Expense Reports          | Expense reports functionality is available for both PMA and integrated projects. |
| F&O Journals (Hour, Expense, Item, Fee)     | Journals are available in the list or details page for PMA projects in the ribbon . Journal setup doesn't have a menu, but is available for a read-only view through the journal name hyperlink. |
| On-Account transactions      | On-Account transactions (milestones, advances, retainers) are available for both PMA and integrated projects. |
| Invoicing & credit notes     | Project invoice proposals can be created from the project or contract list page or details page for PMA projects. |
| Invoicing Billing Rules      | Project invoice proposals can be created from the project or contract list page or details page for PMA projects. The contract is read-only, so new milestones, progress, or units of deliveries can be enabled for invoicing. |
| Post invoices                | The existing post invoices button will work for both PMA and integrated projects. |
| Multiple funding sources invoicing | PMA projects support posting invoices for multiple funding sources, but no changes can be made to the contract for funding limits, rules, or allocations. |
| Revenue Recognition          | Revenue recognition is available for both PMA and integrated projects.  |

- General Journals are no longer available but can be re-enabled with the `xyz` feature.

At a minimum, you must follow these steps to enable the modern architecture in a legal entity that has project data. This example will follow the USSI demo data company.

> [!IMPORTANT]
> Before you complete this procedure in a production environment, you should complete it in a sandbox environment and thoroughly test all project-related functionality.

1. Turn on the **Use the modern architecture for existing legal entities with project data** feature to remove the restriction that blocks this change in the deployment type.
2. Complete all project transactions that aren't in the list of supported transactions above. Examples of unsupported transactions may include timesheets, subscription billing, and more.
3. Complete all processes that aren't in the list of processes above. Examples of unsupported processes may include post costs, accrue revenue, adjustments, and more.
4. Close any projects that are completed.
6. On the **Global project management and accounting parameters** page, select the legal entity to opt in to.

    > [!IMPORTANT]
    > Ensure that all project transactions are completed before you complete this step, because projects can't be reopened after you opt in to the legal entity.

5. In **Data management**, navigate to **Dual write** and add the legal entity.
6. Then run the [appropriate maps](../environment/resource-dual-write-maps.md) in the initial synchronization, or ensure that new data is created as required to sync master data from either system.
1. Complete the required setup in both systems. Learn more about setup and configuration in [Project Operations Integrated with ERP deployment overview](../environment/project-operations-integrated-deployment-overview.md). For the finance and operations architecture, several areas of new setup are required. For example, you must create project categories, configure parameters, and create project cost and revenue profiles.




## Enable the modern architecture of Project Operations (prior to 10.0.45)

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
