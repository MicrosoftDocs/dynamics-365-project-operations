---
title: What's new or changed in Project Service Automation Update Release 28, V3
description: This topic lists the features and fixes that are available in Project Service Automation Update Release 28, V3.
author: ruhercul
manager: kfend
ms.service: project-operations
ms.custom: dyn365-projectservice
ms.date: 01/22/2021
ms.topic: article
ms.author: ruhercul
audience: Admin
search.audienceType: 
  - admin
  - customizer
  - enduser
search.app: 
  - D365CE
  - D365PS
  - ProjectOperations
---



# What's new or changed in Project Service Automation Update Release 28, V3


Project Service Automation Update Release 28, V3
================================================

We’re pleased to announce the latest update for the Project Service Automation
application for Dynamics 365. This release includes some important improvements
to quality, performance, and usability. This release is compatible with Dynamics
365 9.x. To update to this release, visit the Admin Center for Dynamics 365
online solutions page to install the update. For more information, see [Install,
update, or remove a preferred
solution](https://docs.microsoft.com/power-platform/admin/install-remove-preferred-solution).

This topic lists the features and fixes that are new or changed for Project
Service Automation V3, Update Release 28 This version has a build number of
V3.10.46.32 and is generally available through a self-update in January 2021.

Update Release 28
-----------------

### Bug fixes

**Time and Expense**

The following issues have been fixed:

-   Users are able to use Bulk Edit to update time entries that have been
    approved/Submitted.

**Project Management**

The following issues have been fixed:

-   Some tasks cannot be opened for edited using the Edit Task Button in the WBS
    Ribbon in narrow cases when the task GUID is interpreted as a number.

**Sales**

The following issues have been fixed:

-   Null Reference Exception generated when the **GetEstimatesForProject**
    plugin is invoked.

-   "Mark ready to invoice" on milestone grid pseudo-updates attributes other
    than **InvoiceStatus**

