---
title: What's new or changed in Project Service Automation Update Release 14, V3
description: This article provides information about what's new in Project Service Automation Update Release 14 V3.
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


# Project Service Automation Update Release 14, V3

[!include [banner](../includes/psa-now-project-operations.md)]

We’re pleased to announce the latest update for the Dynamics 365 Project Service Automation (PSA) application. This release includes some important improvements to quality, performance, and usability. This release is compatible with Dynamics 365 9.x. To update to this release, visit the Admin Center for Dynamics 365 online, and go to the solutions page to install the update. For more information, see [Install, update, or remove a preferred solution](/power-platform/admin/install-remove-preferred-solution).

This article lists the features and fixes that are new or changed for PSA V3, Update Release 14. This version has a build number of V3.10.4.21 and is available on the following schedule:

- **General availability (self-update):** January 2020
- **Auto-update:** February 2020

## Update Release 14

### Enhancements

- Sales

     - Custom field values from **Quote Line Details** are copied to **Project Contract Line Details** when a quote is updated to **Closed as won**.
     - Confirmed projects can be **Closed as lost**.

- Resource Management

     - When extending bookings, users will be prompted with a confirmation dialog box to summarize booking results and provide a link to Maintain Bookings.


### Bug fixes

- Time and Expense

     - Fixed: Improved the user experience when the user has not selected any entries to be corrected.

- Resource Management

     - Fixed: Booking a resource multiple times overflows the name of the bookable resource.

- Sales

     - Fixed: The total sales price is not calculated until the user also inputs a cost price for expense estimates on a project.
     - Fixed: Closing a quote as **Won** fails if the associated project contract is not in a **Draft** state.



[!INCLUDE[footer-include](../includes/footer-banner.md)]
