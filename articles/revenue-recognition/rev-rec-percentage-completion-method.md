---
title: Fixed price revenue estimate projects 
description: This article provides information about fixed price revenue in projects.
author: sigitac
ms.date: 10/27/2023
ms.topic: concept-article
ms.reviewer: johnmichalak
ms.author: sigitac
---
# Fixed price revenue estimate projects 
 > [!NOTE]
   > Estimates have been renamed to revenue recognition in a recent product update with the **Update labels for revenue recognition and related forms and processes in Project Operations** feature. Terminology may reference either estimate or revenue recognition depending on if the feature is enabled.

_**Applies To:** Project Operations Integrated with ERP_

When you create a project contract line with the following attributes in Dynamics 365 Project Operations on Microsoft Dataverse, the system automatically creates a fixed price revenue estimate project. The information in this project is based on the following:

  - A fixed price billing method.
  - An associated project.
  - At least one milestone defined on the **Invoice schedule** tab on the **Project contract line** page.

## Review fixed price revenue estimates projects
To review fixed price revenue estimates projects, complete the following steps:

1. In the Dynamics 365 Finance environment, go to **Projects management and accounting** > **Projects** > **Fixed price revenue estimate projects**.
2. Select the project that you want to view and double-click the **Estimate project ID** to open the record and review the details of the project.
3. Expand the **Project** tab. You will see one project in the **Selected projects** grid. The system uses this as default project because it is the project associated to the project contract line. 
4. To change the association, select additional projects and add them to the **Selected projects** grid. If multiple projects are selected in this grid, the project percentage completion and revenue estimates are calculated together for of the all selected projects.

  Project cost, revenue profile, cost template, and the period code can be set manually. If they aren't set manually, the values default during the first estimate calculation for the project using the rules configured for project cost and revenue profiles.



[!INCLUDE[footer-include](../includes/footer-banner.md)]