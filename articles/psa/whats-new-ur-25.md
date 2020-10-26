---
title: What's new or changed in Project Service Automation Update Release 25, V3
description: This topic lists the features and fixes that are available in Project Service Automation Update Release 25, V3.
author: ruhercul
manager: kfend
ms.service: dynamics-365-customerservice
ms.custom: dyn365-projectservice
ms.date: 10/26/2020
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

# What's new or changed in Project Service Automation Update Release 25, V3

We’re pleased to announce the latest update for the Project Service Automation application for Dynamics 365. This release includes some important improvements to quality, performance, and usability. This release is compatible with Dynamics 365 9.x. To update to this release, visit the Admin Center for Dynamics 365 online solutions page to install the update. For more information, see [Install, update, or remove a preferred solution](https://docs.microsoft.com/power-platform/admin/install-remove-preferred-solution).

This topic lists the features and fixes that are new or changed for Project Service Automation V3, Update Release 25 This version has a build number of V 3.10.43.64 and is generally available through a self-update in October 2020.

## Update Release 25

### Bug fixes

**Time and Expense**

The following issues have been fixed:

- Time entry chart showing additional data based on retrieving too large of an interval.
- Support the ability display two or more react grids on the **Project** form.
- Correct rounding and exchange rate discrepancies that resulted in an incorrect planned cost in the project tracking grid.
- **Not Ready to Invoice** on the **Time and Material Billing Backlog** doesn't clear the billing status.
- Provided validation to address the ability to assign a task past the calendar end date which results in a failed resource assignment.
- Added package deployer code to skip the Universal Resource Scheduling (URS) patch import if a higher version patch already exists.
- Correct mislabeled price buttons on the **Role Price** and **Catalog Items** tab.
- Improved error handling to address the Null Reference Exception generated from the following:

    - **PreValidateProjectTaskCreate** when a project task is created without an associated project
    - **PostProjectTeamMemberDelete** plug-in
    - **PreValidateProjectTeamMemberCreate** plug-in
    - **PreProjectTeamMemberCreate** plug-in
    - **PreValidateProjectTaskDelete** plug-in
    - **Copy Project: Estimates HelperResource Management**

The following issues have been fixed:

-   TBD

**Project Management**

The following issues have been fixed:

-   TBD

**Sales**

The following issues have been fixed:

-   TBD
