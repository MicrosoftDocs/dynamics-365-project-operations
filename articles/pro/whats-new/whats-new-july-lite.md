---
title: What's new July 2021 - Project Operations lite deployment
description: This topic provides information about the quality updates available in the July 2021 release of Project Operations lite deployment.
author: sigitac
ms.date: 07/05/2021
ms.topic: article
ms.prod:
ms.reviewer: kfend 
ms.author: sigitac
---

# What's new July 2021 - Project Operations lite deployment

_Applies To: Lite deployment - deal to proforma invoicing_

This topic applies to the following Dynamics 365 Project Operations components and versions:

  - Project Operations on Dataverse environment version 4.12.0.129.

## Quality updates
| **Feature area**              | **Reference number** | **Quality update**                                                                                                                                                                                             |
|-------------------------------|----------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Billing and Pricing           | 2224046              | "Transaction class" is editable on editable grid under Quote line Details tab but same field are locked if you open the Quote Line Details                                                                     |
| Billing and Pricing           | 2224400              | **Close Quote As Won** ribbon action fails on quote with no-date milestones                                                                                                                                    |
| Billing and Pricing           | 2234089              | Write-in Product description are cleared after entering quantity in Material estimates                                                                                                                         |
| Billing and Pricing           | 2234100              | Task billing setup grid does not include Material column and its value on the Project's task billing tab                                                                                                       |
| Billing and Pricing           | 2277409              | Product ID not available in Contract Line Detail for Material type line                                                                                                                                        |
| Billing and Pricing           | 2281728              | Contract line creation reevaluates actuals unnecessarily causing significant increases in data volume and impacting performance                                                                                |
| Billing and Pricing           | 2298668              | Journal Lines associated to a recalled and deleted expense are not removed                                                                                                                                     |
| Billing and Pricing           | 2300192              | When multiple users are editing an invoice it is possible for a new invoice line detail to be created on a confirmed invoice                                                                                   |
| Billing and Pricing           | 2301569              | Invoices cannot be corrected if a \$0 amount retainer has been applied.                                                                                                                                        |
| Billing and Pricing           | 2307965              | A Null Reference Exception thrown if a category price is created with missing values                                                                                                                           |
| Billing and Pricing           | 2326870              | A Null Reference Exception thrown in the Microsoft.Dynamics.ProjectService.Plugins.PostInvoiceLineDelete if producttypecode is null                                                                            |
| Billing and Pricing           | 2332732              | A Null Reference Exception thrown if a contract line milestone is created without an order line                                                                                                                |
| Project Planning and Tracking | 2181094              | The Project Scheduling API now support an PSS Logs and Operation Set Logs stored for 90 days.                                                                                                                  |
| Project Planning and Tracking | 2254201              | Schedule Mode Label updated with details describing the defaulting logic.                                                                                                                                      |
| Project Planning and Tracking | 2300252              | **openProject** response cache has been updated to include the token owner in the cache key and **base Url** and **Segment Url** so that **Request Url** can always be re-created if the **base Url** changes. |
| Project Planning and Tracking | 2301312              | "msdyn_membershipstatus" has been removed from Project Team Member view                                                                                                                                        |
| Project Planning and Tracking | 2302759              | Products are being fetched on Resource Assignments, Estimates, and Expense Estimates tabs unnecessarily                                                                                                        |
| Project Planning and Tracking | 2308050              | **CopyProject** failing with error – “Failed to get token to talk to remote service”                                                                                                                           |
| Project Planning and Tracking | 2322650              | The Project Task List View has been updated to display date display the date of the task by default                                                                                                            |
| Project Planning and Tracking | 2327266              | **CopyProject** generating the following exception when copying estimates - "key not found in dictionary"                                                                                                      |
| Project Planning and Tracking | 2328123              | **CopyProject** is failing with error "Failed to get token to talk to remote service"                                                                                                                          |
| Project Planning and Tracking | 2336258              | **CopyProject** incorrectly copies position names of resources                                                                                                                                                 |
| Billing and Pricing           | 2224476              | Bookable resource field is not correctly defaulted to the logged in user on the material usage form                                                                                                            |
| Resource Management           | 2277249              | A null reference exception error is thrown when a non-project based resource requirement is updated                                                                                                            |
| Resource Management           | 2323869              | Resource Utilization does not correctly respect filtered resources                                                                                                                                             |
| Time and Expense              | 2176538              | Incorrect filter operators applied to the Time Entry control                                                                                                                                                   |
| Time and Expense              | 2177462              | Deleting a time entry in the grid does not update the Submit, Recall, Delete, and Edit Entry button status to disabled.                                                                                        |
| Time and Expense              | 2299985              | **TimeEntriesImportFromResourceAssignment** does not maintain the start/end time from the assignment contours                                                                                                  |
| Time and Expense              | 2318426              | User was able to edit time entry locked fields after submitting a time entry                                                                                                                                   |
| Time and Expense              | 2323749              | A Null Reference Exception is thrown when creating an expense from the related tab of a bookable resource                                                                                                      |
| Time and Expense              | 2327678              | When creating a time entry from the related tab of a bookable resource, the parent resource is not passed to the time entry control                                                                            |
| General                       | 2296857              | Progress tracking for long running jobs                                                                                                                                                                        |
| General                       | 2253682              | The Project Operations Dual Write solution should not install when Dual Write Core is installed in an environment without the Dual Write Orchestration solution                                                |
| General                       | 2316420              | Project Service Core Provisioning Fails if the application user’s business unit is changed                                                                                                                     |
