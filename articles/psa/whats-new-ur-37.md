---
title: What's new or changed in Project Service Automation Update Release 37, V3
description: This article lists the features and fixes that are available in Microsoft Dynamics 365 Project Service Automation Update Release 37, V3.
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

# What's new or changed in Project Service Automation Update Release 37, V3

[!include [banner](../includes/psa-now-project-operations.md)]

We're pleased to announce the latest update for the Microsoft Dynamics 365 Project Service Automation app. This release includes some important improvements to quality, performance, and usability. It's compatible with Dynamics 365 9.x. To update to this release, visit the Admin Center for Dynamics 365 online solutions page, and install the update. For more information, see [Install, update, or remove a preferred solution](/power-platform/admin/install-remove-preferred-solution).

This article lists the features and fixes that are new or changed for Project Service Automation Update Release 37, V3. This version has a build number of V3.10.58.120 and is generally available through a self-update in November 2021.

## Update Release 37

### Bug fixes

The following issues have been fixed.

**Time and Expense**
- Users are unable to delete a time entry by clearing the cell.
- The **My failed approval** view only contains project approvals with a status of **Submitted**.

**Project management**
- Users receive a null reference exception error when opening a project in the Microsoft desktop add-in if the Project team member's position name is empty.
- There is no **Save** button on the **Project Task** page so users can't save changes to task records.
- Users can't delete a project that has a task associated to a quote with a status of **Won**.

**Sales**
- The **Currency** field on the **Project** page is updated to match the applied template's currency.
- The cost is calculated incorrectly on tasks that have multiple currencies.
