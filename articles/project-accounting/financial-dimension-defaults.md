---
title: Financial dimension defaults
description: This article provides information about how to set up financial dimension defaults.
author: ryansandnessMSFT
ms.date: 05/30/2024
ms.topic: how-to
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak
ms.author: ryansandness
---

# Financial dimension defaults

[!INCLUDE[banner](../includes/banner.md)]

_**Applies To:** Project Operations Integrated with ERP._

This article provides information about how to set up financial dimension defaults.

Microsoft Dynamics 365 Project Operations uses the [Financial dimensions](/dynamics365/finance/general-ledger/financial-dimensions) framework in Dynamics 365 Finance to provide more insights into project subledger and general ledger transactions.

Default financial dimensions can be set up for a customer, project funding source, project contract line, or project.

## Define default financial dimensions for a customer

Customer dimension defaults are specified in Finance. To set up default financial dimensions, follow these steps.

1. Go to **Accounts receivable** \> **Customers** \> **All customers**.
1. On the **Customers** page, on the **Financial dimensions** tab, set the financial dimension values for a specific customer.

## Define default financial dimensions for project contracts

Project contracts are created and maintained in Dataverse. Accounting attributes for project contracts are set in the **Project management and accounting** module in Finance.

### Set financial dimensions for a project funding source

To set financial dimensions for a project funding source, follow these steps.

1. Go to **Project management and accounting** \> **Projects** \> **Project contracts**.
1. Select the record that you want to update, select the **Project contract** tab, and then select **Show default accounting**.
1. Expand **Related information**, select the **Funding sources** tab, and then set the financial dimension defaults. Notice that the financial dimension defaults are taken from the customer account.

### Set financial dimensions for a project contract line

1. Go to **Project management and accounting** \> **Projects** \> **Project contracts**.
1. Select the record that you want to update, select the **Project contract** tab, and then select **Show default accounting**.
1. Expand **Related information**, select the **Contract lines** tab, and then set the financial dimension defaults. The financial dimension defaults are applicable and can be used only with Fixed price (milestone) contract lines.

These defaults are used on related project on-account transactions and invoice lines.

## Define default financial dimensions for projects

Projects are created and maintained in Dataverse. Accounting attributes for projects are set in the **Project management and accounting** module in Finance.

1. Go to **Project management and accounting** \> **Projects** \> **All projects**.
1. Select the record that you want to update, select the **Project** tab, and then select **Show default accounting**.
1. Expand **Related information**, select the **Setup** tab, and then set the financial dimension defaults. Notice that financial dimensions defaults are taken from the customer account. If the project is associated with a contract line that has multiple project contract customers, the primary customer is used to enter financial dimension defaults.

Project default financial dimensions are used to set journal line defaults for time, expense, and fee transactions in the Project Operations integration journal and on related project invoice lines.

## Enable default financial dimensions for bookable resources

Previously, an employee's financial dimensions weren't considered in the financial entries that were generated from the employee's work. However, new functionality is available to map an individual worker to a bookable resource and use that worker's employment financial dimensions in the related integration journal, forecast lines, and postings. This feature has a dependency on an optional Dataverse solution and integration. The **Dynamics 365 HR Integration to URS** app must be installed as a prerequisite. For more information and installation instructions, see [Human resources to bookable resource integration](/dynamics365/human-resources/hr-admin-integration-hr-rm).

After installation and configuration, the Worker (cdm\_workers) dual-write map should be installed and have a status of **Running**. A new field on the bookable resource is available to map workers to bookable resources. Bookable resources must also be newly created or updated manually to have workers linked to them.

> [!IMPORTANT]
> The **Dynamics 365 HR Integration to URS** app makes the **Worker** field editable when a new bookable resource is created. The **Worker** field isn't editable later.

### Set up the Use employment default dimensions on integration journals feature

The following prerequisites must be completed for the new feature to take effect for mapped workers.

1. Go to **Feature management**.
1. Enable **Use employment default dimensions on integration journals**.
1. Apply the solution in dual-write for the Project Operations dual-write entity maps to import one new map and two updated maps for this feature.
1. Modify the integration key to make bookable resources have context for the relevant legal entity.

    1. Select the integration key, and then, in the first column next to **Bookable Resource**, add **bookableresourceid \[Bookable Resource\]**.
    1. Select **Save**, and close the integration key page.

1. Stop the **Project Operations Integration Actuals** map, and then select **Table map version** to update to version 10.0.17 or later. You might have to select **Refresh tables** from within the dual-write map to see and run the new table schema. 
1. Stop the **Project Operations integration** entity for the **Hour estimates** map, and then select **Table map version** to update to version 1.0.6 or later. You might have to select **Refresh tables** from within the dual-write map to see and run the new table schema.
1. Start the new map for **Project worker resource import (bookable resources)**.

### Changes enabled by this feature

After the prerequisites are completed, users should notice changes to the integration journal. A new **Resource** field in the integration journal now shows the unique identifier and name of the resource, based on the worker.

> [!NOTE]
> The previous field, **Resource name**, is still available. However, it shows the same value when there are two bookable resources that have the same name. If no **Resource** value is set for an integration journal line, there's no mapping between the worker and the bookable resource.

Among the scenarios that the feature includes are scenarios that use Dataverse time entries and expenses for actuals and estimates. The behavior for expense reports that are submitted from finance and operations apps hasn't changed in this feature.

Dimension defaults differ for time entries and expenses. For both forecasts and actuals in time entries, the following behavior occurs:

- For the **Posting type** of **Project - cost**, dimensions are merged from both workers and projects, but project dimensions win if there's a conflict.
- For the **Posting type** of **Project - payroll allocation**, dimensions are merged from both workers and projects, but worker dimensions win if there's a conflict.

For both forecasts and actuals in expense entries, the following behavior occurs:

- For the **Posting type** of **Project - cost**, dimensions are merged from both workers and projects, but project dimensions win if there's a conflict.
- For the **Posting type** of **Ledger journal**,  dimensions are merged from both workers and projects, but project dimensions win if there's a conflict.

## Enable flexibility in determining financial dimension defaulting for resource based/non-stocked scenarios

New functionality provides more options for the entry of default financial dimensions on transactions. This feature lets you select the project or contract line to determine the default financial dimensions that are entered on transactions.

To use this functionality, you must enable the **(Preview) Enable flexibility in determining financial dimension defaulting for resource based/non-stocked scenarios** feature in Feature management.

The feature includes the following functionality:

- You can use the new **Project default dimension rules** page to define the criteria that determine whether default dimensions should be taken from the project or contract line.
- **Time** and **Material** contract lines appear in the defaulting accounting for project contracts. Therefore, users can now enter financial dimension default values for both types of contract lines.
- Logic that is added to import from staging, on-account transactions, forecasts, and revenue recognition determines whether default dimensions should be taken from the project or contract line.
- Fixes have been made to improve the reliability of saving default dimension values on the project and contract line pages.

### Dimension rules

After the feature is enabled, a new page for project default dimension rules is available at **Project management and accounting** \> **Setup** \> **Posting** \> **Project default dimension rules**.

The **Project default dimension rules** page provides several criteria for determining the scope at which the rule should apply. The last column is for the default dimension priority. It's used to determine whether default dimensions should be taken from the project or contract line.

After the feature is first enabled, or in the event of upgrades, no rules are defined. In most cases, the absence of defined rules is equivalent to the previous behavior, where default dimensions are taken from the project.

The following previous legacy rules are used if the feature isn't enabled:

- The project dimensions are used as the primary source for time entries, expense entries, fees, material usage entries, and journals that originate from Dataverse.
- The project dimensions are used as the primary source for forecast entries that originate from Dataverse.
- The project contract line dimensions are used as the primary source for on-account transactions that originate from Dataverse.
- Transactions that originate from finance and operations apps use the dimensions that are defined on the originating document. These dimensions used the project dimensions as their primary source.

If a dimension rule can't be found, the legacy behavior acts as if the feature is off.

The rules are evaluated from right to left, and a rule that is more specific to a field on the right takes precedence. For example, one rule is defined for a specific project cost and revenue profile, and another rule is added for a specific project contract. In this case, the second contract rule takes precedence over the first one.

If projects aren't connected to a contract, the legacy rules apply, and the project is used for dimensions.

### Feature considerations and limitations

As of the 10.0.40 preview release, the feature doesn't consider the following documents. Therefore, these documents will continue to use the legacy behavior.

- Expense reports that are submitted from finance and operations apps
- Purchase requests, purchase orders, and vendor invoices that are submitted from finance and operations apps

As of the 10.0.40 preview release, revenue recognition has a known limitation. Revenue recognition follows the dimensions where fee journals are enabled. In a simple fixed-price project that has a single contract line, the default dimensions can be correctly taken from the contract. However, if a time-and-material contract line for fees and a separate fixed-price contract line for revenue recognition exist, the default dimensions are taken from the time-and-material contract line that is used for fees.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
