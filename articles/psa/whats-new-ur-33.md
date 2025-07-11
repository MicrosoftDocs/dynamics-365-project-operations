---
title: What's new or changed in Project Service Automation Update Release 33, V3
description: This article lists the features and fixes that are available in Project Service Automation Update Release 33, V3.
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


# What's new or changed in Project Service Automation Update Release 33, V3

[!include [banner](../includes/psa-now-project-operations.md)]

We're pleased to announce the latest update for the Microsoft Dynamics 365 Project Service Automation app. This release includes some important improvements to quality, performance, and usability. It's compatible with Dynamics 365 9.x. To update to this release, visit the Admin Center for Dynamics 365 online solutions page, and install the update. For more information, see [Install, update, or remove a preferred solution](/power-platform/admin/install-remove-preferred-solution).

This article lists the features and fixes that are new or changed for Project Service Automation V3, Update Release 33. This version has a build number of V3.10.54.98 and is generally available through a self-update in July 2021.

## Update Release 33

### Bug fixes

**Time and Expense**

The following issues have been fixed:

- Two locked fields, **msdyn_description** and **msdyn_externaldescription** are editable after submission.
- An error message occurs if an expense is created that isn't related to a project.
- When a time entry is created, the resource role defaults to an inactive role.
- Journal lines associated with a recalled and deleted expense aren't deleted.
- On the **Time entry Quick Create Form**, update the **Project Task List** view to change the date displayed by default to the start date of the task.
- When you create a time entry from the **Related** tab of the bookable resource, the time entry is incorrectly created for the signed-in user instead of the parent bookable resource.
- New fields are added to the **Bulk approval MDD** dialog box.

**Project planning**

The following issues have been fixed:
- Slow project creation performance when project work hour templates are applied with complex calendars.
- When the start date is greater than the end date, an error displays on the copy project template because of differences in the time component of each field.

**Resource management**

The following issues have been fixed:
- An incorrect parameter is used in the resource utilization query and the XML leads to incorrect filter results on the **Resource Utilization** grid.
- The **Extend Bookings** confirmation displays incorrect end date for bookings.

**Sales**

The following issues have been fixed:
- An error message occurs if a category price is created with missing values.
- An error message occurs if a contract line milestone is created without an order line.
