---
title: What's new or changed in Project Service Automation Update Release 39, V3
description: This topic lists the features and fixes that are available in Microsoft Dynamics 365 Project Service Automation Update Release 39, V3.
author: ruhercul
ms.custom: dyn365-projectservice
ms.date: 01/19/2022
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

This topic lists the features and fixes that are new or changed for Project Service Automation Update Release 39, V3. This version has a build number of V3.10.59.117 and is generally available through a self-update in January 2022.

## Update Release 39

### Bug fixes

The following issues have been fixed.

**General**

- Several improvements have been made to the site map for Arabic translation.

**Project Management**

- An exception is thrown when changing the project manager on a project to a user who is already a team member.

**Sales**

- Owner of the **Project contract price list** is incorrect when created automatically. 
- Price list date effectivity is not honored on price lists applied to the project parameter.
- Contracting unit can be incorrectly defaulted when editing two separate quotes.
