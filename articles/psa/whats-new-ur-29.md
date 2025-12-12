---
title: What's new or changed in Project Service Automation Update Release 29, V3
description: This article lists the features and fixes that are available in Project Service Automation Update Release 29, V3.
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



# What's new or changed in Project Service Automation Update Release 29, V3

[!include [banner](../includes/psa-now-project-operations.md)]

We’re pleased to announce the latest update for the Project Service Automation application for Dynamics 365. This release includes some important improvements to quality, performance, and usability. This release is compatible with Dynamics 365 9.x. To update to this release, visit the Admin Center for Dynamics 365 online solutions page to install the update. For more information, see [Install, update, or remove a preferred solution](/power-platform/admin/install-remove-preferred-solution).

This article lists the features and fixes that are new or changed for Project Service Automation V3, Update Release 29. This version has a build number of V3.10.47.7 and is generally available through a self-update in February 2021.

## Update Release 29

### Bug fixes

**Time and Expense**

The following issues have been fixed:

- Users can't see working hours logged on non-working days in the time entry grid.
- Approved expense entries can be edited on the grid.

**Project Management**

The following issues have been fixed:

- Missing validation logic to ensure resource assignment effort hours can't be negative.
- The custom action, **AssignResourcesForTask** updates all fields instead of only changed fields.
- When copying a project in an environment with plug-ins or workflows that are registered on the **CreateProject** event, the **msdyn_bulkgenerationstatus** attribute isn't updated if the **CopyWBSToProject** fails.
- When you expand the project calendar, the working days aren't sorted in ascending order causing some project task updates to fail.
- Changing the Project Manager on an existing project triggers the organizational unit defaulting logic.

**Sales**

The following issues have been fixed:

- The **Contract Performance** tab on the **Contract** page fails silently during initialization when no contract lines are present.
