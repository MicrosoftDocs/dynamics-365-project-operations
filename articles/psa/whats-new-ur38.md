---
title: What's new or changed in Project Service Automation Update Release 38, V3
description: This topic lists the features and fixes that are available in Microsoft Dynamics 365 Project Service Automation Update Release 38, V3.
author: ruhercul
ms.custom: dyn365-projectservice
ms.date: 12/02/2021
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

# What's new or changed in Project Service Automation Update Release 38, V3

[!include [banner](../includes/psa-now-project-operations.md)]

We're pleased to announce the latest update for the Microsoft Dynamics 365 Project Service Automation app. This release includes some important improvements to quality, performance, and usability. It's compatible with Dynamics 365 9.x. To update to this release, visit the Admin Center for Dynamics 365 online solutions page, and install the update. For more information, see [Install, update, or remove a preferred solution](/power-platform/admin/install-remove-preferred-solution).

This topic lists the features and fixes that are new or changed for Project Service Automation Update Release 38, V3. This version has a build number of V3.10.59.117 and is generally available through a self-update in December 2021.

## Update Release 38

### Bug fixes
the following features have been added.

The following issues have been fixed.

**Time and Expense**
- An exception when the length of approval set logs exceeds 100,000.
- Users are unable to access the time entry grid from time entry main form.
- Time Entry import dialog does not display any text when there are no items eligible for import.
- Users are able to create approval set with "target status" as "unknown"

**Project management**
- Contours are not displayed correctly in resource assignments for UTC(+09:30) and UTC(+10:00) when daylisght savings time starts.
- WBS Additional Column dropdown is hidden in some locales.
- The date picker for the the calendar Control on the project task grid is not correctly localized for Chinese.

**Sales**
- Contract Performance and Project Actual Cost do not match when bookable resources with different Contracting Units and currencies submit time entries.
- Custom workflow to auto-confirm invoices fails with message "Microsoft.Xrm.Sdk.InvalidPluginExecutionException Message: Invalid invoice status" when imported as managed soultion.
- When Root is selected as the summarization option and the project has estimates from a mix of transactions class ie. a combination time, expense and material estimates, the system summarizes across transaction classes as a single fee line.
- In scenarios where an expense line is added before a contract line has been associated with a project, Update Price does not correctly default the correct pricing.
- Negative sales amounts not allowed on Project and Task entities






