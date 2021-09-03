---
title: What's new or changed in Project Service Automation Update Release 35, V3
description: This topic lists the features and fixes that are available in Project Service Automation Update Release 35, V3.
author: ruhercul
ms.custom: dyn365-projectservice
ms.date: 09/03/2021
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
- The Project Approver receives a read privilege error when approving expense entries with a **Project Approver** role.
- The Project Approver receives a write privilege error on **msdyn_projectapproval** when canceling an approved time entry with a **Project Approver** role.
- When you select **Copy week** in a Time Entry in the Dynamics 365 for phone - Project Resource Hub app module, the following error occurs, "...\OfficeProductivity_RibbonRules.js.map: HTTP error: status code 404, net::ERR_HTTP_RESPONSE_CODE_FAILURE".
- The **Retry** policy automatically approves entries that were previously rejected.
- The **Approval Sets** subgrid displays non-applicable ribbon actions.
- **Project Task** and **Resource Role** are missing icons on the **Time Entry** entity.
- When you import resource assignments, time entries aren't imported with the correct duration for assignments that are created with manual mode tasks.
- **Delete** is missing from the **Advanced Find for Time Entry records**.
- **Save** is missing from the **Time entry information** page. This is preventing changes from being saved when the page is closed.

**Project planning**
- The **Resource Assignment** and **Resource Reconciliation** grids aren't sorting grouped attributes alphabetically.
- Tasks can't be created if the date behavior is customized to **Date Only**.

**Resource management**
- Overlayering issues occur when associating the **Resource Requirement Associated View** to a main page when both Dynamics 365 Field Service and Dynamics 365 Project Service Automation are installed.
- From the **Team Member Quick Create** dialog page, double-clicking **Save** prevents the resource requirement from being created.

**Sales**
- An exception is thrown when you delete a task associated to a quote with a status of **Won**.

