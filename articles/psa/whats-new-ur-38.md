---
title: What's new or changed in Project Service Automation Update Release 38, V3
description: This topic lists the features and fixes that are available in Microsoft Dynamics 365 Project Service Automation Update Release 38, V3.
author: ruhercul
ms.custom: dyn365-projectservice
ms.date: 12/06/2021
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

The following issues have been fixed.

**Time and Expense**
- An exception when the length of approval set logs exceeds 100,000.
- Users are unable to access the **Time Entry** grid from The **Time Entry** main page.
- The **Time Entry Import** dialog box doesn't display any text when there are no items eligible for import.
- Users are able to create approval sets with the **Target Status** set to **Unknown**.

**Project Management**
- Contours aren't displayed correctly in resource assignments for UTC(+09:30) and UTC(+10:00) when daylight savings time starts.
- The work breakdown structure **Additional Column** drop-down list is hidden in some locales.
- The date picker for the the calendar control on the **Project Task** grid isn't correctly localized for Chinese.

**Sales**
- **Contract Performance** and **Project Actual Cost** don't match when bookable resources with different contracting units and currencies submit time entries.
- Custom workflow to auto-confirm invoices fails with the message, **Microsoft.Xrm.Sdk.InvalidPluginExecutionException Message: Invalid invoice status** when they're imported as a managed soultion.
- When **Root** is selected as the summarization option and the project has estimates from a mix of transactions classes, such as a combination of time, expense, and material estimates, the system summarizes across transaction classes as a single fee line.
- In scenarios where an expense line is added before a contract line is associated with a project, the **Update Price** field doesn't default the correct pricing.
- Negative sales amounts aren't allowed on **Project** and **Task** entities.






