---
title: What's new or changed in Project Service Automation Update Release 43, V3
description: This article lists the features and fixes that are available in Microsoft Dynamics 365 Project Service Automation Update Release 43, V3.
author: ruhercul
ms.custom: 
  - dyn365-projectservice
  - evergreen
ms.date: 04/09/2024
ms.topic: article
ms.author: ruhercul
audience: Admin
search.audienceType: 
  - admin
  - customizer
  - enduser
ms.reviewer: johnmichalak
---

# What's new or changed in Project Service Automation Update Release 43, V3

[!include [banner](../includes/psa-now-project-operations.md)]

We're pleased to announce the latest update for the Microsoft Dynamics 365 Project Service Automation app. This release includes some important improvements to quality, performance, and usability. It is compatible with Dynamics 365 9.x. To update to this release, visit the Admin Center for Dynamics 365 online solutions page, and install the update. For more information, see [Install, update, or remove a preferred solution](/power-platform/admin/install-remove-preferred-solution).

This article lists the features and fixes that are new or changed for Project Service Automation Update Release 43, V3. This version has a build number of V3.10.74.200 and is generally available through a self-update in May 2022.

## Update Release 43

### Bug fixes

The following issues have been fixed.


**Time and Expense**

- When importing time entries from bookings or resource assignments, the reference to the related bookable resource is not maintained.
- When the time entry grid is expanded to full screen, navigating the grid with the tab key does not function.
- When submitting a time entry created by another user, the **Submitted By** field is incorrectly populated with the user who created the time sheet.
