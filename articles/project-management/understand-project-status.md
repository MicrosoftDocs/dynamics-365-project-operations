---
title: Understand project status
description: This topic provides information about the status assigned to projects in Dynamics 365 Project Operations. 
author: ruhercul
ms.date: 10/01/2020
ms.topic: article
ms.reviewer: johnmichalak
ms.author: ruhercul
---

# Understand project status

_**Applies To:** Project Operations for resource/non-stocked based scenarios, Lite deployment - deal to proforma invoicing_


The **Status** section on the **Project Entity** page provides a summary of a project's health based upon cost and effort.


## Status summary fields

- The **Overall project status** field is an editable field that shows the overall status of the project. This field uses color-coding, such as green, yellow, and red, to indicate increasing risk. 
- The **Comments** field lets the project manager enter specific comments about the status. 
- The **Status updated on** field isn't editable. The value in this field is a timestamp that indicates when the status was last updated.
- The **Schedule performance** and **Cost performance** fields are set from the tracking grid. When the schedule and cost variance for the root node in the **Effort tracking** view are positive, these fields are updated to **Ahead**. When the schedule and cost variance for the root node are negative, these fields are set to **Behind**.


[!INCLUDE[footer-include](../includes/footer-banner.md)]