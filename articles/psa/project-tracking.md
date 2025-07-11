---
title: Project progress and cost consumption
description: This article provides information about tracking project progress and cost consumption.
author: ruhercul
ms.custom: 
  - dyn365-projectservice
  - evergreen
ms.date: 07/07/2025
ms.update-cycle: 1095-days
ms.topic: article
ms.author: ruhercul
audience: Admin
search.audienceType: 
  - admin
  - customizer
  - enduser
ms.reviewer: johnmichalak
---
    
# Project progress and cost consumption

[!include [banner](../includes/psa-now-project-operations.md)]

[!INCLUDE[cc-applies-to-psa-app-3.x](../includes/cc-applies-to-psa-app-3x.md)]

The need to track progress against a schedule varies by industry. Some industries track at a granular level, whereas other industries track at a higher level. This article shows how to schedule in order to meet your organization's requirements.

## Effort tracking view

The **Effort tracking** view tracks the progress of tasks in the schedule. It compares the actual effort hours spent on a task to the task's planned effort hours. Project Service Automation uses the following formulas to calculate the tracking metrics:

Initially on the task creation: Planned cost will be set to the Estimated cost at complete. Once Actuals are recorded on the task, the following will be calculation on the Tracking view for Effort

- Progress percentage = Actual effort spent to date ÷ Estimate at complete (EAC) 
- Estimate to complete (ETC) = Estimate at complete (EAC)  – Actual effort spent to date 
- EAC = Remaining effort + Actual effort spent to date 
- Projected effort variance = Planned effort – EAC

Project Service Automation shows a projection of the effort variance on the task. If the EAC is more than the planned effort, the task is projected to take more time than was originally planned. Therefore, it's behind schedule. If the EAC is less than the planned effort, the task is projected to take less time than was originally planned. Therefore, it's ahead of schedule.

## Reprojecting effort

It's common for a project manager to revise the original estimates on a task. Project reprojections are a project manager's perception of estimates, given the current state of a project. However, we don't recommend that project managers change the baseline numbers, because the project baseline represents the established source of truth for the project's schedule and cost estimate, and all project stakeholders have agreed to it.

There are two ways that a project manager can reproject effort on tasks:

- Override the default ETC with a new estimate of the actual remaining effort on the task. 
- Override the default progress percentage with a new estimate of the true progress on the task.

Each of these approaches cause a recalculation of the task's ETC, EAC, and progress percentage, and the projected effort variance on a task. The EAC, ETC, and progress percentage on the summary tasks are also recalculated, and produce a new projection of effort variance.

## Reprojection of effort on summary tasks

Effort on summary tasks or container tasks can be reprojected. Regardless of whether the user reprojects by using the remaining effort or the progress percentage on the summary tasks, the following set of calculations begins:

- The EAC, ETC, and progress percentage on the task are calculated.
- The new EAC is distributed down to the child tasks in the same proportion as the original EAC was on the task.
- The new EAC on each of the individual tasks down to the leaf node tasks is calculated. 
- The affected child tasks down to the leaf nodes have their ETC and progress percentage recalculated based on the EAC value. This results in a new projection for the effort variance of the task. 
- The EACs of the summary tasks all the way to the root node are recalculated.

### Cost tracking view 

The **Cost tracking** view compares the actual cost that was spent on a task to the planned cost. 

> [!NOTE]
> This view shows only labor costs and doesn’t include costs from the expense estimates. 

Project Service Automation uses the following formulas to calculate the tracking metrics:

When a task is created, the planned cost is equal to the estimated cost at complete. After actuals are recorded on the task, the following is calculated on the **Tracking** view for cost:

 - Percentage of cost consumed = Actual cost spent to date ÷ Estimated cost at complete for the task
 - Cost to complete (CTC) = Estimated cost at complete – Actual cost spent to date
 - Estimated cost at complete = CTC + Actual cost spent to date
 - Projected cost variance = Planned cost – Estimated cost at complete

A projection of the cost variance is shown on the task. If the estimated cost at complete is more than the planned cost, the task is projected to cost more than was originally planned. Therefore, it's trending over budget. If the Estimated cost at complete is less than the planned cost, the task is projected to cost less than was originally planned and is trending under budget.

## Project manager’s reprojection of cost

When effort is reprojected, the CTC, Estimated cost at complete, percentage of cost consumed, and projected cost variance are all recalculated in the **Cost tracking** view.

## Project status summary

Tracking data in the **Effort tracking** and **Cost tracking** views shows the progress and cost consumption at the project root node, summary tasks, and leaf node tasks levels. The **Status** section on the **Project entity** page shows a summary of project-level status.

## Status summary fields

The **Overall project status** field is an editable field that shows the overall status of the project. It uses color-coding, such as green, yellow, and red, to indicate increasing risk. The **Comments** field lets the project manager enter specific comments about the status. The **Status updated on** field is not editable and the value is a timestamp that indicates when the status was last updated.

The **Schedule performance** and **Cost performance** fields are set from the tracking date. When the schedule and cost variance for the root node in the **Effort tracking** view are positive, you can set these fields to **Ahead**. When the schedule and cost variance for the root node are negative, you can set them to **Behind**.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
