---
title: What's new or changed in Project Service Automation Update Release 17, V3
description: This article lists the features and fixes that are available in Project Service Automation Update Release 17, V3.
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


# Project Service Automation Update Release 17, V3

[!include [banner](../includes/psa-now-project-operations.md)]

We’re pleased to announce the latest update for the Project Service Automation application for Dynamics 365. This release includes some important improvements to quality, performance, and usability.  This release is compatible with Dynamics 365 9.x. To update to this release, visit the Admin Center for Dynamics 365 online, solutions page to install the update. For more information, see [Install, update, or remove a preferred solution](/power-platform/admin/install-remove-preferred-solution).

This article lists the features and fixes that are new or changed for PSA V3, Update Release 17. This version has a build number of V3.10.6.34 and is generally available through a self-update in March 2020.


## Update Release 17

### Bug fixes

**General**

- Fixed: Update Project Service Automation to enforce Team Member licenses (Project Resource Hub will include Team Member Service plan metadata 3.x)
 
**Time and Expense**

- Fixed: It is not possible to change an expense estimate from a non-zero price to zero (0). The change is ignored.

**Project Management**

- Fixed: A check for null values has been added on a team member's position name.
- Fixed: **msdyn_userresourceid** field on the **msdyn_resourceassignment** entity has been deprecated.
- Fixed: Upgrade from 2.x to 3.x now handles empty effort contours on task assignments.

**Sales**

- Fixed: **Invoice.PreValidateInvoiceUpdate** now handles the scenario of reassigning record owners properly.
- Fixed: When the transaction class is **Time**, **UnitGroup** is non-editable for all entities including, **QuoteLineDetails**, **JournalLine**, **InvoiceLineDetail**, and **ContractLineDetails**. However, **Unit** is non-editable only for **JournalLine** and **InvoiceLineDetails**.




[!INCLUDE[footer-include](../includes/footer-banner.md)]
