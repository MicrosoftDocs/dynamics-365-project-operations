---
title: What's new or changed in Project Service Automation Update Release 13, V3
description: This article provides information about what's new in Project Service Automation Update Release 13, V3.
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


# Project Service Automation Update Release 13, V3

[!include [banner](../includes/psa-now-project-operations.md)]

We’re pleased to announce the latest update for the Dynamics 365 Project Service Automation (PSA) application. This release includes some important improvements to quality, performance, and usability. This release is compatible with Dynamics 365 9.x. To update to this release, visit the Admin Center for Dynamics 365 online, and go to the solutions page to install the update. For more information, see [Install, update, or remove a preferred solution](/power-platform/admin/install-remove-preferred-solution).

This article lists the features and fixes that are new or changed for Project Service Automation V3, Update Release 13. This version has a build number of V3.10.3.18 and is available on the following schedule:

- **General availability (self-update):** November 2019
- **Auto-update:** December 2019


## Update Release 13 

### Bug fixes

- Time and Expense

     - Fixed: Search functionality on the **Expense approval** page does not work when searching by expense purpose.

- Resource Management

     - Fixed: Numbers in the reconciliation have been updated to be right justified.
     - Fixed: Named Resources can't be assigned to tasks through the **Schedule** tab.

- Project Management

     - Fixed: Null reference exception when assigning team member when the **TransactionType** is missing setup information for **Unit** and **DefaultGroup**.

- Sales

     - Fixed: Duplicate transaction type records return an error when role price records are created.
     - Fixed: Extra buttons for **New Opportunity**, **Quote**, **Order Line**, and **Add Product** are visible in commands for Opportunities, Quotes, Order Products, and the project-based Lines subgrid.




[!INCLUDE[footer-include](../includes/footer-banner.md)]
