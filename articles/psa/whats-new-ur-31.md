---
title: What's new or changed in Project Service Automation Update Release 31, V3
description: This article lists the features and fixes that are available in Project Service Automation Update Release 31, V3.
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



# What's new or changed in Project Service Automation Update Release 31, V3

[!include [banner](../includes/psa-now-project-operations.md)]

We’re pleased to announce the latest update for the Project Service Automation application for Dynamics 365. This release includes some important improvements to quality, performance, and usability. This release is compatible with Dynamics 365 9.x. To update to this release, visit the Admin Center for Dynamics 365 online solutions page to install the update. For more information, see [Install, update, or remove a preferred solution](/power-platform/admin/install-remove-preferred-solution).

This article lists the features and fixes that are new or changed for Project Service Automation V3, Update Release 31. This version has a build number of V3.10.52.77 and is generally available through a self-update in May 2021.

## Update Release 31

### Bug fixes

**Time and Expense**

The following issues have been fixed:

- Time entry control command buttons on the **Bookable Resource** page were confusing.
- A null reference exception was generated in **Project.SetTrackingFields** when approving a time entry.

**Resource Management**

The following issues have been fixed:

- **Create Team Member** doesn't correctly display the booking setup metadata setting for **Default Booking Committed Status**.
- When upgrading from PSA 1.X to 3.X, the upgrade process fails at **UpgradeResourceRequirements**.


**Sales**

The following issues have been fixed:

- Actual revenue converts the amounts to the project currency in the tracking grid.
- The currency default is unclear when creating journal lines, quote lines, and contract lines in scenarios where an organization's base currency differs from the project currency.
- **Pending correction journal validation** query doesn't filter by project.
- Remaining sales are calculated incorrectly on a project.
- Quotes based on a contact fail when they are created without a price list.
- No processing spinner is shown when you select **Confirm Invoice**.
- No processing spinner is shown when you select **Create Invoice**.
- Closing a quote as lost doesn't cancel the bookings.







