---
title: Project time task tracking
description: This article provides information the Project time task tracking setting.
author: abriccetti
ms.date: 10/10/2023
ms.topic: how-to
ms.custom: bap-template
ms.reviewer: johnmichalak
ms.author: abriccetti
---

# Project time task tracking

_**Applies To:** Project Operations for resource/non-stocked based scenarios, Lite deployment - deal to proforma invoicing_

Microsoft Dynamics 365 Project Operations offers the ability for customers to configure updates on the **Project task time tracking** fields to sync to Microsoft Project for the Web in **Real-time** (default behavior) or **Delayed update**. When **Delayed update** is selected, these updates only happen when a new project session is started (this update occurs when the user navigates to the tasks tab on a project entity). 

There are two main scenarios when setting this field to **Delayed update** provides stability or performance improvements:

1. **Bulk Time Entry Approval** - In situations where there are many time entries on project tasks that are approved at once. For example, a project manager approves 1000 time entries at the end of the month. If **Real-time** update is selected, the queue of updates to Project for the Web gets saturated by these requests. This saturation can lead to instability and performance issues for other operations that also update Project for the Web.
1. **Bulk New Project Creation** - In bulk project creation scenarios using CopyProjectV3 or CopyProjectV4, when the work breakdown structure is created on the new project, there are multiple updates to the time tracking fields for these new project tasks. If real-time update is selected, this creates multiple calls to Project for the Web for each newly created project. Setting this feature to on-demand update delays these calls and meaningfully improves project creation performance in these scenarios.

## Project Task Time Tracking Options

| Value            | Behavior           |
|------------------|--------------------|
| Null             | When this value is null, the behavior is the same as Real-time update. 
| Delayed update   | Remaining Effort, Effort Completed, Effort Estimate at Complete aren't updated with time is approved on any task until a Project for the Web Session is opened. |
| Real-time update | Approved time logged against a task updates Remaining Effort, Effort Completed, Effort Estimate at Complete on that task and any tasks above it in its hierarchy in real-time. |
