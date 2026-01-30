---
title: Fixed price revenue estimate projects
description: Learn how to manage fixed price revenue estimate projects in Dynamics 365 Project Operations. Discover key steps for reviewing and updating project details.
author: sigitac
ms.date: 01/30/2026
ms.topic: concept-article
ms.reviewer: johnmichalak
ms.author: sigitac
---

# Fixed price revenue estimate projects

[!INCLUDE[banner](../includes/banner.md)]

 > [!NOTE]
   > In a recent product update, the **Update labels for revenue recognition and related forms and processes in Project Operations** feature renamed estimates to revenue recognition. Depending on whether the feature is enabled, terminology might reference either estimate or revenue recognition.

_**Applies To:** Project Operations Integrated with ERP_

When you create a project contract line with the following attributes in Dynamics 365 Project Operations on Microsoft Dataverse, the system automatically creates a fixed price revenue estimate project. The information in this project is based on the following attributes:

- A fixed price billing method.
- An associated project.
- At least one milestone defined on the **Invoice schedule** tab on the **Project contract line** page.

## Review fixed price revenue estimates projects

To review fixed price revenue estimates projects, complete the following steps:

1. In the Dynamics 365 Finance environment, go to **Projects management and accounting** > **Projects** > **Fixed price revenue estimate projects**.
1. Select the project that you want to view and double-click the **Estimate project ID** to open the record and review the details of the project.
1. Expand the **Project** tab. You see one project in the **Selected projects** grid. The system uses this project as the default project because it's the project associated to the project contract line.
1. To change the association, select additional projects and add them to the **Selected projects** grid. If you select multiple projects in this grid, the project percentage completion and revenue estimates are calculated together for all of the selected projects.

  You can set the project cost, revenue profile, cost template, and the period code manually. If you don't set these values manually, the values default during the first estimate calculation for the project by using the rules configured for project cost and revenue profiles.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
