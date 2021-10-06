---
title: What's new or changed in Project Service Automation Update Release 36, V3
description: This topic lists the features and fixes that are available in Microsoft Dynamics 365 Project Service Automation Update Release 36, V3.
author: ruhercul
ms.custom: dyn365-projectservice
ms.date: 10/03/A
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

# What's new or changed in Project Service Automation Update Release 36, V3

[!include [banner](../includes/psa-now-project-operations.md)]

We're pleased to announce the latest update for the Microsoft Dynamics 365 Project Service Automation app. This release includes some important improvements to quality, performance, and usability. It's compatible with Dynamics 365 9.x. To update to this release, visit the Admin Center for Dynamics 365 online solutions page, and install the update. For more information, see [Install, update, or remove a preferred solution](/power-platform/admin/install-remove-preferred-solution).

This topic lists the features and fixes that are new or changed for Project Service Automation Update Release 36, V3. This version has a build number of V3.10.57.152 and is generally available through a self-update in October 2021.

## Update Release 36

### Bug fixes

The following issues have been fixed.

**General**
- "Default Work Hour Template" string incorrectly translated on the Project Parameter form.
- Async plugins do not correcty handled exceptions related to the SharedVariableService.

**Time and Expense**
- The incorrect error is thrown when cancelling Project Approvals in scenarios where journal lines are missing or the user does not have the correct privileges to read journal lines.
- Users are unable to cancel an approval when an expense or time entry has more than one associated project approval.
- "Absence" and "Vacation" are incorrectly translated for Chinese language in a lookup on the time entry quick create form.


**Resource management**

- User are unable to search for resources in Schedule Assistant when view mode is set to Day, Week or month.
- Generic resources are incorrectly allowed to have empty position names. 
- Closing a contract as lost does not cancel future bookings.


**Sales**

- When an environment has a large volume of products, performanc degrades in the materials estimate grid.
- When creating a project from a template, the project currrency is not defaulted to respect the Project Manager's contracting unit.
- Actual amounts do not always match what is reflected on the project due or become negative in specific recall scenarios.
- Associating a project created from project template to a contract line throws an exception.
- Users incorrectly have the ability to delete a contract line with "Ready to invoice"/ "Invoice Created" milestone.
- Quote Line Detail chargeability is set incorrectly when Task Based Billing is enabled for the Quote Line in scenarios when estimates are imported from project.
- when adding a fixed pricing billing milestone, the milestone is not being reflected in the milestone subgrid until the form is refreshed.
- Null Reference Exception is generated when creating a Project contract when quote name is null.
- Manual mode tasks where the project currrency is different from the resource's currency result in incorrect price estimates.
- Users are unable to recall a transaction that has been successfully corrected by a corrective invoice.
- Deactivated transaction categories appear in the expense estimates grid.



