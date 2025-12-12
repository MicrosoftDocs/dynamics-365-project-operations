---
title: What's new or changed in Project Service Automation Update Release 32, V3
description: This article lists the features and fixes that are available in Project Service Automation Update Release 32, V3.
author: ruhercul
ms.custom: 
  - dyn365-projectservice
  - evergreen
ms.date: 07/07/2025
ms.update-cycle: 1095-days
ms.topic: whats-new
ms.author: ruhercul
audience: Admin
search.audienceType: 
  - admin
  - customizer
  - enduser
ms.reviewer: johnmichalak
---


# What's new or changed in Project Service Automation Update Release 32, V3

[!include [banner](../includes/psa-now-project-operations.md)]

We're pleased to announce the latest update for the Microsoft Dynamics 365 Project Service Automation app. This release includes some important improvements to quality, performance, and usability. It's compatible with Dynamics 365 9.x. To update to this release, visit the Admin Center for Dynamics 365 online solutions page, and install the update. For more information, see [Install, update, or remove a preferred solution](/power-platform/admin/install-remove-preferred-solution).

This article lists the features and fixes that are new or changed for Project Service Automation V3, Update Release 32. This version has a build number of V3.10.53.108 and is generally available through a self-update in June 2021.

## Update Release 32

### Bug fixes

#### General

- When a major upgrade fails, only the main application entry points should be blocked, to ensure that shared entities are still accessible.

#### Time and Expense

The following issues have been fixed:

- **TimeEntriesImportFromResourceAssignment** doesn't maintain the start and end times of the resource assignment contour slice.
- When you select **Open Entry** on the **Time Entry** grid, you might be prevented from selecting other forms.
- While you import assignments to time entries, the client code query could generate a long URL that fails the query.
- In the **Time Entry** grid, after a value is deleted from a cell, the focus doesn't remain in the grid.
- The **Reject** button has been removed from the **Processing approvals** view for modern approvals.
- The stability and performance of time entry bulk approval are affected by deadlocks and a failure to appropriately handle customizations that are related to the **Time Entry** entity.

#### Project Planning

- A null reference exception is generated when you update a project that has a null value in the **Contracting Unit** field.
- **Refresh Project Totals** incorrectly calculates the remaining cost and remaining sales on a project.
- Redundant pricing calculations affect performance that is related to updates on resource assignment contours.

#### Resource Management

The following issue has been fixed:

- When a bookable resource's calendar capacity is more than 1, Project Service Automation incorrectly recognizes the capacity as 0 (zero). Therefore, an infinite loop occurs in the schedule view.

#### Sales

The following issues have been fixed:

- When a journal line is created that has a custom transaction type, the following null reference exception occurs: *Microsoft.Dynamics.ProjectService.Plugins.JournalLinePlugins.ValidateUnitScheduleAndUnitWithTransactionType(TransactionTypetransactionType, TransactionTypeCode transTypeCodeFromPlugin)*.
- Roles and categories that are inactivated before a quotation is copied should not be added to chargeable roles and categories of the newly copied quotation.
- The document date and accounting date aren't aligned with the start date that is provided on an invoice line detail that is created directly on a draft invoice.
- Null reference exceptions are generated in scenarios that are related to inactivation of roles and categories before a quotation is copied.
- The **Update Prices** action on the **Projects** page doesn't update expense estimates and material estimates.
