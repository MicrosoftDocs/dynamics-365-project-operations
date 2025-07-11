---
title: What's new or changed in Project Service Automation Update Release 40, V3
description: This article lists the features and fixes that are available in Microsoft Dynamics 365 Project Service Automation Update Release 40, V3.
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

# What's new or changed in Project Service Automation Update Release 40, V3

[!include [banner](../includes/psa-now-project-operations.md)]

We're pleased to announce the latest update for the Microsoft Dynamics 365 Project Service Automation app. This release includes some important improvements to quality, performance, and usability. It's compatible with Dynamics 365 9.x. To update to this release, visit the Admin Center for Dynamics 365 online solutions page, and install the update. For more information, see [Install, update, or remove a preferred solution](/power-platform/admin/install-remove-preferred-solution).

This article lists the features and fixes that are new or changed for Project Service Automation Update Release 40, V3. This version has a build number of V3.10.61.61 and is generally available through a self-update in February 2022.

## Update Release 40

### Features
Phase 1 of the upgrade from Project Service Automation to Project Operations - Lite will be released in February 2022 to all customers. To check for eligibility, see [Upgrade from Project Service Automation to Project Operations](upgrade-project-operations-non-stocked.md). If the application doesn't appear in your instance in the Power Platform Admin Center, contact support and request that the flight be enabled for your environments. Your request must include a list of environment IDs where the flight needs to be enabled.

### Bug fixes

The following issues have been fixed.

**Time and Expense**
- A note entry is missing when a time entry is rejected or canceled. 

**Sales**

- When you update cost or sales estimates using out-of-the-box plug-ins, you are incorrectly permitted to send JSON payloads that aren't valid outside of the user interface.
- When you update quote lines using the quick view, you are allowed to activate quotes.
