---
title: What's new or changed in Project Service Automation Update Release 35, V3
description: This topic lists the features and fixes that are available in Project Service Automation Update Release 35, V3.
author: ruhercul
ms.custom: dyn365-projectservice
ms.date: 09/02/2021
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


# What's new or changed in Project Service Automation Update Release 35, V3

[!include [banner](../includes/psa-now-project-operations.md)]

We're pleased to announce the latest update for the Microsoft Dynamics 365 Project Service Automation app. This release includes some important improvements to quality, performance, and usability. It's compatible with Dynamics 365 9.x. To update to this release, visit the Admin Center for Dynamics 365 online solutions page, and install the update. For more information, see [Install, update, or remove a preferred solution](/power-platform/admin/install-remove-preferred-solution).

This topic lists the features and fixes that are new or changed for Project Service Automation V3, Update Release 35. This version has a build number of V3.10.56.110 and is generally available through a self-update in September 2021.

## Update Release 35

### Bug fixes
The following issues have been fixed.

**Time and Expense**
- The Project Approver is experiencing read privilege error when approving expense entry with "Project Approver" role.
- The Project Approver is experiencing write privilege error on msdyn_projectapproval when canceling the approved time entry with "Project Approver" role.
- "Copy week" in a Time Entry in Dynamics 365 for phone - Project Resource Hub app module throws an error "...\OfficeProductivity_RibbonRules.js.map: HTTP error: status code 404, net::ERR_HTTP_RESPONSE_CODE_FAILURE".
- Retry policy automatically approves the entry that was previously rejected.
- Approval Sets subgrid incorrectly displays non-applicable ribbon actions.
- Project Task and Resource Role are missing icons on the Time Entry entity.
- When importing Resource Assignments, time entries are not imported with the correct duration for assignments created with manual mode tasks.
- Delete button is not found in Advanced Find for Time Entry records.
- "Save" Button is not present in Time entry information form and preventing a save when the form is closed.

**Project planning**
- Resource Assignment and Resource Reconciliation grids are not sorting grouped attributes alphabetically.
- Tasks cannot be created if date behavior is customized to "Date Only".

**Resource management**
- Users are experiencing overlayering issues when trying to associate the 'Resource Requirement Associated View' to a main form when the customer has both Field Service and Project Service Automation installed.
- From the Team Member Quick Create, double clicking save prevents creation of the resource requirement.

**Sales**
- An exception is thrown when deleting a task associated to a won quote.

