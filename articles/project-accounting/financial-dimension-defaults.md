---
title: Financial dimension defaults
description: This article provides information about how to set up financial dimension defaults.
author: ryansandness
ms.date: 06/02/2026
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

Set up default financial dimensions for a customer, project funding source, project contract line, or project.

## Define default financial dimensions for a customer

Specify customer dimension defaults in Finance. To set up default financial dimensions, follow these steps:

1. Go to **Accounts receivable** > **Customers** > **All customers**.
1. On the **Customers** page, on the **Financial dimensions** tab, set the financial dimension values for a specific customer.

## Define default financial dimensions for project contracts

Create and maintain project contracts in Dataverse. Set accounting attributes for project contracts in the **Project management and accounting** module in Finance.

### Set financial dimensions for a project funding source

To set financial dimensions for a project funding source, follow these steps:

1. Go to **Project management and accounting** > **Projects** > **Project contracts**.
1. Select the record that you want to update, select the **Project contract** tab, and then select **Show default accounting**.
1. Expand **Related information**, select the **Funding sources** tab, and then set the financial dimension defaults. The system takes the financial dimension defaults from the customer account.

### Set financial dimensions for a project contract line

1. Go to **Project management and accounting** > **Projects** > **Project contracts**.
1. Select the record that you want to update, select the **Project contract** tab, and then select **Show default accounting**.
1. Expand **Related information**, select the **Contract lines** tab, and then set the financial dimension defaults. The financial dimension defaults apply only to Fixed price (milestone) contract lines.

These defaults are used on related project on-account transactions and invoice lines.

## Define default financial dimensions for projects

Create and maintain projects in Dataverse. Set accounting attributes for projects in the **Project management and accounting** module in Finance.

1. Go to **Project management and accounting** > **Projects** > **All projects**.
1. Select the record that you want to update, select the **Project** tab, and then select **Show default accounting**.
1. Expand **Related information**, select the **Setup** tab, and then set the financial dimension defaults. The system takes the financial dimension defaults from the customer account. If the project is associated with a contract line that has multiple project contract customers, the primary customer is used to enter financial dimension defaults.

Use project default financial dimensions to set journal line defaults for time, expense, and fee transactions in the Project Operations integration journal and on related project invoice lines.

## Enable default financial dimensions for bookable resources

Previously, an employee's financial dimensions weren't considered in the financial entries that were generated from the employee's work. However, new functionality is available to map an individual worker to a bookable resource and use that worker's employment financial dimensions in the related integration journal, forecast lines, and postings. This feature has a dependency on an optional Dataverse solution and integration. You must install the **Dynamics 365 HR Integration to URS** app as a prerequisite. For more information and installation instructions, see [Human resources to bookable resource integration](/dynamics365/human-resources/hr-admin-integration-hr-rm).

After installation and configuration, install the Worker (cdm\_workers) dual-write map and ensure its status is **Running**. A new field on the bookable resource is available to map workers to bookable resources. You must also create or update bookable resources manually to link workers to them.

> [!IMPORTANT]
> The **Dynamics 365 HR Integration to URS** app makes the **Worker** field editable when you create a new bookable resource. The **Worker** field isn't editable later.

### Set up the Use employment default dimensions on integration journals feature

Complete the following prerequisites for the new feature to take effect for mapped workers.

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

After you complete the prerequisites, you see changes to the integration journal. A new **Resource** field in the integration journal now shows the unique identifier and name of the resource, based on the worker.

> [!NOTE]
> The previous field, **Resource name**, is still available. However, it shows the same value when there are two bookable resources that have the same name. If you don't set a **Resource** value for an integration journal line, there's no mapping between the worker and the bookable resource.

This feature includes scenarios that use Dataverse time entries and expenses for actuals and estimates. The behavior for expense reports that are submitted from finance and operations apps didn't change in this feature.

Dimension defaults differ for time entries and expenses. For both forecasts and actuals in time entries, the following behavior occurs:

- For the **Posting type** of **Project - cost**, dimensions are merged from both workers and projects, but project dimensions win if there's a conflict.
- For the **Posting type** of **Project - payroll allocation**, dimensions are merged from both workers and projects, but worker dimensions win if there's a conflict.

For both forecasts and actuals in expense entries, the following behavior occurs:

- For the **Posting type** of **Project - cost**, dimensions are merged from both workers and projects, but project dimensions win if there's a conflict.
- For the **Posting type** of **Ledger journal**,  dimensions are merged from both workers and projects, but project dimensions win if there's a conflict.

## Enable flexibility in determining financial dimension defaulting for resource based and nonstocked scenarios

The new functionality provides more options for entering default financial dimensions on transactions. Use this feature to select the project or contract line to determine the default financial dimensions that you enter on transactions.

To use this functionality, enable the **Enable flexibility in determining financial dimension defaulting for resource based/non-stocked scenarios** feature in Feature management. This feature is generally available with the 10.0.48 release with full support for task-based billing for documents originating within Dynamics 365 Finance and Supply Chain Management.  

This feature includes the following functionality:

- Use the new **Project default dimension rules** page to define the criteria that determine whether default dimensions come from the project or contract line.
- **Time** and **Material** contract lines appear in the defaulting accounting for project contracts. Therefore, you can now enter financial dimension default values for both types of contract lines.
- Logic that is added to import from staging, on-account transactions, forecasts, and revenue recognition determines whether default dimensions come from the project or contract line.
- Fixes that improve the reliability of saving default dimension values on the project and contract line pages.

### Dimension rules

After you enable the feature, a new page for project default dimension rules is available at **Project management and accounting** > **Setup** > **Posting** > **Project default dimension rules**.

The **Project default dimension rules** page provides several criteria for determining the scope at which the rule should apply. The last column is for the default dimension priority. It's used to determine whether default dimensions come from the project or contract line.

When you first enable the feature, or during upgrades, no rules are defined. In most cases, the absence of defined rules is equivalent to the previous behavior, where default dimensions come from the project.

If you don't enable the feature, the system uses the following legacy rules:

- The project dimensions are the primary source for time entries, expense entries, fees, material usage entries, and journals that originate from Dataverse.
- The project dimensions are the primary source for forecast entries that originate from Dataverse.
- The project contract line dimensions are the primary source for on-account transactions that originate from Dataverse.
- Transactions that originate from finance and operations apps use the dimensions that are defined on the originating document. These dimensions use the project dimensions as their primary source.

If the system can't find a dimension rule, the legacy behavior acts as if the feature is off.

The system evaluates the rules from right to left, and a rule that is more specific to a field on the right takes precedence. For example, you define one rule for a specific project cost and revenue profile, and you add another rule for a specific project contract. In this case, the second contract rule takes precedence over the first one.

If you don't connect projects to a contract, the legacy rules apply, and the project is used for dimensions.

For documents that originate in the finance and operations architecture, many significant updates were made for the 10.0.45 release.

- Purchase requisitions, purchase orders, vendor invoices, and purchase agreements support dimensions by contract line. Postings to the vendor account from the vendor invoice aren't associated with a specific contract line, so they have a blank dimension value.
- Expense reports support dimensions by contract line.
- Revenue recognition uses the default contract line number for dimensions in the estimate project. Without contract line based revenue recognition, the system follows the dimensions based on which contract line is used for fees.

### Feature considerations and limitations

Before the 10.0.48 release, the system doesn't support task-based billing as the source of dimensions for documents that originate in the finance and operations architecture. If multiple contract lines exist for a transaction type, the system uses the first contract line rather than the selected task.

Some postings don't have visibility into transaction lines, so the system continues to merge dimensions from only the document header and project. For example, purchase orders and vendor invoices don't consider individual invoice lines when posting to vendor balance.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
