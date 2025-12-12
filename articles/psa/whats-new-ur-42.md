---
title: What's new or changed in Project Service Automation Update Release 42, V3
description: This article lists the features and fixes that are available in Microsoft Dynamics 365 Project Service Automation Update Release 42, V3.
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

# What's new or changed in Project Service Automation Update Release 42, V3

[!include [banner](../includes/psa-now-project-operations.md)]

We're pleased to announce the latest update for the Microsoft Dynamics 365 Project Service Automation app. This release includes some important improvements to quality, performance, and usability. It's compatible with Dynamics 365 9.x. To update to this release, visit the Admin Center for Dynamics 365 online solutions page, and install the update. For more information, see [Install, update, or remove a preferred solution](/power-platform/admin/install-remove-preferred-solution).

This article lists the features and fixes that are new or changed for Project Service Automation Update Release 42, V3. This version has a build number of V3.10.73.61 and is generally available through a self-update in April 2022.

## Update Release 42

### Bug fixes

The following issues have been fixed.

**Time and Expense**

- When a time sheet is rejected, the user who rejected it is incorrectly identified as **System**.
- When time entries are imported, the **Resource Category** value is missing.
- Project approvers can approve submitted projects when their permissions aren't specifically set to **Can Approve**.

**Sales**

- When actuals are logged on non-root level tasks, the actual costs are incorrectly aggregated.
