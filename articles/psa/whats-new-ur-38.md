---
title: What's new or changed in Project Service Automation Update Release 38, V3
description: This article lists the features and fixes that are available in Microsoft Dynamics 365 Project Service Automation Update Release 38, V3.
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

# What's new or changed in Project Service Automation Update Release 38, V3

[!include [banner](../includes/psa-now-project-operations.md)]

We're pleased to announce the latest update for the Microsoft Dynamics 365 Project Service Automation app. This release includes some important improvements to quality, performance, and usability. It's compatible with Dynamics 365 9.x. To update to this release, visit the Admin Center for Dynamics 365 online solutions page, and install the update. For more information, see [Install, update, or remove a preferred solution](/power-platform/admin/install-remove-preferred-solution).

This article lists the features and fixes that are new or changed for Project Service Automation Update Release 38, V3. This version has a build number of V3.10.59.117 and is generally available through a self-update in December 2021.

## Update Release 38

### Bug fixes

The following issues have been fixed.

**Time and Expense**

- An exception occurs when the length of approval set logs exceeds 100,000 records.
- Users can't access the **Time Entry** grid from The **Time Entry** main page.
- The **Time Entry Import** dialog box doesn't show any text when no items are eligible for import.
- Users can create approval sets where the **Target Status** field is set to **Unknown**.

**Project Management**

- Contours aren't shown correctly in resource assignments for UTC(+09:30) and UTC(+10:00) when daylight saving time starts.
- The **Additional Column** field for work breakdown structures is hidden in some locales.
- The date picker for the calendar control in the **Project Task** grid isn't correctly localized for Chinese.

**Sales**

- **Contract Performance** and **Project Actual Cost** values don't match when bookable resources that have different contracting units and currencies submit time entries.
- A custom workflow to automatically confirm invoices fails when the invoices are imported as a managed solution. The following message is shown: "Microsoft.Xrm.Sdk.InvalidPluginExecutionException Message: Invalid invoice status."
- When **Root** is selected as the summarization option, and the project has estimates from a mixture of transactions classes (for example, a combination of time, expense, and material estimates), the system summarizes across transaction classes as a single fee line.
- In scenarios where an expense line is added before a contract line is associated with a project, the correct pricing isn't entered as a default value in the **Update Price** field.
- Negative sales amounts aren't allowed on **Project** and **Task** entities.
