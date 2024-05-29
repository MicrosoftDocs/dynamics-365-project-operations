---
title: Financial dimension defaults
description: This article provides information about how to set up financial dimension defaults.
author: ryansandness
ms.date: 05/30/2024
ms.topic: article
ms.reviewer: johnmichalak
ms.author: ryansandness
---

# Financial dimension defaults

_**Applies To:** Project Operations for resource/non-stocked based scenarios_

Dynamics 365 Project Operations uses the [Financial dimensions](/dynamics365/finance/general-ledger/financial-dimensions) framework in Dynamics 365 Finance to provide additional insights on project subledger and general ledger transactions.

Default financial dimensions can be set on a customer, project funding source, project contract line, or project.

## Define default financial dimensions for a customer

Customer dimension defaults are specified in Finance. Complete the following steps to set dimension defaults.

1. Go to **Accounts receivable** > **Customers** > **All customers**.
2. On the **Customers** page, on the **Financial dimensions** tab, set the financial dimension values for specific customer.

## Define default financial dimensions for project contracts

Project contracts are created and maintained in Dataverse. Accounting attributes for project contracts are set in the **Project management and accounting** module in Finance.

### Set financial dimensions for a project funding source

1. Go to **Project management and accounting** > **Projects** > **Project contracts**.
2. Select the record you want to update, and on the **Project contract** tab, select **Show default accounting**.
3. Expand **Related information** and select the **Funding sources** tab.
4. Set the financial dimension defaults. Notice that the financial dimensions default from the customer account.

### Set financial dimensions for a project contract line

1. Go to **Project management and accounting** > **Projects** > **Project contracts**.
2. Select the record you want to update and on the **Project contract** tab, select **Show default accounting**.
3. Expand **Related information** and select the **Contract lines** tab.
4. Set the financial dimension defaults. The financial dimension defaults are applicable and can be used only with Fixed price (milestone) contract lines.

These defaults are used on related project on-account transactions and invoice lines.

## Define default financial dimensions for projects

Projects are created and maintained in Dataverse. Accounting attributes for projects are set in the **Project management and accounting** module in Finance.

1. Go to **Project management and accounting** > **Projects** > **All projects**.
2. Select the record that you want to update and on the **Project** tab, select **Show default accounting**.
3. Expand **Related information** and select the **Setup** tab.
4. Set the financial dimension defaults. Notice that financial dimensions default from the customer account. If the project is associated with a contract line with multiple project contract customers, the primary customer is used to default financial dimensions.

Project default financial dimensions are used to set journal line defaults for time, expense, and fee transactions in the **Project Operations Integration Journal** and on related project invoice lines.

## Enable default financial dimensions for bookable resources

An employee’s financial dimensions were previously not considered in the financial entries generated from their work for time or expense transactions. New functionality is now available to map an individual worker to a bookable resource and use that worker’s financial dimensions in the related integration journal and forecast lines and postings.

This feature has a dependency on an optional Dataverse solution and integration. The Dynamics 365 HR Integration to URS app must be installed as a prerequisite. Setup installations are available here - <https://learn.microsoft.com/dynamics365/human-resources/hr-admin-integration-hr-rm>. 

After installation and configuration, the Worker (cdm_workers) dual write map should be installed and have status running. A new field on the bookable resource will now be available to map workers to bookable resources.
Bookable resources will also need to be newly created or updated manually to link the worker to the bookable resource. Note: The Dynamics 365 HR Integration to URS app makes the Worker field editable on creation of a new bookable resource and the field isn’t editable later.

### Setup of the Use employment default dimensions on integration journals feature

Prerequisites must be completed for the new feature to take effect for any mapped workers.

1. The first required step is to enable the **Use employment default dimensions on integration journals** feature in feature management.
2. The second required step is to apply solution in Dual Write for the Dynamics 365 Project Operations Dual Write Entity Maps. This will import one new map and two updated maps for this feature.
3. With the prerequisites features installed we need to modify the integration key to make **Bookable Resource** have context for the relevant legal entity. Click into integration key and add "bookable resourceid [Bookable Resource] in the first column next to **Bookable Resource**. Click Save and exit the integration key screen.
4. Next, stop the Project Operations Integration Actuals map and click Table map version to update from 1.0.14 to 10.0.17 or later. You may need to also click refresh tables from within the dual write map to see the new table schema, and then run.
5. Next, stop the Project Operations integration entity for hour estimates map and click Table map version to update from 1.0.4 to 1.0.6 or later. You may need to also click refresh tables form within the dual write map to see the new table schema, and then run.
6. Finally, start the new map for Project worker resource import (bookableresources) if it has not yet been started from the related maps starting.

### Changes enabled by this feature

With these prerequisites enabled the first thing noticed by end users will be changes to the integration journal. A new field for Resource will now be visible in the integration journal. The Resource field will display the unique identifier and name of the resource based on the worker. Note the previous field Resource name is still available but will display the same value in the case of two bookable resources with the same name. If any integration journal line does not have a Resource value populated, that will indicate there is no mapping between the worker and the bookable resource.

The scenarios included in the feature include scenarios using Dataverse time entries and expenses for actuals and estimates. Expense reports submitted from Dynamics 365 Finance and Operations behavior is not changed in this feature.

Dimension defaults are different for time entries and expenses. For both forecasts and actuals in time entires, the behavior is as follows:

- For Project – cost posting type dimensions merge from both worker and project, but project dimensions win in case of conflict.
- For Project – payroll allocation posting type dimensions merge from both worker and project, but worker dimensions win in case of conflict.

For both forecasts and actuals in expense entries, the behavior is as follows:

- For Project – cost posting type dimensions merge from both worker and project, but project dimensions win in case of conflict.
- For ledger journal posting type dimensions merge from both worker and project, but project dimensions win in case of conflict.

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

As of the 10.0.40 preview release, Revenue recognition has a known limitation. Revenue recognition will follow the dimensions where fee journals are enabled. In a simple fixed price project with a single contract line dimensions can correctly default from the contract. However if a more complicated scenario is used with a time and material contract line for fees, the dimensions will default from the time and material line used for fees currently.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
