---
title: Financial dimension defaults
description: This article provides information about how to set up financial dimension defaults.
author: ryansandnessMSFT
ms.date: 03/05/2024
ms.topic: how-to
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak
ms.author: ryansandness
---

# Financial dimension defaults

[!INCLUDE[banner](../includes/banner.md)]

_**Applies To:** Project Operations for resource/non-stocked based scenarios._

This article provides information about how to set up financial dimension defaults.

Microsoft Dynamics 365 Project Operations uses the [Financial dimensions](/dynamics365/finance/general-ledger/financial-dimensions) framework in Microsoft Dynamics 365 Finance to provide more insights on project subledger and general ledger transactions.

Default financial dimensions can be set up on a customer, project funding source, milestone, project contract line, or project.

## Define default financial dimensions for a customer

Customer dimension defaults are specified in Finance. To set up default financial dimensions, follow these steps.

1. Go to **Accounts receivable** \> **Customers** \> **All customers**.
1. On the **Customers** page, on the **Financial dimensions** tab, set the financial dimension values for a specific customer.

## Define default financial dimensions for project contracts

Project contracts are created and maintained in Common Data Service (CDS). Accounting attributes for project contracts are set in the **Project management and accounting** module in Finance.

### Set financial dimensions for a project funding source

To set financial dimensions for a project funding source, follow these steps.

1. Go to **Project management and accounting** \> **Projects** \> **Project contracts**.
1. Select the record you want to update, and on the **Project contract** tab, select **Show default accounting**.
1. Expand **Related information** and select the **Funding sources** tab.
1. Set the financial dimension defaults. Notice that the financial dimensions default from the customer account.

### Set financial dimensions for a project contract line

1. Go to **Project management and accounting** \> **Projects** \> **Project contracts**.
1. Select the record you want to update and on the **Project contract** tab, select **Show default accounting**.
1. Expand **Related information** and select the **Contract lines** tab.
1. Set the financial dimension defaults. The financial dimension defaults are applicable and can be used only with Fixed price (milestone) contract lines.

These defaults are used on related project on-account transactions and invoice lines.

## Define default financial dimensions for projects

Projects are created and maintained in Dataverse. Accounting attributes for projects are set in the **Project management and accounting** module in Finance.

1. Go to **Project management and accounting** \> **Projects** \> **All projects**.
1. Select the record that you want to update and on the **Project** tab, select **Show default accounting**.
1. Expand **Related information** and select the **Setup** tab.
1. Set the financial dimension defaults. Notice that financial dimensions default from the customer account. If the project is associated with a contract line with multiple project contract customers, the primary customer is used to default financial dimensions.

Project default financial dimensions are used to set journal line defaults for time, expense, and fee transactions in the **Project Operations Integration Journal** and on related project invoice lines.

## Enable default financial dimensions for bookable resources

An employee’s financial dimensions were previously not considered in the financial entries generated from their work. New functionality is now available to map an individual worker to a bookable resource, and use that worker’s financial dimensions in the related integration journal and forecast lines and postings.

This feature has a dependency on an optional Dataverse solution and integration. The **Dynamics 365 HR Integration to URS** app must be installed as a prerequisite. For more information and installation instructions, see [Human resources to bookable resource integration](/dynamics365/human-resources/hr-admin-integration-hr-rm).

After installation and configuration, the Worker (cdm_workers) Dual-write map should be installed and have the status of running. A new field on the bookable resource is available to map workers to bookable resources. Bookable resources also need to be newly created or updated manually to link the worker to the bookable resource. 

> [!IMPORTANT]
> The **Dynamics 365 HR Integration to URS** app makes the **Worker** field editable on creation of a new bookable resource. The **Worker** field isn’t editable later.

### Set up the Use employment default dimensions on integration journals feature

The following prerequisites must be completed for the new feature to take effect for any mapped workers.

1. Enable the **Use employment default dimensions on integration journals** feature in feature management.
1. Apply solution in Dual-write for the Dynamics 365 Project Operations Dual Write Entity Maps to import one new map and two updated maps for this feature. 
1. Modify the integration key for the new bookable resources map.
   1. Select the integration key and add a bookable resource ID [Bookable Resource] in the first column next to **Bookable Resource**. 
   1. Select **Save**, and exit the integration key screen.
1. Stop the **Project Operations Integration Actuals** map and select **Table map version** to update from 1.0.14 to 10.0.17 or later. You may need to select **Refresh tables** from within the Dual-write map to see and run the new table schema. This refresh also starts the new map for Project worker resource import (bookable resources). 
1. Stop the **Project Operations integration** entity for the **Hour estimates** map, and select **Table map version** to update from 1.0.4 to 1.0.6 or later. You may need to select **Refresh tables** from within the Dual-write map to see and run the new table schema.

### Changes enabled by this feature

With these prerequisites enabled, the first thing noticed by end users is changes to the integration journal. A new field for Resource is visible in the integration journal. The Resource field displays the unique identifier and name of the resource based on the worker. 

> [!NOTE]
> The previous field Resource name is still available but displays the same value when there are two bookable resources with the same name. If any integration journal line doesn't have a Resource value populated, that indicates there isn't mapping between the worker and the bookable resource. 

The scenarios included in the feature include scenarios using Dataverse time entries and expenses for actuals and estimates. The behavior for expense reports submitted from Microsoft Dynamics 365 finance and operations apps hasn't changed in this feature. 

Dimension defaults are different for time entries and expenses. For both forecasts and actuals in time entires, the behavior is as follows:

- For Project – cost posting type dimensions merge from both worker and project, but project dimensions win if there's a conflict.
- For Project – payroll allocation posting type dimensions merge from both worker and project, but worker dimensions win if there's a conflict.

For both forecasts and actuals in expense entries, the behavior is as follows:

- For Project – cost posting type dimensions merge from both worker and project, but project dimensions win if there's a conflict.
- For ledger journal posting type dimensions merge from both worker and project, but project dimensions win if there's a conflict.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
