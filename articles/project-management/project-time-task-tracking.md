---
title: Project time task tracking
description: This article provides information about the Project time task tracking setting.
author: abriccetti
ms.date: 11/14/2023
ms.topic: how-to
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak
ms.author: abriccetti
---

# Project time task tracking

_**Applies To:** Project Operations Integrated with ERP, Project Operations Core_

Microsoft Dynamics 365 Project Operations lets customers configure updates to the **Project task time tracking** fields for synchronization to Microsoft Project for the Web either in real time (the default behavior) or through delayed update. When **Delayed update** is selected, these updates occur only when a new project session is started. (This update occurs when the user navigates to the **Tasks** tab on a project entity.)

There are two main scenarios where the **Delayed update** setting provides stability or performance improvements:

- **Bulk time entry approval** – Scenarios where many time entries on project tasks are approved at one time. For example, a project manager approves 1,000 time entries at the end of the month. If **Real-time update** is selected, the queue of updates to Project for the Web becomes saturated by these requests. This saturation can cause instability and performance issues for other operations that also update Project for the Web.
- **Bulk new project creation** – Bulk project creation scenarios that use CopyProjectV3 or CopyProjectV4. When the work breakdown structure (WBS) is created on the new project, multiple updates are made to the time tracking fields for these new project tasks. If **Real-time update** is selected, multiple calls to Project for the Web are created for each newly created project. The **Delayed update** setting delays these calls and meaningfully improves project creation performance in these scenarios.

## Project task time tracking options

| Value            | Behavior |
|------------------|----------|
| Null             | The behavior is the same as the behavior when **Real-time update** is selected. |
| **Delayed update**   | **Remaining Effort**, **Effort Completed**, and **Effort Estimate at Complete** aren't updated with time that's approved on any task until a Project for the Web session is opened. |
| **Real-time update** | Approved time that's logged against a task updates, in real time, **Remaining Effort**, **Effort Completed**, and **Effort Estimate at Complete** on that task and any tasks above it in its hierarchy. |

Details on the **Project actual values tracking** feature are available. For more information, see [Status summary fields](/dynamics365/project-operations/project-management/understand-project-status#status-summary-fields).
