---
title: Understand project status
description: This article provides information about the status assigned to projects in Dynamics 365 Project Operations. 
author: ruhercul
ms.date: 10/16/2023
ms.topic: concept-article
ms.reviewer: johnmichalak
ms.author: ruhercul
---

# Understand project status

[!INCLUDE[banner](../includes/banner.md)]

_**Applies To:** Project Operations Integrated with ERP, Project Operations Core_


The **Status** section on the **Project Entity** page provides a summary of a project's health based upon cost and effort.


## Status summary fields

- The **Overall project status** field is an editable field that shows the overall status of the project. This field uses color-coding, such as green, yellow, and red, to indicate increasing risk. 
- The **Comments** field lets the project manager enter specific comments about the status. 
- The **Status updated on** field isn't editable. The value in this field is a timestamp that indicates when the status was last updated.
- The **Schedule performance** and **Cost performance** fields are set from the tracking grid. When the schedule and cost variance for the root node in the **Effort tracking** view are positive, these fields are updated to **Ahead**. When the schedule and cost variance for the root node are negative, these fields are set to **Behind**.

**Project task time tracking** - In **Settings** > **Parameters**, you can use this field to set project tasks time as **Real-time update** or **Delayed update**. During data migration, the **Delayed updated** setting is recommended to enable the best performance.

**Project actual values tracking** - In **Settings** > **Parameters**, you can use this field to set project actual values as **Real-time update** or **On Demand update**. If you select **Real time update**, factoring the actuals in total takes time. The status of project is real time, and performance might be slow. Whereas the **On-demand update** increases performance and this setting is recommended during data migration. After the data migration is complete, you can set the update to **Real time** and select the **Refresh Project Totals** button.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
