---
# required metadata

title: Project effort tracking 
description: This article provides information about how to track project effort and progress of work.
author: abriccetti
ms.author: abriccetti
ms.date: 05/17/2024
ms.topic: overview
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak

---

# Project effort tracking

_**Applies To:** Project Operations Integrated with ERP, Core deployment - deal to proforma invoicing_

The need to track progress against a schedule varies by industry. Some industries track at a granular level, where other industries track at a higher level. The tracking tab on the project entity allows customers to view the status of their project based on effort or cost.

## Effort tracking view

The **Effort tracking** view tracks the progress of tasks in the schedule by comparing the actual effort hours spent on a task to the task's planned effort hours. Dynamics 365 Project Operations uses the following formulas to calculate the tracking metrics:

- **Progress percentage**: Actual effort spent to date ÷ Estimate at complete (EAC) 
- **Remaining Effort**: Estimated effort at complete – Actual effort spent to date 
- **EAC**: Remaining effort + Actual effort spent to date 
- **Projected effort variance**: Planned effort – EAC

Project Operations shows a projection of the effort variance on the task. If the EAC is more than the planned effort, the task is projected to take more time than was originally planned and is behind schedule. If the EAC is less than the planned effort, the task is projected to take less time than was originally planned and is ahead schedule.

## Reprojecting effort on leaf node tasks

Project managers often revise the original estimates on a task. Project reprojections are a project manager's perception of estimates, given the current state of a project. However, we don't recommend that project managers change the planned effort numbers. This is because the project planned effort represents the established source of truth for the project schedule and cost estimate, and all project stakeholders have agreed to it.

A project manager can reproject effort on tasks by updating the default **Remaining Effort** with a new estimate on the task. This update causes a recalculation of the task's estimate at complete (EAC), progress percentage, and the projected effort variance on a task. The EAC, ETC, and progress percentage on the summary tasks are also recalculated and produce a new projection of effort variance.

## Reprojection of effort on summary tasks

Effort on summary tasks or container tasks can be reprojected. Project managers can update remaining effort on the summary tasks. Updating the remaining effort triggers the following set of calculations in the application:

- The EAC and progress percentage on the task are calculated.
- The new EAC is distributed down to the child tasks in the same proportion as the original EAC was on the task.
- The new EAC on each of the individual tasks down to the leaf node tasks is calculated. 
- The affected child tasks down to the leaf nodes have their remaining effort and progress percentage recalculated based on the EAC value. This results in a new projection for the effort variance of the task. 
- The EACs of the summary tasks all the way to the root node are recalculated.
- The approved effort on a summary task is the sum of the approved effort on all child tasks plus the approved effort on the summary task.
- The remaining effort on the summary task is the sum of the remaining effort on all child tasks minus the approved effort on the summary task.

## Project status summary

Tracking data in the **Effort tracking** and **Cost tracking** views shows the progress and cost consumption at the project root node, summary tasks, and leaf node tasks levels. The **Status** section on the **Project entity** page shows a summary of project-level status.

## Status summary fields

The **Overall project status** field is an editable field that shows the overall status of the project. It uses color-coding, such as green, yellow, and red, to indicate increasing risk. The **Comments** field lets the project manager enter specific comments about the status. The **Status updated on** field is not editable and the value is a timestamp that indicates when the status was last updated.

The **Schedule performance** and **Cost performance** fields are set from the tracking date. When the schedule and cost variance for the root node in the **Effort tracking** view are positive, you can set these fields to **Ahead**. When the schedule and cost variance for the root node are negative, you can set them to **Behind**.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
