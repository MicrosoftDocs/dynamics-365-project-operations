---
title: What's new or changed in Project Service Automation Update Release 34, V3
description: This article lists the features and fixes that are available in Project Service Automation Update Release 34, V3.
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


# What's new or changed in Project Service Automation Update Release 34, V3

[!include [banner](../includes/psa-now-project-operations.md)]

We're pleased to announce the latest update for the Microsoft Dynamics 365 Project Service Automation app. This release includes some important improvements to quality, performance, and usability. It's compatible with Dynamics 365 9.x. To update to this release, visit the Admin Center for Dynamics 365 online solutions page, and install the update. For more information, see [Install, update, or remove a preferred solution](/power-platform/admin/install-remove-preferred-solution).

This article lists the features and fixes that are new or changed for Project Service Automation V3, Update Release 34. This version has a build number of V3.10.55.38 and is generally available through a self-update in July 2021.

## Update Release 34

### Bug fixes
The following issues have been fixed.

**General**

- Publisher driven updates don't activate the new modern approval workflow.
- The **Target Status** and **Action Type** attributes are missing on the **Approval Set** main page.

**Time and Expense**

- Unable to approve a recall request using the modern approval flow.
- Copying a week of time entries doesn't work when copying entries that aren't related to the logged in user.

**Project planning**

- Resource assignment contours are corrupted when importing from the Microsoft Project desktop add-in.

**Resource management**

- When you publish a project from the Microsoft Project desktop client add-in, the end date of existing requirements is changed.
- Decimal precision exceeds two decimal places in the extend bookings confirmation dialog.

**Sales**

- When you add a product-based line with an existing product to a project contract, a **key not found in dictionary** exception is displayed.
- Leads can't be qualified when an order type is mapped from a lead to an opportunity.
