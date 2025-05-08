---
title: What's new or changed in Project Service Automation Update Release 28, V3
description: This article lists the features and fixes that are available in Project Service Automation Update Release 28, V3.
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



# What's new or changed in Project Service Automation Update Release 28, V3

[!include [banner](../includes/psa-now-project-operations.md)]

We’re pleased to announce the latest update for the Project Service Automation application for Dynamics 365. This release includes some important improvements to quality, performance, and usability. This release is compatible with Dynamics 365 9.x. To update to this release, visit the Admin Center for Dynamics 365 online solutions page to install the update. For more information, see [Install, update, or remove a preferred solution](/power-platform/admin/install-remove-preferred-solution).

This article lists the features and fixes that are new or changed for Project Service Automation V3, Update Release 28 This version has a build number of V3.10.46.32 and is generally available through a self-update in January 2021.

## Update Release 28

### Bug fixes

**Time and Expense**

The following issues have been fixed:

- Users can use **Bulk Edit** to update time entries that have been approved and submitted.

**Project Management**

The following issues have been fixed:

- In cases where the task GUID is interpreted as a number, tasks can't be opened for edit using **Edit Task** in the ribbon on the **Work Breakdown Structure** page.

**Sales**

The following issues have been fixed:

- A null reference exception is generated when the **GetEstimatesForProject** plug-in is invoked.
- **Mark ready to invoice** on the milestone grid only partially updates attributes, except for the **InvoiceStatus** attribute, which is updated.



[!INCLUDE[footer-include](../includes/footer-banner.md)]
