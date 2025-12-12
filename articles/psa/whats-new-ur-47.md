---
title: What's new or changed in Project Service Automation Update Release 47, V3
description: This article lists the features and fixes that are available in Microsoft Dynamics 365 Project Service Automation Update Release 47, V3.
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

# What's new or changed in Project Service Automation Update Release 47, V3

[!include [banner](../includes/psa-now-project-operations.md)]

We're pleased to announce the latest update for the Microsoft Dynamics 365 Project Service Automation app. This release includes some important improvements to quality, performance, and usability. It's compatible with Dynamics 365 9.x. To update to this release, visit the Admin Center for Dynamics 365 online solutions page, and install the update. For more information, see [Install, update, or remove a preferred solution](/power-platform/admin/install-remove-preferred-solution).

This article lists the features and fixes that are new or changed for Project Service Automation Update Release 47, V3. This version has a build number of V3.10.78.8 and is generally available through a self-update in September 2022.

## Update Release 47

### Bug fixes

The following issues have been fixed.

**Resource Management**
- A validation was updated to ensure users cannot trigger a null reference exception when attempting to create a Project Team Member without a **Bookable Resource**.
