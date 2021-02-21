---
title: What's new or changed in Project Service Automation Update Release 29, V3
description: This topic lists the features and fixes that are available in Project Service Automation Update Release 29, V3.
author: ruhercul
manager: kfend
ms.service: project-operations
ms.custom: dyn365-projectservice
ms.date: 02/19/2021
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



# What's new or changed in Project Service Automation Update Release 29, V3

[!include [banner](../includes/psa-now-project-operations.md)]

We’re pleased to announce the latest update for the Project Service Automation
application for Dynamics 365. This release includes some important improvements
to quality, performance, and usability. This release is compatible with Dynamics
365 9.x. To update to this release, visit the Admin Center for Dynamics 365
online solutions page to install the update. For more information, see [Install,
update, or remove a preferred
solution](https://docs.microsoft.com/power-platform/admin/install-remove-preferred-solution).

This topic lists the features and fixes that are new or changed for Project
Service Automation V3, Update Release 29 This version has a build number of
V3.10.45.98 and is generally available through a self-update in February 2021.

Update Release 29
-----------------

### Bug fixes

**Time and Expense**

The following issues have been fixed:

-   Users are unable to see working hours logged on non-working days in the time
    entry grid.

-   Approved expense entries are editable on the Grid.

**Project Management**

The following issues have been fixed:

-   Missing validation logic to ensure resource assignment effort hours cannot
    be negative.

-   **AssignResourcesForTask** custom action unnecessarily updates all fields
    instead of only changed fields.

-   When copying a project in an environment with plugins or workflows
    registered on the **CreateProject** event, attribute
    **msdyn_bulkgenerationstatus** is not updated when the **CopyWBSToProject**
    fails.

-   When expanding the project calendar, the working days are not being sorted
    in ascending order, causing failures in some updates to project tasks.

-   Changing the Project Manager on an existing project triggers the
    organizational unit defaulting logic.

**Sales**

The following issues have been fixed:

- Contract Performance tab on the contract form fails silently during
initialization when no contract lines are present.
