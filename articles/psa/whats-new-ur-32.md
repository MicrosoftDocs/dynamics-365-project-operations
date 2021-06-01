---
title: What's new or changed in Project Service Automation Update Release 32, V3
description: This topic lists the features and fixes that are available in Project Service Automation Update Release 32, V3.
author: ruhercul
ms.custom: dyn365-projectservice
ms.date: 05/31/2021
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
- When major upgrade fails, only the main application entry points should be blocked to ensure shared entities are still accessible.



**Time and Expense**

The following issues have been fixed:

- TimeEntriesImportFromResourceAssignment does not maintain the start/end time of the resource assignment contour slice.
- Selecting **Open Entry**  on the Time Entry grid, may prevent a user from subsequently selecting other forms.
- While importing assignments to time entries, client code query could generate a long url that fails the query.
- In the time entry grid, after deleting a value froma a cell, focus does not remain in the grid.
- The Reject button has been removed from "Processing approvals" view for modern approvals.
- Time Entry bulk approval stability and performance is impacted by deadlocks and failure to appropriately handle customizations related to the time entry entity




**Project Planning**
- Null refernce exception generated when updating a project with a null value for the Contracting Unit.
- Refresh Project Totals incorrectly calculates Remaining Cost and Remaining Sales on project.
- Performance related to updated on resource assignment contours is impacted by redundant pricing calculations.

**Resource Management**

The following issues have been fixed:

- When a bookable resource's calendar capacity is > 1, Project Service Automation incorrectly recognizes capacity as 0, causing an infinite loop in the schedule view.




**Sales**

The following issues have been fixed:

- Null Reference  Exception Microsoft.Dynamics.ProjectService.Plugins.JournalLinePlugins.ValidateUnitScheduleAndUnitWithTransactionType(TransactionTypetransactionType, TransactionTypeCode transTypeCodeFromPlugin) when a journal line is created with any custom transaction type.
- Roles and categories that are deactivated before coping a quote should not be added to chargeable roles and categories of the newly copied quote.
- Document date and Accounting date do not align with the Start date provided on the Invoice Line Detail for an Invoice Line Detail created directly on a draft Invoice.
- Null Reference Exceptions generated in scenarios related to deactivating roles and categories before copying quote.
-  'Update Prices' action on project main form does not update expense estimates and material Estimates.













