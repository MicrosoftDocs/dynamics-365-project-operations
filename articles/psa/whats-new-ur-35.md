---
title: What's new or changed in Project Service Automation Update Release 35, V3
description: This article lists the features and fixes that are available in Microsoft Dynamics 365 Project Service Automation Update Release 35, V3.
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

# What's new or changed in Project Service Automation Update Release 35, V3

[!include [banner](../includes/psa-now-project-operations.md)]

We're pleased to announce the latest update for the Microsoft Dynamics 365 Project Service Automation app. This release includes some important improvements to quality, performance, and usability. It's compatible with Dynamics 365 9.x. To update to this release, visit the Admin Center for Dynamics 365 online solutions page, and install the update. For more information, see [Install, update, or remove a preferred solution](/power-platform/admin/install-remove-preferred-solution).

This article lists the features and fixes that are new or changed for Project Service Automation Update Release 35, V3. This version has a build number of V3.10.56.110 and is generally available through a self-update in September 2021.

## Update Release 35

### Bug fixes

The following issues have been fixed.

**Time and Expense**

- The project approver receives a read privilege error when they approve expense entries with a **Project Approver** role.
- The project approver receives a write privilege error on **msdyn_projectapproval** when they cancel an approved time entry with a **Project Approver** role.
- When you select **Copy week** in a time entry in the Dynamics 365 for phone - Project Resource Hub app module, the following error occurs: "...\OfficeProductivity_RibbonRules.js.map: HTTP error: status code 404, net::ERR_HTTP_RESPONSE_CODE_FAILURE."
- The **Retry** policy automatically approves entries that were previously rejected.
- The **Approval Sets** subgrid shows non-applicable ribbon actions.
- Icons are missing for **Project Task** and **Resource Role** on the **Time Entry** entity.
- When you import resource assignments, imported time entries don't have the correct duration for assignments that were created through manual mode tasks.
- **Delete** is missing from the **Advanced Find for Time Entry records** page.
- **Save** is missing from the **Time entry information** page. This issue prevents changes from being saved when the page is closed.

**Project planning**

- The **Resource Assignment** and **Resource Reconciliation** grids don't sort grouped attributes alphabetically.
- Tasks can't be created if the date behavior is customized to **Date Only**.

**Resource management**

- If both Dynamics 365 Field Service and Project Service Automation are installed, overlayering issues occur when **Resource Requirement Associated View** is associated with a main page.
- Double-clicking **Save** in the **Team Member Quick Create** dialog box prevents the resource requirement from being created.

**Sales**

- An exception is thrown if you delete a task that is associated with a quotation that has a status of **Won**.
