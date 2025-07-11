---
title: What's new or changed in Project Service Automation Update Release 26, V3
description: This article lists the features and fixes that are available in Project Service Automation Update Release 26, V3.
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

# Project Service Automation Update Release 26, V3

[!include [banner](../includes/psa-now-project-operations.md)]

We’re pleased to announce the latest update for the Project Service Automation application for Dynamics 365. This release includes some important improvements to quality, performance, and usability. This release is compatible with Dynamics 365 9.x. To update to this release, visit the Admin Center for Dynamics 365 online solutions page to install the update. For more information, see [Install, update, or remove a preferred solution](/power-platform/admin/install-remove-preferred-solution).

This article lists the features and fixes that are new or changed for Project Service Automation Update Release 26, V3. This version has a build number of V3.10.44.59 and is generally available through a self-update in December 2020.

## Update Release 26

### Bug fixes

**Time and Expense**

The following issues have been fixed:

- Users are able to change the task on a time entry that has been approved/submitted.
- "Object Reference Not Set" error when saving time entry.
- Time entry import from resource assignments creates time entries with the incorrect DateTime values.
- When Project Service Automation and the Field Service app are both installed, the **New** button is displaying twice on the command bar for time entries in the Field Service app.
- **Allow Unit** and **Unit group** cells updates now work on the **Expense Estimates** grid.
- **Update Time Entry Edit** form includes **Timeline**.
- Time approval for non-project time entries blocks the system when searching for a project approver role.

**Resource Management**

The following issues have been fixed:

- Added validation in the **PostProjectCreate** plug-in to check for a primary requirement before creating one.
- **Project Team Member** quick create form throws a null reference exception if fields are removed from the form.
- Generate requirements for 12 hours over 1 year will fail.
- Improved error message null reference exception during resource requirement creation.

**Project Management**

The following issues have been fixed:

- Improved validation to address null reference exception generated in the **PreProjectUpdate** plug-in.
- Projects published by the Microsoft Project desktop add-in delete unassigned assignments.
- Added new validation when a task’s project reference is invalid due to null reference exception in **PreValidateProjectTaskUpdate** plug-in.
- Team Member grid does not show distinct assignments on the team member record.
- Added new validation and error messages due to null reference exception in **PreProjectTaskDelete** plug-in.

**Sales**

The following issues have been fixed:

- When selecting a project-based line in quote or contract, the **Suggestion** button should only be visible when selecting a product-based line associated with an existing product.
- Split **Create_Product** privilege from **Create_ProjectContract** privilege.
- Deleting an invoice line causes null reference failure on **MarkReadyToInvoiceForProductContractLineAfterDeletingInvoice**.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
