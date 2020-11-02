---
title: What's new November 2020 - Project Operations for resource/non-stocked based scenarios
description: 
author: sigitac
manager: Annbe
ms.date: 10/30/2020
ms.topic: article
ms.service: project-operations
ms.reviewer: kfend 
ms.author: sigitac
---

# What's new November 2020 - Project Operations for resource/non-stocked based scenarios

_**Applies To:** Project Operations for resource/non-stocked based scenarios_

This article applies to the following Dynamics 365 Project Operations components and versions:

- Project Operations on CDS environment version 4.4.0.79
- Project management and accounting in Dynamics 365 Finance environment version 10.0.14

## Updates to Project Operations for resource-non-stocked based scenarios

### Project Operations on CDS

| Feature area                 | Reference number | Quality update                                                                                                                                                                    |
|------------------------------|------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Opportunity management       | 2036993          | Estimate line and resource   assignment contract lines are updated on winning quotes when the quote line   type is **All tasks**.                                                 |
| Billing and pricing          | 2070392          | Project contract lines on the   invoice increase every time **Refresh invoice transactions** is selected.                                                                         |
| Project planning             | 2043336          | Unable to delete a project team   member record.                                                                                                                                  |
| Project planning             | 2046013          | Inconsistent behavior for   Estimates tag columns during load vs. on change of time-phase type.                                                                                   |
| Project planning             | 2046647          | Start and end times are off by   an hour when resource requirements are generated from project team members.                                                                      |
| Project planning             | 2053879          | (Per the upcomping CDS rollout)   PublishUnassignedAssignments breaks saving a task when the error, "The   value passed for ConditionOperator.In is empty."                       |
| Project planning             | 2055501          | Leaving the **Project Start   Date** empty causes a failure in the schedule.                                                                                                      |
| Project planning             | 2066817          | Can't create a generic resource   using the people picker on the **Tasks** tab.                                                                                                   |
| Project planning             | 2067034          | **View Details** button is not   available on the **Details of Task** page.                                                                                                       |
| Resource management          | 2046667          | Generic team members are not   deleted even after all resources are fulfilled.                                                                                                    |
| Time and quick expense entry | 2047499          | The **New** button on the Time   Entry page opens the **New Email Signature** page.                                                                                               |
| Time and quick expense entry | 2059859          | Unexpected pop-up opens when   creating an expense entry.                                                                                                                         |
| Other                        | 2044181          | (Uninstalling purchase order)   When trying to uninstall msdyn_ProjectServiceCore_Patch and msdyn Project   service core solutions, the error, "Record is unavailable"   occurs.  |

### Project management and accounting in Dynamics 365 Finance

| Feature area        | Reference number | Quality update                                                                                                                                                            |
|---------------------|------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Revenue recognition | 451662           | Project estimate percentage   complete is wrong when the contract is using a foreign currency and the work   progress percentage for complete method.                     |
| Revenue recognition | 469894           | Unable to post estimates with   the **Actual cost** completion method.                                                                                                    |
| Revenue recognition | 485439           | Elimination fails because of a   voucher imbalance error when the company currency and transaction currency   are different.                                              |
| Expense management  | 456882           | For non-admin users, the lookup   values for expense line columns such as **Project ID** and **Expense   Category** aren't showing correctly in the data connector frame. |
| Expense management  | 469300           | The line property default isn't   showing for Expense categories.                                                                                                         |
| Expense management  | 469302           | Expense integration must include   the line property from the expense report.                                                                                             |
| Invoicing           | 462499           | Can't post project invoice   proposals because of an error message that says the combination of FD wasn't   validated.                                                    |
| Invoicing           | 470614           | Can't view transactions from the   **invoice** details page.                                                                                                              |
| Invoicing           | 480070           | Invoice proposal lines can be   deleted.                                                                                                                                  |
| Project accounting  | 470293           | **Forecast** menu items aren't   visible on the **Projects** list page.                                                                                                   |
| Project accounting  | 475873           | Can't open **Project statement**   > **Transactions and forecast**.                                                                                                       |
| Project accounting  | 475879           | **Adjust accounting** isn't   enabled for invoiced project transactions.                                                                                                  |
| Project accounting  | 480962           | Accounting details aren't   included on the **ProjCDSActualsImport** table when the **Integration**   journal is posted.                                                  |
| Project accounting  | 482558           | The Project forecast entry is   doubled when you remove and then re-add a resource assignment.                                                                            |
| Project accounting  | 502019           | Selecting a Project ID link   doesn't open the CDS deep link URL.                                                                                                         |
| Project accounting  | 505458           | Can't update the start date on a   task in CDS.                                                                                                                           |
| Project accounting  | 510041           | Enabling the feature, Multiple contract lines isn't possible without CDS integration.                                                                                   |

### Regulatory updates
For information about regulatory updates for Finance and Operations apps, see [Regulatory updates](https://docs.microsoft.com/dynamics365/finance/localizations/regulatory-updates). You can also sign in to LCS and view the planned regulatory updates using the Issue search tool. Issue search lets you search by country, type of feature, and release.
