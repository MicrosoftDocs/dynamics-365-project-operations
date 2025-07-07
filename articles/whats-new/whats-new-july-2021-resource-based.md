---
title: What's new July 2021 - Project Operations Integrated with ERP
description: This article provides information about the quality updates available in the July 2021 release of Project Operations Integrated with ERP.
author: sigitac
ms.custom:
  - evergreen
ms.date: 07/07/2025
ms.topic: whats-new
ms.reviewer: johnmichalak
ms.author: sigitac
---

# What's new July 2021 - Project Operations Integrated with ERP

*Applies To: Project Operations Integrated with ERP*

This article applies to the following Dynamics 365 Project Operations components and versions:

   - Project Operations in Microsoft Dataverse environment version 4.12.0.148 or 4.12.0.152.
   - Project management and accounting in Dynamics 365 Finance environment version 10.0.20.

## Features included in this release

The following features are included in this release:

- Ability for administrators to view PSS logs and Operations Set logs from the settings menu. The logs are stored for 90 days.

## Project Operations dual-write maps updates

There are no updates for Project Operations dual-write maps in this release.

For a current list and versions of Project Operations dual-write maps, see [Project Operations dual-write map versions](../environment/resource-dual-write-maps.md).

Always run the latest version of the map in your environment and enable all related table maps as you update your Project Operations Dataverse solution and Finance solution version. Certain features and capabilities might not work correctly if the latest version of the map isn't activated. You can see the active version of the map on the **Dual-write** page in the **Version** column. Activate a new version of the map by selecting **Table map versions**, selecting the latest version, and then saving the selected version. If you have customized an out-of-the-box table map, reapply the changes. For more information, see [Application lifecycle management](/dynamics365/fin-ops-core/dev-itpro/data-entities/dual-write/app-lifecycle-management).

If you encounter an issue starting the map, follow the instructions in the [Missing table columns issue on maps](/dynamics365/fin-ops-core/dev-itpro/data-entities/dual-write/dual-write-troubleshooting-finops-upgrades#missing-table-columns-issue-on-maps) section in the Dual-write troubleshooting guide.

## Quality updates

### Project Operations on Dataverse

| **Feature area**              | **Reference number** | **Quality update**                                                                                                                                                                                             |
|-------------------------------|----------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Billing and Pricing           | 2224046              | The **Transaction Class** field is editable on the **Quote Line Details** tab, but is locked if you are working from the **Quote Line Details** page.                                                                     |
| Billing and Pricing           | 2224400              | The **Close Quote As Won** action fails when a quote has no date milestones.                                                                                                                                    |
| Billing and Pricing           | 2234089              | When you manually enter a product description, it's cleared after you enter a quantity for a material estimate.                                                                                                                         |
| Billing and Pricing           | 2234100              | The **Task Billing Setup** grid doesn't include the **Material** column and it's value on the **Task Billing** tab of the project.                                                                                                       |
| Billing and Pricing           | 2277409              | The product ID isn't available on the contract line detail for a material type line.                                                                                                                                        |
| Billing and Pricing           | 2281728              | Creating a contract line unnecessarily reevaluates actuals causing significant increases in data volume, which impacts performance.                                                                                |
| Billing and Pricing           | 2298668              | Journal lines associated to a recalled and deleted expense aren't removed.                                                                                                                                     |
| Billing and Pricing           | 2300192              | When multiple users are editing an invoice, it's possible for a new invoice line detail to be created on a confirmed invoice.                                                                                   |
| Billing and Pricing           | 2301569              | Invoices can't be corrected if a \$0 amount retainer has been applied.                                                                                                                                        |
| Billing and Pricing           | 2307965              | An error occurs if a category price is created with missing values.                                                                                                                           |
| Billing and Pricing           | 2326870              | An error occurs in **Microsoft.Dynamics.ProjectService.Plugins.PostInvoiceLineDelete** if **producttypecode** is null.                                                                            |
| Billing and Pricing           | 2332732              | An error occurs if a contract line milestone is created without an order line.                                                                                                                |
| Project Planning and Tracking | 2181094              | The Project Scheduling API now supports PSS Logs and Operation Set Logs which are stored for 90 days.                                                                                                                  |
| Project Planning and Tracking | 2254201              | The **Schedule Mode** label is updated with details that describe the defaulting logic.                                                                                                                                      |
| Project Planning and Tracking | 2300252              | The **openProject** response cache is updated and includes the token owner in the cache key, **base Url**, and **Segment Url** so that **Request Url** can always be re-created if the **base Url** changes. |
| Project Planning and Tracking | 2301312              | **msdyn_membershipstatus** has been removed from the **Project Team Member** view.                                                                                                                                        |
| Project Planning and Tracking | 2302759              | Products are unnecessarily fetched on the **Resource Assignments**, **Estimates**, and **Expense Estimates** tabs.                                                                                                        |
| Project Planning and Tracking | 2308050              | **CopyProject** fails with the error, “Failed to get token to talk to remote service”.                                                                                                                           |
| Project Planning and Tracking | 2322650              | The **Project Task List** view has been updated to display the date of the task by default.                                                                                                            |
| Project Planning and Tracking | 2327266              | **CopyProject** generates the error, "Key not found in dictionary" when copying estimates.                                                                                                      |
| Project Planning and Tracking | 2328123              | **CopyProject** generates the error, "Failed to get token to talk to remote service".                                                                                                                          |
| Project Planning and Tracking | 2336258              | **CopyProject** incorrectly copies the position names of resources.                                                                                                                                                 |
| Billing and Pricing           | 2224476              | The **Bookable Resource** field doesn't correctly default to the logged in user on the **Material Usage** page.                                                                                                            |
| Resource Management           | 2277249              | An error occurs when a non-project-based resource requirement is updated.                                                                                                            |
| Resource Management           | 2323869              | Resource utilization doesn't correctly recognize filtered resources.                                                                                                                                             |
| Time and Expense              | 2176538              | Incorrect filter operators are applied to the **Time Entry** control.                                                                                                                                                   |
| Time and Expense              | 2177462              | Deleting a time entry in the grid doesn't update the **Submit**, **Recall**, **Delete**, and **Edit Entry** button status as expected.                                                                                        |
| Time and Expense              | 2299985              | **TimeEntriesImportFromResourceAssignment** doesn't maintain the start/end time from the assignment contours.                                                                                                  |
| Time and Expense              | 2318426              | After a time entry is submitted, locked fields can still be edited.                                                                                                                                   |
| Time and Expense              | 2323749              | An error occurs when an expense is created from the **Related** tab of a bookable resource.                                                                                                      |
| Time and Expense              | 2327678              | When you create a time entry from the **Related** tab of a bookable resource, the parent resource isn't passed to the time entry control.                                                                            |
| General                       | 2296857              | Progress tracking for long running jobs.                                                                                                                                                                        |
| General                       | 2253682              | The Project Operations dual-write solution shouldn't be installed when dual-write core is installed in an environment without the dual-write orchestration solution.                                                |
| General                       | 2316420              | Project service core provisioning fails if the application user’s business unit is changed.                                                                                                                     |
| General                       | 2376405              | Fixed publisher driven update issue (Quality update is available in version 4.12.0.152)                                                                                                                     |
### Project management and accounting on Dynamics 365 Finance

| Feature area                      | Reference number | Quality update                                                                                                                                                                                                                                                                                                                |
|-----------------------------------|------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Project management and accounting | 4620267          | Can't personalize forms to add a **Purpose** field to the **Project posted transaction**, **Invoice proposal creation**, and **Invoice proposal** pages.                                                                                                                                                                                         |
| Project management and accounting | 4613449          | When you select a Project contract ID in Finance, the Project Operations integrated environment opens the page to create a new record, instead of the page for already created project contracts.                                                                                                                                           |
| Project management and accounting | 4614445          | In the Project Operations integrated scenario deployment, you can't edit the **Item sales tax group** field on the invoice proposal that's imported from staging. The item sales tax group should be editable for an open invoice proposal of all transaction types including on account, hours, expenses, fees, and items. |
| Project management and accounting |                  | Can't post an invoice proposal resulting from a negative time transaction correction.                                                                                                                                                                                                                                              |
| Project management and accounting |                  | Invoice proposal lines are duplicated because of multiple **Import from staging** periodic processes running at the same time.                                                                                                                                                                                                                |

