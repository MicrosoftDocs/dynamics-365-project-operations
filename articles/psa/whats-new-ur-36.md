---
title: What's new or changed in Project Service Automation Update Release 36, V3
description: This article lists the features and fixes that are available in Microsoft Dynamics 365 Project Service Automation Update Release 36, V3.
author: ruhercul
ms.custom: 
  - dyn365-projectservice
  - evergreen
ms.date: 04/09/2024
ms.topic: whats-new
ms.author: ruhercul
audience: Admin
search.audienceType: 
  - admin
  - customizer
  - enduser
ms.reviewer: johnmichalak
---

# What's new or changed in Project Service Automation Update Release 36, V3

[!include [banner](../includes/psa-now-project-operations.md)]

We're pleased to announce the latest update for the Microsoft Dynamics 365 Project Service Automation app. This release includes some important improvements to quality, performance, and usability. It's compatible with Dynamics 365 9.x. To update to this release, visit the Admin Center for Dynamics 365 online solutions page, and install the update. For more information, see [Install, update, or remove a preferred solution](/power-platform/admin/install-remove-preferred-solution).

This article lists the features and fixes that are new or changed for Project Service Automation Update Release 36, V3. This version has a build number of V3.10.57.152 and is generally available through a self-update in October 2021.

## Update Release 36

### Bug fixes

The following issues have been fixed.

**General**
- The **Default Work Hour Template** field name is translated incorrectly on the **Project Parameters** page.
- Async plug-ins aren't correctly handling exceptions related to the **SharedVariableService**.

**Time and Expense**
- When journal lines are missing or the user doesn't have the correct privileges to read journal lines, an incorrect error occurs when project approvals are canceled.
- Users can't cancel an approval when an expense or time entry has more than one associated project approval.
- **Absence** and **Vacation** are incorrectly translated for the Chinese language in a lookup on the **Time Entry** quick create page.

**Resource management**
- User can't search for resources in the **Schedule Assistant** when the view mode is set to **Day**, **Week**, or **Month**.
- Generic resources are incorrectly allowed to have empty position names. 
- Closing a contract as lost doesn't cancel future bookings.

**Sales**
- When an environment has a large volume of products, performance degrades in the **Materials Estimate** grid.
- When creating a project from a template, the project currency does not default to the respective Project Manager's contracting unit.
- Actual amounts don't always match what is reflected on the project due, or the amounts become negative in specific recall scenarios.
- An error occurs when you associate a project created from project template to a contract line.
- Users are able to delete a contract line with the milestones, **Ready to invoice** and **Invoice Created**. This shouldn't be allowed.
- When estimates are imported from a project, the quote line detail chargeability is set incorrectly when task-based billing is enabled for the quote line.
- When you add a fixed price billing milestone, the milestone isn't reflected in the milestone subgrid until the page is refreshed.
- A null reference exception is generated when you create a project contract with a quote name that is null.
- Manual mode tasks where the project currency is different from the resource's currency result in incorrect price estimates.
- Users can't recall a transaction that has been successfully corrected by a corrective invoice.
- Deactivated transaction categories appear in the **Expense Estimates** grid.



