---
title: What's new May 2021 - Project Operations Integrated with ERP
description: This article provides information about the quality updates available in the May 2021 release of Project Operations Integrated with ERP.
author: sigitac
ms.custom:
  - evergreen
ms.date: 04/09/2024
ms.topic: whats-new
ms.reviewer: johnmichalak
ms.author: sigitac
---

# What's new May 2021 - Project Operations Integrated with ERP

_**Applies To:** Project Operations Integrated with ERP_

This article applies to the following Dynamics 365 Project Operations components and versions:

- Project Operations on Dynamics 365 Dataverse environment version 4.10.0.186
- Project management and accounting in finance and operations apps environments version 10.0.18

## Features included in this release

The following features are included in this release:

- [Scheduling modes](../project-management/scheduling-modes.md):  Project managers can define whether a project should be managed using the fixed duration, fixed work, or fixed units scheduling mode.
- [Set up mileage using mileage rate tiers](../expense/set-up-mileage.md): Update mileage rate tiers for employee expense reports.

## Project Operations dual-write maps updates

The following list shows the dual-write maps that have been modified or added in the Project Operations May 2021 release.

| Entity map | Updated version | Comments |
| --- | --- | --- |
| Project funding source (msdyn\_projectcontractsplitbillingrules) | 1.0.0.2 | Syncing project contract customer terms of payment. |
| Project invoice proposal V2 (invoices) | 1.0.0.3 | Syncing proforma invoice terms of payment. |
| Project Operations integration project vendor invoice line export entity (msdyn\_projectvendorinvoicelines) | 1.0.0.1 | Quality updates |
| Projects V2 (msdyn\_projects) | 1.0.0.2 | Quality updates |

Always run the latest version of the map in your environment and enable all related table maps as you update your Project Operations Dataverse solution and finance and operations apps solution version. Certain features and capabilities might not work correctly if the latest version of the map isn't activated. You can see the active version of the map in the  **Version**  column on the  **Dual-write**  page. To activate a new version of the map, select **Table map versions**, select the latest version, and then save the selected version. If you have customized an out-of-the-box table map, reapply the changes. For more information, see [Application lifecycle management](/dynamics365/fin-ops-core/dev-itpro/data-entities/dual-write/app-lifecycle-management).

If you encounter an issue with starting the map, follow the instructions in the [Missing table columns issue on maps](/dynamics365/fin-ops-core/dev-itpro/data-entities/dual-write/dual-write-troubleshooting-finops-upgrades#missing-table-columns-issue-on-maps) section of the Dual-Write troubleshooting guide.

## Quality updates

### Project Operations on Dataverse

| **Feature area** | **Reference number** | **Quality update** |
| --- | --- | --- |
| Billing and Pricing | 2227635 | The values in the **Unit group** and **Unit** fields default from the product in the **Material Estimates** grid. |
| Billing and Pricing | 2234127 | The **Task ID** field now correctly integrates to Dataverse project actuals when a vendor invoice is posted. |
| Billing and Pricing | 2235564 | Saving the journal line ensures that the currency displayed in the journal line entry matches the default currency to the line after saving. |
| Billing and Pricing | 2246671 | Making a transaction non-chargeable during invoicing reverses the original unbilled sales record and creates a new unbilled sales record as non-chargeable. |
| Billing and Pricing | 2264042 | Valid invoice correction must not be blocked if there is an invoice correction detail that isn't valid in the environment. |
| Billing and Pricing | 2146367 | Project invoice header dual-write mapping is extended to include payment terms. |
| Opportunity management | 2086888 | Don't add roles and categories that are deactivated before you copy a quote to chargeable roles and categories of a newly copied quote. |
| Opportunity management | 2234376 | Read-only fields are greyed out in the **Material Estimates** grid. |
| Opportunity management | 2238337 | A quote based on a contact can be saved even if it's not associated with a project pricelist. |
| Opportunity management | 2239810 | Closing a quote as lost also closes the associated project and cancels any bookings. |
| Project Planning and Tracking | 2099559 | Added additional validations for system health before the **Project tasks** grid opens. |
| Project Planning and Tracking | 2178987 | Fixed a transient error that occurs when selecting **Next Stage** on the **Project** page. |
| Resource Management | 2224817 | The functionality to extend bookings defaults to the correct booking status. |
| Time entry | 2202476 | The **Time Entry** page now uses react grid control and fixes issues such as grid misalignment. |
| Time entry | 2223377 | Time entry is hidden from the **Related** section on the **Bookable Resource** page to avoid confusion with usability. |

### Project management and accounting in Dynamics 365 Finance

| Feature area | Reference number | Quality update |
| --- | --- | --- |
| Project management and accounting | [545878](https://fix.lcs.dynamics.com/Issue/Details/?bugId=545878) | Project Operations for Resource based scenarios: Can't convert quote to won because of an integration error. |
| Project management and accounting | [546604](https://fix.lcs.dynamics.com/Issue/Details/?bugId=546604) | Project Operations: An error occurs when you try to associate a contract line to a Project ID because of the check for overlapping contract lines and transaction types. |
| Project management and accounting | [547440](https://fix.lcs.dynamics.com/Issue/Details/?bugId=547440) | **ProjCDSProjectContractEntity** sets the funding source invoice address from a different customer. |
| Travel and Expense | [480451](https://fix.lcs.dynamics.com/Issue/Details/?bugId=480451) | A posting error related to mileage setup can occur. |
| Travel and Expense | [522084](https://fix.lcs.dynamics.com/Issue/Details/?bugId=522084) | The functionality, **Split to personal** isn't working for foreign currency expense transactions. |
| Travel and Expense | [523938](https://fix.lcs.dynamics.com/Issue/Details/?bugId=523938) | Expense category drop-down values are displaying incorrect categories for delegates regardless if they are a resource. |
| Travel and Expense | [539266](https://fix.lcs.dynamics.com/Issue/Details/?bugId=539266) | You can't save an intercompany expense report because of a **Resource/Category validation** error. |
| Travel and Expense | [532610](https://fix.lcs.dynamics.com/Issue/Details/?bugId=532610) | The wrong mileage rate calculation in expense report posting has split lines. |
| Travel and Expense | [537404](https://fix.lcs.dynamics.com/Issue/Details/?bugId=537404) | You can't post an intercompany expense report when sales tax is included and the offset account type on the payment method is **Worker**. |
| Travel and Expense | [542927](https://fix.lcs.dynamics.com/Issue/Details/?bugId=542927) | Rollback **TrvRequisitionLine** data entity and the unique index are associated. |
| Travel and Expense | [543239](https://fix.lcs.dynamics.com/Issue/Details/?bugId=543239) | Expense report supports source document line creating and updating. |
| Travel and Expense | [544323](https://fix.lcs.dynamics.com/Issue/Details/?bugId=544323) | An incorrect subledger journal is shown in an intercompany scenario if the sales tax is posted to the destination legal entity. |
| Travel and Expense | [546877](https://fix.lcs.dynamics.com/Issue/Details/?bugId=546877) | Project Operations: The expense estimate isn't deleted from Finance when it's deleted from Dataverse. |
| Travel and Expense | [550575](https://fix.lcs.dynamics.com/Issue/Details/?bugId=550575) | When the expense category is a non-project category, financial dimensions that are selected on the **Expenses** page aren't copied to the expense report. |
