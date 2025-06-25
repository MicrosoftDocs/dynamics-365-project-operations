---
title: What's new July 2021 - Project Operations lite deployment
description: This article provides information about the quality updates available in the July 2021 release of Project Operations lite deployment.
author: sigitac
ms.custom:
  - evergreen
ms.date: 04/09/2024
ms.topic: whats-new
ms.reviewer: johnmichalak
ms.author: sigitac
---

# What's new July 2021 - Project Operations lite deployment

_Applies To: Core deployment - deal to proforma invoicing_

This article applies to the following Dynamics 365 Project Operations components and versions:

  - Project Operations on Dataverse environment version 4.12.0.148 or 4.12.0.152.

## Quality updates
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
