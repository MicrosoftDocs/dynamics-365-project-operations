---
title: What's new or changed in Project Service Automation Update Release 30, V3
description: This article lists the features and fixes that are available in Project Service Automation Update Release 30, V3.
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



# What's new or changed in Project Service Automation Update Release 30, V3

[!include [banner](../includes/psa-now-project-operations.md)]

We’re pleased to announce the latest update for the Project Service Automation application for Dynamics 365. This release includes some important improvements to quality, performance, and usability. This release is compatible with Dynamics 365 9.x. To update to this release, visit the Admin Center for Dynamics 365 online solutions page to install the update. For more information, see [Install, update, or remove a preferred solution](/power-platform/admin/install-remove-preferred-solution).

This article lists the features and fixes that are new or changed for Project Service Automation V3, Update Release 30. This version has a build number of V3.10.51.61 and is generally available through a self-update in April 2021.

## Update Release 30

### Bug fixes

**Time and Expense**

The following issues have been fixed:

- An error occurs when you create and save a time entry on the **Quick Create** page if the **Role** field is removed.
- The Time Entry filter applies the wrong filter operator.
- Copied timesheets aren't automatically displayed when you select **Copy Week** on the time entry control.

**Resource Management**

The following issues have been fixed:

- When you extend a booking, the booking status assigned to the hard booking is incorrect. Extending a booking respects the booking status defined as **Committed** in the booking setup metadata.
- When a valid booking status isn't specified, the error message is not correctly localized.

**Project Management**

The following issues have been fixed:

- Projects can't be created in one currency and include related tasks in another currency.

**Sales**

The following issues have been fixed:

- When a price list is copied, prices aren't updated.
- Closing a quote as won fails when the cost detail has a value for origin.
- On the **Project Task** entity, **Estimated Cost** has been renamed to **Planned Cost (Base)**.
- A null reference exception is generated when invoices are created or deleted.
