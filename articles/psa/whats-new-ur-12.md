---
title: What's new or changed in Project Service Automation Update Release 12, V3
description: This article provides information about what's new in Project Service Automation Update Release 12, V3.
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


# Project Service Automation Update Release 12, V3

[!include [banner](../includes/psa-now-project-operations.md)]

We’re pleased to announce the latest update for the Dynamics 365 Project Service Automation (PSA) application. This release includes some important improvements to quality, performance, and usability. This release is compatible with Dynamics 365 9.x. To update to this release, visit the Admin Center for Dynamics 365 online, and go to the solutions page to install the update. For more information, see [Install, update, or remove a preferred solution](/power-platform/admin/install-remove-preferred-solution).

This article lists the features and fixes that are new or changed for Project Service Automation V3, Update Release 12. This version has a build number of V3.10.2.34 and is generally available through a self-update in October 2019.

## Update Release 12

### Bug fixes

- Time and Expense

    - Fixed: Time entry error messaging has been updated with more relevant context.
    - Fixed: Time entry grid and schedule correctly displays the vertical scrollbar when required.
    - Fixed: Submitted expense and time entries can be approved.
    - Fixed: Cancel approval confirmation dialog message has been corrected to reflect the status of the approval when changed from **Approved** to **Submitted**.
    - Fixed: **Price**, **Unit**, and **Quantity** fields are now locked on the Expense record after it is has been approved.

- Project Management

    - Fixed: **New** action on **Team member** main form has been removed.
    - Fixed: Resource assignments have been updated to account for inaccurate rounding errors, which lead to a shift in a task’s end date.
    - Fixed: In the task grid, relevant server-side errors will be surfaced to the user.
    - Fixed: The team member’s name now renders in the task people picker instead of the position name.

- Resource Management

    - Fixed: Resource requirement details for projects created from a template now use the project calendar.
    - Fixed: Skills and competencies now default from role master data to the resource requirement created for that role.

- Sales

    - Fixed: Duplicate object IDs found on the **Contract main** form.
    - Fixed: Logic has been updated to make the **Quote Analysis** tab visible so that it displays the metadata setup of the tab.
    - Fixed: Accounting date on the actual record now comes from the date of the time/expense entry date and not the date of the approval.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
