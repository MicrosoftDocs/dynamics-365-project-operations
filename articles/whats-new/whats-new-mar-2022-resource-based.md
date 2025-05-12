---
title: What's new March 2022 - Project Operations for resource/non-stocked based scenarios
description: This article provides information about the quality updates that are available in the March 2022 release of Project Operations for resource/non-stocked based scenarios.
author: sigitac
ms.custom:
  - evergreen
ms.date: 04/09/2024
ms.topic: whats-new
ms.reviewer: johnmichalak
ms.author: sigitac
---

# What's new March 2022 - Project Operations for resource/non-stocked based scenarios

*Applies To: Project Operations for resource/non-stocked based scenarios*

This article applies to the following components and versions of Microsoft Dynamics 365 Project Operations:

- Project Operations in a Dataverse environment version 4.30.0.99
- Project management and accounting in a Dynamics 365 Finance environment version 10.0.25

## Features included in this release

Per diems are now supported in the new and reimagined modern expense workspace. Companies that use per diems can enable this feature to give users an easy way to submit and be reimbursed for their per diem expenses. For more information, see [Per diem expenses](../expense/per-diem-expenses.md).

## Project Operations dual-write maps updates

The following list shows the dual-write maps that have been modified or added in the Project Operations March 2022 release.

| **Entity map** | **Updated version** | **Comments** |
| --- | --- | --- |
| Project Operations integration project vendor invoice line export entity msdyn\_projectvendorinvoicelines | 1.0.0.3 | Mappings updated to align with vendor invoice line entity in Dataverse. <br>Don't activate mapping version 1.0.0.4. It will be ready to use in combination with Finance environment version 10.0.26 in the next monthly update. |

Always run the latest version of the map in your environment, and enable all related table maps as you update your Project Operations Dataverse solution and Finance solution version. Some features and capabilities might not work correctly if the latest version of the map isn't activated. You can view the active version of the map in the **Version** column on the **Dual-write** page. To activate a new version of the map, select **Table map versions**, select the latest version, and then save the selected version. If you've customized an out-of-box table map, reapply the changes. For more information, see [Application lifecycle management](/dynamics365/fin-ops-core/dev-itpro/data-entities/dual-write/app-lifecycle-management).

If you encounter an issue when you start the map, follow the instructions in the [Missing table columns issue on maps](/dynamics365/fin-ops-core/dev-itpro/data-entities/dual-write/dual-write-troubleshooting-finops-upgrades#missing-table-columns-issue-on-maps) section of the Dual-write troubleshooting guide.

## Quality updates

### Project Operations on Dataverse

| Feature area | Reference number | Quality update |
| --- | --- | --- |
| Time and expense | 2388011 | Show rejection comments to time entry submitters during bulk approval. |
| Project planning and tracking | 2495294 | Project details must not be editable on the **Task details** page. |
| Billing and pricing | 2499605 | Contract milestones that are created from quotation milestones are incorrectly marked as read-only. |
| Project planning and tracking | 2506050 | The operation set stays pending for one hour if there is no change to save. The set is then falsely marked as **Failed**, whereas it should be completed immediately. |
| Billing and pricing | 2507401 | Default contracting units are incorrectly entered on projects because of incorrect caching. |
| Billing and pricing | 2541660 | **Sales Order Creation Validation** in dual-write should be for project-based orders only. |
| Billing and pricing | 2552745 | Tax isn't split between customers who have set up split billing rules. |
| Billing and pricing | 2558859 | Improved error messages when pricing dimensions are set up. |
| Billing and pricing | 2558933 | **Import from Project Estimates** fails when **msdyn\_project** is added as a pricing dimension. |
| Billing and pricing | 2559101 | Project parameter deletion isn't blocked and causes issues. |
| Opportunity management | 2570390 | The dual-write plug-in forces the account type on quotations, orders, and opportunities to be **Customer**, even when that account type isn't correct. |
| Billing and pricing | 2586097 | Split billed cost actuals aren't reversed when a project is removed from a project contract line. |
| Billing and pricing | 2589619 | Tax on write-in material is propagated to unbilled sales actuals and the invoice. |
| Opportunity management | 2594015 | A quotation can't be closed as won for customers who have **Net60** payment terms. |
| Project planning and tracking | 2595841 | In Project for the Web, users receive an error message about a missing **msdyn\_actualstart** when they create a new resource request. |
| Time and Expense | 2602511 | The **Rejected by** field for time entries shows **System** instead of a named user as the rejector. |
| Time and Expense | 2602528 | A project approver can approve time on projects where they aren't listed as an approver. |
| Billing and pricing | 2608550 | A correction invoice can be confirmed even if there are no changes to the original. |

### Project management and accounting on Dynamics 365 Finance

| Feature area | Reference number | Quality update |
| --- | --- | --- |
| Project management and accounting | [606759](https://fix.lcs.dynamics.com/Issue/Details/?bugId=606759) | There is a mismatch between Finance and Project Operations in the allowed length of the **Category ID** field. |
| Project management and accounting | [617806](https://fix.lcs.dynamics.com/Issue/Details/?bugId=617806) | Fixed price projects can't be eliminated when the **On account invoicing** field is set to **Profit and Loss** and the **Completed percentage** principle is used. |
| Project management and accounting | [620979](https://fix.lcs.dynamics.com/Issue/Details/?bugId=620979) | An incorrect default sales tax group is entered from the project setup on expense lines in the Project Operations integration journal. |
| Project management and accounting | [623014](https://fix.lcs.dynamics.com/Issue/Details/?bugId=623014) | You can't edit the project invoice proposal header dimensions in an integrated deployment with Project Operations. |
| Project management and accounting | [624283](https://fix.lcs.dynamics.com/Issue/Details/?bugId=624283) | Intercompany vendor invoices must not be integrated with Dataverse. |
| Project management and accounting | [634156](https://fix.lcs.dynamics.com/Issue/Details/?bugId=634156) | There is a mismatch in the customer balances currency and the reporting currency. |
| Project management and accounting | [641612](https://fix.lcs.dynamics.com/Issue/Details/?bugId=641612) | You can post a project invoice even if the customer is on hold for all invoices. |
| Project management and accounting | [642945](https://fix.lcs.dynamics.com/Issue/Details/?bugId=642945) | The **Delete all lines** button is missing from project invoice proposals that have the **Header** and **Lines** views. |
| Project management and accounting | [637760](https://fix.lcs.dynamics.com/Issue/Details/?bugId=637760) | When you post a vendor invoice, the following error occurs: "The accounting date for the invoice must be in the same accounting year as the related purchased order. Run the purchase order year-end process or change the date to the current accounting year." |
| Travel and Expense | [604128](https://fix.lcs.dynamics.com/Issue/Details/?bugId=604128) | The committed cost for a project isn't released after the travel requisition's committed cost is released. |
| Travel and Expense | [620803](https://fix.lcs.dynamics.com/Issue/Details/?bugId=620803) | The following error occurs when you submit an expense report: "Stack Trace: The company does not exist." |
| Travel and Expense | [622465](https://fix.lcs.dynamics.com/Issue/Details/?bugId=622465) | The default **Project ID** isn't entered on expense reports when the **Require activity for journal** parameter is selected on the project. |
| Travel and Expense | [626781](https://fix.lcs.dynamics.com/Issue/Details/?bugId=626781) | The **Post Expenses** button doesn't work correctly in Project Operations for resource/non-stocked scenarios. |
| Travel and Expense | [635348](https://fix.lcs.dynamics.com/Issue/Details/?bugId=635348) | There is an issue with **Rate per mile** for a mileage expense report that includes passengers. |
| Travel and Expense | [638019](https://fix.lcs.dynamics.com/Issue/Details/?bugId=638019) | Expense mileage rates for employees aren't correctly totaled when two different vehicle types are used in the **Mileage rate tiers** expense category. |
| Travel and Expense | [641272](https://fix.lcs.dynamics.com/Issue/Details/?bugId=641272) | The lookup for the **Project** field on a travel requisition line doesn't return the correct list of projects. |
| Travel and Expense | [645905](https://fix.lcs.dynamics.com/Issue/Details/?bugId=645905) | **Mileage in review** shows a warning on expense reports. |
| Travel and Expense | [647819](https://fix.lcs.dynamics.com/Issue/Details/?bugId=647819) | The receipt optical character recognition (OCR) service doesn't work because of an issue with the URL of the expense OCR service. |
| Travel and Expense | [648684](https://fix.lcs.dynamics.com/Issue/Details/?bugId=648684) | When the **Ability to itemize recurring expenses quickly** feature is enabled, the amounts on itemization lines on expense reports change amounts every time that the **Itemize** page is opened. |
| Travel and Expense | [651899](https://fix.lcs.dynamics.com/Issue/Details/?bugId=651899) | You can't delete an expense report when the interim list has more than one approver. |

## Removed and deprecated features

The [Removed or deprecated features in Project Operations](removed-depreciated-features-project.md) article describes features that have been removed or deprecated for Dynamics 365 Project Operations.

- A removed feature is no longer available in the product.
- A deprecated feature isn't in active development and might be removed in a future update.

A deprecation announcement will be appear in the [Removed or deprecated features in Project Operations](removed-depreciated-features-project.md) article 12 months before any feature is removed from the product.

For breaking changes that only affect compilation time, but are binary compatible with sandbox and production environments, the deprecation time will be less than 12 months. Typically, these changes are functional updates that must be made to the compiler.
