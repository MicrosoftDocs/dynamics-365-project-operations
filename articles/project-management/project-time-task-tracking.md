---
title: Project time task tracking
description: Learn how to configure Project time task tracking in Dynamics 365 Project Operations for real-time or delayed updates to improve stability and performance.
author: abriccetti
ms.date: 01/30/2026
ms.topic: how-to
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak
ms.author: abriccetti
---

# Project time task tracking

[!INCLUDE[banner](../includes/banner.md)]

_**Applies To:** Project Operations Integrated with ERP, Project Operations Core_

Microsoft Dynamics 365 Project Operations lets you configure updates to the **Project task time tracking** fields for synchronization to Microsoft Project for the Web either in real time (the default behavior) or through delayed update. When you select **Delayed update**, these updates occur only when a new project session starts. The update happens when the user navigates to the **Tasks** tab on a project entity.

The **Delayed update** setting provides stability or performance improvements in two main scenarios:

- **Bulk time entry approval** – Scenarios where many time entries on project tasks are approved at one time. For example, a project manager approves 1,000 time entries at the end of the month. If you select **Real-time update**, these requests saturate the queue of updates to Project for the Web. This saturation can cause instability and performance problems for other operations that also update Project for the Web.
- **Bulk new project creation** – Bulk project creation scenarios that use CopyProjectV3 or CopyProjectV4. When the work breakdown structure (WBS) is created on the new project, multiple updates are made to the time tracking fields for these new project tasks. If you select **Real-time update**, each newly created project makes multiple calls to Project for the Web. The **Delayed update** setting delays these calls and meaningfully improves project creation performance in these scenarios.

## Project task time tracking options

| Value            | Behavior |
|------------------|----------|
| Null             | The behavior is the same as the behavior when **Real-time update** is selected. |
| **Delayed update**   | **Remaining Effort**, **Effort Completed**, and **Effort Estimate at Complete** aren't updated with time that's approved on any task until a Project for the Web session is opened. |
| **Real-time update** | Approved time that's logged against a task updates, in real time, **Remaining Effort**, **Effort Completed**, and **Effort Estimate at Complete** on that task and any tasks above it in its hierarchy. |

Details on the **Project actual values tracking** feature are available. For more information, see [Status summary fields](/dynamics365/project-operations/project-management/understand-project-status#status-summary-fields).

[!INCLUDE[footer-include](../includes/footer-banner.md)]
