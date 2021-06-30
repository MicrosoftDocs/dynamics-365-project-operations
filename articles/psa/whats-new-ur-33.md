---
title: What's new or changed in Project Service Automation Update Release 33, V3
description: This topic lists the features and fixes that are available in Project Service Automation Update Release 33, V3.
author: ruhercul
ms.custom: dyn365-projectservice
ms.date: 06/30/2021
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


# What's new or changed in Project Service Automation Update Release 33, V3

[!include [banner](../includes/psa-now-project-operations.md)]

We're pleased to announce the latest update for the Microsoft Dynamics 365 Project Service Automation app. This release includes some important improvements to quality, performance, and usability. It's compatible with Dynamics 365 9.x. To update to this release, visit the Admin Center for Dynamics 365 online solutions page, and install the update. For more information, see [Install, update, or remove a preferred solution](/power-platform/admin/install-remove-preferred-solution).

This topic lists the features and fixes that are new or changed for Project Service Automation V3, Update Release 33. This version has a build number of V3.xx.xx.xx and is generally available through a self-update in June 2021.

## Update Release 33

### Bug fixes

#### Time and Expense

The following issues have been fixed:
- 2 locked fields, msdyn_description and msdyn_externaldescription fields are editable after submission.
- Null Reference Exception thrown if an expense is created that is not related to a project.
- When creating a time entry, a resource's role defaults to an inactive one.
- Journal Lines associated to a recalled and deleted Expense are not deleted.
- On the **Time entry Quick Create Form**, Update the Project Task List View to change the date displayed by default to the start date of the task.
- From the related tab of the bookable resource, creating a time entry would incorrectly create a time entry for the logged in user instead of the parent bookable resource.
- New fields added to the bulk approval MDD dialog.

#### Project Planning

The following issue has been fixed:
- Slow project creation performance observed when project work hour templates are applied with complex calendars.
- Start Date greater than end date error thrown on copying project/template due to differences in the time component of each field.

#### Resource Management

The following issue has been fixed:
- Incorrect parameter used in resource utilization query xml leads to incorrect filter results on the Resource Utilization grid.
- **Extend Bookings** confirmation displays the incorrect end date of the bookings.

#### Sales

The following issues have been fixed:
- Null Reference Exception thrown if a category price is created with missing values.
- Null Reference Exception thrown if a contract line milestone is created without an order line.
