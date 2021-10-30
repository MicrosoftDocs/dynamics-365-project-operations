---
title: What's new or changed in Project Service Automation Update Release 37, V3
description: This topic lists the features and fixes that are available in Microsoft Dynamics 365 Project Service Automation Update Release 37, V3.
author: ruhercul
ms.custom: dyn365-projectservice
ms.date: 10/29/2021
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

# What's new or changed in Project Service Automation Update Release 37, V3

[!include [banner](../includes/psa-now-project-operations.md)]

We're pleased to announce the latest update for the Microsoft Dynamics 365 Project Service Automation app. This release includes some important improvements to quality, performance, and usability. It's compatible with Dynamics 365 9.x. To update to this release, visit the Admin Center for Dynamics 365 online solutions page, and install the update. For more information, see [Install, update, or remove a preferred solution](/power-platform/admin/install-remove-preferred-solution).

This topic lists the features and fixes that are new or changed for Project Service Automation Update Release 37, V3. This version has a build number of V3.10.58.120 and is generally available through a self-update in November 2021.

## Update Release 37

### Bug fixes

The following issues have been fixed.



**Time and Expense**
- Users are unable to delete time entry by clearing the cell.
- "My failed approval" view only contains project approvals in "Submitted" stage.

**Project management**
- Users receive a Null Reference Exception error when trying to open a project in the Microsoft desktop add-in when a Project team member's position name is null.
- "Save" Button is not present in Project Task form preventing users from saving changes to task records.
- Users are unable to delete a project containing a task associated to a won quote.

**Sales**
- The Project form's currency field is updated to match the applied template's currency.
- Cost is incorrect calculated on tasks where there are multiple ccurrencies.



