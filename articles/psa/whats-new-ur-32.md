---
title: What's new or changed in Project Service Automation Update Release 32, V3
description: This topic lists the features and fixes that are available in Project Service Automation Update Release 32, V3.
author: ruhercul
ms.custom: dyn365-projectservice
ms.date: 06/01/2021
ms.topic: article
ms.author: ruhercul
audience: Admin
search.audienceType: 
  - admin
  - customizer
  - enduser
search.app: 
  - D365CE
  - D365PS
  - ProjectOperations
---


# What's new or changed in Project Service Automation Update Release 32, V3

[!include [banner](../includes/psa-now-project-operations.md)]

We’re pleased to announce the latest update for the Project Service Automation application for Dynamics 365. This release includes some important improvements to quality, performance, and usability. This release is compatible with Dynamics 365 9.x. To update to this release, visit the Admin Center for Dynamics 365 online solutions page to install the update. For more information, see [Install, update, or remove a preferred solution](/power-platform/admin/install-remove-preferred-solution).

This topic lists the features and fixes that are new or changed for Project Service Automation V3, Update Release 32. This version has a build number of V3.10.53.108 and is generally available through a self-update in June 2021.

## Update Release 32

### Bug fixes

**General**
- When major upgrade fails, only the main application entry points should be blocked to ensure that shared entities are still accessible.

**Time and Expense**
The following issues have been fixed:

- **TimeEntriesImportFromResourceAssignment** doesn't maintain the start and end time of the resource assignment contour slice.
- Selecting **Open Entry** on the **Time Entry** grid, may prevent you from selecting other forms.
- While importing assignments to time entries, the client code query could generate a long url that fails the query.
- In the **Time Entry** grid, after a value is deleted from a a cell, the focus doesn't remain in the grid.
- The **Reject** button has been removed from the **Processing approvals** view for modern approvals.
- Time entry bulk approval stability and performance is impacted by deadlocks and a failure to appropriately handle customizations related to the **Time Entry** entity.


**Project Planning**
- A null refernce exception is generated when you update a project with a null value in the **Contracting Unit** field.
- **Refresh Project Totals** incorrectly calculates the remaining cost and remaining sales on a project.
- Performance related to updates on resource assignment contours is impacted by redundant pricing calculations.

**Resource Management**
The following issues have been fixed:

- When a bookable resource's calendar capacity is > 1, Project Service Automation incorrectly recognizes the capacity as 0 causing an infinite loop in the schedule view.

**Sales**

The following issues have been fixed:

- When a journal line is created with a custom transaciton type, the following null reference exception occurs, *Microsoft.Dynamics.ProjectService.Plugins.JournalLinePlugins.ValidateUnitScheduleAndUnitWithTransactionType(TransactionTypetransactionType, TransactionTypeCode transTypeCodeFromPlugin)*.
- Roles and categories that are deactivated before copying a quote shouldn't be added to chargeable roles and categories of the newly copied quote.
- The document date and accounting date don't align with the start date provided on the invoice line detail for an invoice line detail created directly on a draft invoice.
- Null Reference Exceptions are generated in scenarios related to deactivating roles and categories before copying quote.
- The **Update Prices** action on the **Projects** page doesn't update expense estimates and material estimates.
