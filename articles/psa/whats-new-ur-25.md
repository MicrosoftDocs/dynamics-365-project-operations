---
title: What's new or changed in Project Service Automation Update Release 25, V3
description: This article lists the features and fixes that are available in Project Service Automation Update Release 25, V3.
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

# What's new or changed in Project Service Automation Update Release 25, V3

[!include [banner](../includes/psa-now-project-operations.md)]

We’re pleased to announce the latest update for the Project Service Automation application for Dynamics 365. This release includes some important improvements to quality, performance, and usability. This release is compatible with Dynamics 365 9.x. To update to this release, visit the Admin Center for Dynamics 365 online solutions page to install the update. For more information, see [Install, update, or remove a preferred solution](/power-platform/admin/install-remove-preferred-solution).

This article lists the features and fixes that are new or changed for Project Service Automation V3, Update Release 25 This version has a build number of V 3.10.43.76 and is generally available through a self-update in October 2020.

## Update Release 25

### Bug fixes

**Time and Expense**

The following issue has been fixed:

- Time entry chart showing additional data based on too large of an interval being retrieved.

**Resource Management**

The following issue has been fixed:

- Added package deployer code to skip the Universal Resource Scheduling patch import if a higher version patch already exists.

**Project Management**

The following issues have been fixed:

- Corrected rounding and exchange rate discrepancies resulting in incorrect planned cost in the project tracking grid.
- Support the ability to display two or more react grids on the **Project** form.
- Provided validation to address the ability to assign a task past the calendar end date, which results in a failed resource assignment.
- Improved error handling to address Null Reference Exception generated from the following:

    - **PreValidateProjectTeamMemberCreate** plug-in
    - **PreValidateProjectTaskCreate** when a project task is created without an associated project
    - **PreProjectTeamMemberCreate** plug-in
    - **PostProjectTeamMemberDelete** plug-in
    - **PreValidateProjectTaskDelete** plug-in

**Sales**

The following issues have been fixed:

- Improved error handling to address Null Reference Exceptions generated from **Copy Project: Estimates HelperResource Management**.
- **Not ready to Invoice** on a **Time and Material Billing Backlog** doesn't clear the billing status.
- Corrected mislabeled **Prices** buttons on the **Role Price** and **Catalog Items** tab.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
