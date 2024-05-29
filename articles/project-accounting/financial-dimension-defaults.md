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

_**Applies To:** Project Operations for resource/non-stocked based scenarios._

This article provides information about how to set up financial dimension defaults.

Microsoft Dynamics 365 Project Operations uses the [Financial dimensions](/dynamics365/finance/general-ledger/financial-dimensions) framework in Dynamics 365 Finance to provide more insights into project subledger and general ledger transactions.

Default financial dimensions can be set up on a customer, project funding source, project contract line, or project.

## Define default financial dimensions for a customer

Customer dimension defaults are specified in Finance. To set up default financial dimensions, follow these steps.

1. Go to **Accounts receivable** \> **Customers** \> **All customers**.
1. On the **Customers** page, on the **Financial dimensions** tab, set the financial dimension values for a specific customer.

## Define default financial dimensions for project contracts

Project contracts are created and maintained in Dataverse. Accounting attributes for project contracts are set in the **Project management and accounting** module in Finance.

### Set financial dimensions for a project funding source

To set financial dimensions for a project funding source, follow these steps.

1. Go to **Project management and accounting** \> **Projects** \> **Project contracts**.
1. Select the record that you want to update, and then, on the **Project contract** tab, select **Show default accounting**.
1. Expand **Related information**, and then, on the **Funding sources** tab, set the financial dimension defaults. Notice that the financial dimension defaults are taken from the customer account.

### Set financial dimensions for a project contract line

1. Go to **Project management and accounting** \> **Projects** \> **Project contracts**.
1. Select the record that you want to update, and then, on the **Project contract** tab, select **Show default accounting**.
1. Expand **Related information**, and then, on the **Contract lines** tab, set the financial dimension defaults. The financial dimension defaults are applicable and can be used only with Fixed price (milestone) contract lines.

These defaults are used on related project on-account transactions and invoice lines.

## Define default financial dimensions for projects

Projects are created and maintained in Dataverse. Accounting attributes for projects are set in the **Project management and accounting** module in Finance.

1. Go to **Project management and accounting** \> **Projects** \> **All projects**.
1. Select the record that you want to update, and then, on the **Project** tab, select **Show default accounting**.
1. Expand **Related information**, and then, on the **Setup** tab, set the financial dimension defaults. Notice that financial dimensions defaults are taken from the customer account. If the project is associated with a contract line that has multiple project contract customers, the primary customer is used to enter financial dimension defaults.

Project default financial dimensions are used to set journal line defaults for time, expense, and fee transactions in the Project Operations integration journal and on related project invoice lines.

## Enable default financial dimensions for bookable resources

Previously, an employee's financial dimensions weren't considered in the financial entries that were generated from the employee's work. However, new functionality is available to map an individual worker to a bookable resource and use that worker's employment financial dimensions in the related integration journal and forecast lines and postings. This feature has a dependency on an optional Dataverse solution and integration. The Dynamics 365 HR Integration to URS app must be installed as a prerequisite. For more information and installation instructions, see [Human resources to bookable resource integration](/dynamics365/human-resources/hr-admin-integration-hr-rm).

After installation and configuration, the Worker (cdm\_workers) dual-write map should be installed and have a status of **Running**. A new field on the bookable resource is available to map workers to bookable resources. Bookable resources must also be newly created or updated manually to have workers linked to them.

> [!IMPORTANT]
> The Dynamics 365 HR Integration to URS app makes the **Worker** field editable when a new bookable resource is created. The **Worker** field isn't editable later.

### Set up the Use employment default dimensions on integration journals feature

The following prerequisites must be completed for the new feature to take effect for mapped workers.

1. Enable the **Use employment default dimensions on integration journals** feature in Feature management.
2. Apply the solution in dual-write for the Project Operations dual-write entity maps to import one new map and two updated maps for this feature.
3. Modify the integration key to make bookable resources have context for the relevant legal entity.

    a. Select integration key, and then, in the first column next to **Bookable Resource**, add **bookableresourceid [Bookable Resource]**.
    b. Select **Save**, and close the integration key page.

4. Stop the **Project Operations Integration Actuals** map, and then select **Table map version** to update to version 10.0.17 or later. You might have to select **Refresh tables** from within the dual-write map to see and run the new table schema. 
5. Stop the **Project Operations integration** entity for the **Hour estimates** map, and then select **Table map version** to update to version 1.0.6 or later. You might have to select **Refresh tables** from within the dual-write map to see and run the new table schema.
6. Start the new map for **Project worker resource import (bookable resources)**.

### Changes enabled by this feature

After the prerequisites are completed, users should notice changes to the integration journal. A new **Resource** field in the integration journal now shows the unique identifier and name of the resource, based on the worker.

> [!NOTE]
> The previous field, **Resource name**, is still available. However, it shows the same value when there are two bookable resources that have the same name. If no **Resource** value is set for an integration journal line, there's no mapping between the worker and the bookable resource.

Among the scenarios that the feature includes are scenarios that use Dataverse time entries and expenses for actuals and estimates. The behavior for expense reports that are submitted from Dynamics 365 finance and operations apps hasn't changed in this feature.

Dimension defaults differ for time entries and expenses. For both forecasts and actuals in time entries, the following behavior occurs:

- For the **Posting type** of **Project - cost**, dimensions are merged from both workers and projects, but project dimensions win if there's a conflict.
- For the **Posting type** of **Project - payroll allocation**, dimensions are merged from both workers and projects, but worker dimensions win if there's a conflict.

For both forecasts and actuals in expense entries, the following behavior occurs:

- For the **Posting type** of **Project - cost**, dimensions are merged from both workers and projects, but project dimensions win if there's a conflict.
- For the **Posting type** of **Ledger journal**,  dimensions are merged from both workers and projects, but project dimensions win if there's a conflict.

## Enable flexibility in determining financial dimension defaulting for resource based/non-stocked scenarios

New functionality is available to provide additional options in how financial dimensions are defaulted onto transactions. This feature allows for the selection of the project or contract line to determine the financial dimensions that are defaulted onto transactions.

The **(Preview) Enable flexibility in determining financial dimension defaulting for resource based/non-stocked scenarios** feature must be enabled in feature management to use this functionality.

Functionality included in the feature include:

- A new form for **Project default dimension rules** to define the criteria for determining if dimensions should default from the project or contract line.
- The addition of Time and Material contract lines appearing in the defaulting accounting for project contracts. This allows users to enter financial dimension default values for both types of contract lines now.
- Logic added to import from staging, on-account transactions, forecasts, and revenue recognition to determine if dimensions should default from the project or contract line.
- Fixes to improve the reliability of saving default dimensions values within the project and contract line forms.

### Dimension Rules

After the feature is enabled there is a new form available for Project default dimension rules. The form is accessed from **Project management and accounting** > **Setup** > > **Posting** > **Project default dimension rules**.

The **Project default dimension rules** form provides several criteria to determine at what scope the rule should apply. It also provides the last column of default dimension priority to determine if dimensions should default from the project or the contract line.

On initial enabling of feature, or in the case of upgrades there will be no rules defined. No rules defined is equivalent to the previous behavior of defaulting dimensions from the project in most cases.

Previous legacy rules without the feature enabled are as follows:

- The project dimensions are used as the primary source for time entries, expense entries, fees, material usage entries, and journals originating from Dataverse.
- The project dimensions are used as the primary source for forecast entries originating from Dataverse.
- The project contract line dimensions are used as the primary source for on-account transactions originating from Dataverse.
- Transactions originating from Finance and Operations will use the dimensions defined on the originating document. These dimensions used the project dimensions as their primary source.

If there is a situation where a dimension rule cannot be found, the legacy behavior as if the feature was off will apply.

The rules evaluate from right to left and a rule that is more specific to a field on the right will take precedence. For example if a rule is defined for a specific project cost and revenue profile and another rule is added for a specific project contract, that contract rule will take precedence over the project cost and revenue profile rule.

In the case of projects not connected to a contract, the legacy rules to use project for dimensions will apply.

### Feature considerations and limitations

As of the 10.0.40 preview release, the following documents are not considered in the feature and will continue the legacy behavior:

- Expense reports submitted from Dynamics 365 Finance and Operations.
- Purchase requests, purchase orders, and vendor invoices submitted from Finance and Operations.
As of the 10.0.40 preview release, Revenue recognition has a known limitation. Revenue recognition will follow the dimensions where fee journals are enabled. In a simple fixed price project with a single contract line the dimensions can correctly default from the contract. However if a time and material contract line for fees and a separate fixed price contract line for revenue recognition exist, then the dimensions will default from the time and material contract line used for fees.
-

[!INCLUDE[footer-include](../includes/footer-banner.md)]
