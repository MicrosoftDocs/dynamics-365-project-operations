---
title: What's new or changed in Project Service Automation Update Release 45, V3
description: This article lists the features and fixes that are available in Microsoft Dynamics 365 Project Service Automation Update Release 45, V3.
author: ruhercul
ms.custom: 
  - dyn365-projectservice
  - evergreen
ms.date: 07/07/2025
ms.topic: whats-new
ms.author: ruhercul
audience: Admin
search.audienceType: 
  - admin
  - customizer
  - enduser
ms.reviewer: johnmichalak
---

# What's new or changed in Project Service Automation Update Release 45, V3

[!include [banner](../includes/psa-now-project-operations.md)]

We're pleased to announce the latest update for the Microsoft Dynamics 365 Project Service Automation app. This release includes some important improvements to quality, performance, and usability. It's compatible with Dynamics 365 9.x. To update to this release, visit the Admin Center for Dynamics 365 online solutions page, and install the update. For more information, see [Install, update, or remove a preferred solution](/power-platform/admin/install-remove-preferred-solution).

This article lists the features and fixes that are new or changed for Project Service Automation Update Release 45, V3. This version has a build number of V3.10.76.168 and is generally available through a self-update in July 2022.

## Update Release 45

### Bug fixes

The following issues have been fixed.

**Sales**

- Users can't successfully create invoices after they try to create an invoice without any unbilled sales, if they are also viewing the same instance of the page and don't refresh it.

**Time and Expense**

- When Modern Approvals is enabled and a recalled project approval is approved, the record stage is incorrectly updated to **Recall Request Approved**.
- When Modern Approvals is enabled and Cloud Flows is inactive, the approval process isn't successful, and the submitting or approving users aren't notified.
