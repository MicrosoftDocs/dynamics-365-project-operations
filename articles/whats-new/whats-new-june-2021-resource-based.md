---
title: What's new June 2021 - Project Operations for resource/non-stocked based scenarios
description: This article provides information about the quality updates available in the June 2021 release of Project Operations for resource/non-stocked based scenarios.
author: sigitac
ms.custom:
  - evergreen
ms.date: 04/09/2024
ms.topic: whats-new
ms.reviewer: johnmichalak
ms.author: sigitac
---

# What's new June 2021 - Project Operations for resource/non-stocked based scenarios

_**Applies To:** Project Operations for resource/non-stocked based scenarios_

This article applies to the following Dynamics 365 Project Operations components and versions:

- Project Operations on Dynamics 365 Dataverse environment version 4.11.0.156 or 4.11.0.164.
- Project management and accounting in finance and operations apps environments version 10.0.19.

## Features included in this release

The following features are included in this release:

- Ability to delete [Project invoice proposal lines for adjustment scenarios](../invoicing/correct-project-invoice-proposals.md).
- Itemized expense lines reflect subcategory names in the expense report [Expense Reports Reimagined-New Features](../expense/expense-reports-reimagined.md#features-available-when-enabling-the-expense-reports-reimagined-feature).
- Payment method is available in the new expense pane when creating a new expense.
- General availability of Project schedule APIs. This new functionality allows customers to programatically perform create, update, and delete operations on project tasks, resource assignments, task dependencies, and project team member records. For more information, see [Use Project schedule APIs to perform operations with Scheduling entities](../project-management/schedule-api-preview.md).

## Project Operations dual-write maps updates

There are no updates for Project Operations dual-write maps in this release. 

For a current list and versions of Project Operations dual-write maps, see [Project Operations dual-write map versions](../environment/resource-dual-write-maps.md).

Always run the latest version of the map in your environment and enable all related table maps as you update your Project Operations Dataverse solution and finance and operations apps solution version. Certain features and capabilities might not work correctly if the latest version of the map isn't activated. You can see the active version of the map on the **Dual-write** page in the **Version** column. Activate a new version of the map by selecting **Table map versions**, selecting the latest version, and then saving the selected version. If you have customized an out-of-the-box table map, reapply the changes. For more information, see [Application lifecycle management](/dynamics365/fin-ops-core/dev-itpro/data-entities/dual-write/app-lifecycle-management).

If you encounter an issue starting the map, follow the instructions in the [Missing table columns issue on maps](/dynamics365/fin-ops-core/dev-itpro/data-entities/dual-write/dual-write-troubleshooting-finops-upgrades#missing-table-columns-issue-on-maps) section of the Dual-write troubleshooting guide.

## Quality updates

### Project Operations on Dataverse

| **Feature area** | **Reference number** | **Quality update** |
| --- | --- | --- |
| Billing and Pricing | 2281417 | Fixed the issue regarding the failure of the automatic invoice creation action through the invoice schedule. |
| Billing and Pricing | 2287835 | Improved invoice confirmation performance. |
| Opportunity Management | 2222555 | Material estimates chargeability must be correctly copied to quote line details when using **Import from Project Estimation**. |
| Opportunity Management | 2223427 | Customizations are now allowed for the action, **GenerateRetainersFromRetainerScheduleOptions**. |
| Opportunity Management | 2277528 | Fixed billing milestone value calculation for project contract lines with multiple customers. |
| Project Planning and Tracking | 2226110 | Fixed the intermittent issue with the **Generate Requirement** function in the **Project team** grid. |
| Project Planning and Tracking | 2208109 | Users can't create a project in one currency with related tasks in another currency. |
| Project Planning and Tracking | 2258228 | The list of fields allowed to modify with **Scheduling** entities using the Schedule API has been updated. |
| Project Planning and Tracking | 2293989 | The correct language and regional settings must be passed to the **Project Tasks** grid. |
| Resource Management | 2220493 | Fixed the user experience in the **Task** grid when quickly marking a resource request as complete. |
| Resource Management | 2330496 | Fixed the **Schedule Board** loading issue. (Quality update is available in version 4.11.0.164) |
| Time and Expense | 2194431 | The **Time entry** grid must honor the start of the week as set in the **System settings**. |
| Time and Expense | 2277311 | After you delete the value in a cell in the **Time entry** grid, the cursor remains in the grid. |

### Project management and accounting on Dynamics 365 Finance

| Feature area | Reference number | Quality update |
| --- | --- | --- |
| Project management and accounting | [552976](https://fix.lcs.dynamics.com/Issue/Details/?bugId=552976) | **Form notes** and **Form setup** isn't visible under **Project management setup** in Finance legal entities that are integrated with Project Operations. |
| Project management and accounting | [527970](https://fix.lcs.dynamics.com/Issue/Details/?bugId=527970) | The default description for VAT is blank when the **Posting type** = **Sales tax** for project invoice vouchers. |
| Project management and accounting | [565089](https://fix.lcs.dynamics.com/Issue/Details/?bugId=565089) | Double transactions are posted when task-based billing is used in Dataverse with Project Operations integration. |
| Project management and accounting | [566869](https://fix.lcs.dynamics.com/Issue/Details/?bugId=566869) | The percentage complete in revenue recognition is incorrect while using Project Operations integration. |
| Project management and accounting | [568107](https://fix.lcs.dynamics.com/Issue/Details/?bugId=568107) | Revenue accrual is doubled on a pending vendor invoice in a Project Operations integrated scenario. |
| Project management and accounting | [572370](https://fix.lcs.dynamics.com/Issue/Details/?bugId=572370) | Unable to post the integration journal when the revenue profile rule is set to **Group** setup. |
| Project management and accounting | [573596](https://fix.lcs.dynamics.com/Issue/Details/?bugId=573596) | A purchase invoice can't be posted for project purchase orders that have lines with multiple units of measure. |
| Project management and accounting | [573637](https://fix.lcs.dynamics.com/Issue/Details/?bugId=573637) | The default financial dimension on a project can't be updated using the projects **V2** data entity. |
| Project management and accounting | [577211](https://fix.lcs.dynamics.com/Issue/Details/?bugId=577211) | The batch process to create project estimates takes too long to complete. |
| Project management and accounting | [582329](https://fix.lcs.dynamics.com/Issue/Details/?bugId=582329) | Deleting a contract also deletes the address associated with the customer. |
| Travel and expense | [514930](https://fix.lcs.dynamics.com/Issue/Details/?bugId=514930) | The expense report approval workflow condition isn't evaluated correctly. |
| Travel and expense | [519304](https://fix.lcs.dynamics.com/Issue/Details/?bugId=519304) | The expense report policy isn't correctly evaluating the project ID. |
| Travel and expense | [522463](https://fix.lcs.dynamics.com/Issue/Details/?bugId=522463) | The action, **Split to personal for intercompany expense transactions** isn't working correctly. |
| Travel and expense | [534702](https://fix.lcs.dynamics.com/Issue/Details/?bugId=534702) | Expense report line justifications are accidentally deleted when certain travel requisitions are deleted. This occurs when the recID of the expense report and the travel requisition are the same. |
| Travel and expense | [544368](https://fix.lcs.dynamics.com/Issue/Details/?bugId=544368) | There is an issue in the Expense mobile app when the **Project ID** field is required in expense report policies. |
| Travel and expense | [545331](https://fix.lcs.dynamics.com/Issue/Details/?bugId=545331) | Intercompany expenses that are associated with a project can't be edited. Instead, the following error message displays, "Object reference not set to an instance of an object." |
| Travel and expense | [548659](https://fix.lcs.dynamics.com/Issue/Details/?bugId=548659) | After the expense report is posted, the wrong currency and amount is listed in the bank subledger. |
| Travel and expense | [558336](https://fix.lcs.dynamics.com/Issue/Details/?bugId=558336) | Improvements have been made to the *Delete credit card transactions* feature.  |
| Travel and expense | [525070](https://fix.lcs.dynamics.com/Issue/Details/?bugId=525070) | Sales tax included in an expense report isn't consistently calculated when a different reporting currency is specified in a legal entity. |
| Travel and expense | [527779](https://fix.lcs.dynamics.com/Issue/Details/?bugId=527779) | Performance is impacted when adding a new cash travel expense. |
| Travel and expense | [537841](https://fix.lcs.dynamics.com/Issue/Details/?bugId=537841) | Expense policy rules aren't triggered on an expense report. |
| Travel and expense | [566386](https://fix.lcs.dynamics.com/Issue/Details/?bugId=566386) | Uploading a new shared category by using the Data Management Framework removes all subcategories for all shared categories. |
| Travel and expense | [574131](https://fix.lcs.dynamics.com/Issue/Details/?bugId=574131) | When you create an expense line and then select a category, the following error message displays, "The combination of Sales tax group DOM and item sales tax group STD is not valid." |
| Travel and expense | [574900](https://fix.lcs.dynamics.com/Issue/Details/?bugId=574900) | There are synchronization issues in the Expense mobile application. |
