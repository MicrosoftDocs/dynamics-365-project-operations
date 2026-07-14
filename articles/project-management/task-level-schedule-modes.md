---
title: Task-level schedule modes (preview)
description: Learn how to override the project scheduling mode on individual tasks to control how effort, duration, and units are calculated per task.
author: dishantpopli
ms.author: dishantpopli
ms.date: 06/03/2026
ms.topic: overview
ms.custom: bap-template
ms.reviewer: johnmichalak

---

# Task-level schedule modes (preview)

[!INCLUDE [banner](../includes/banner.md)]
[!INCLUDE [preview-banner](~/../shared-content/shared/preview-includes/preview-banner.md)]


_**Applies To:** Project Operations Integrated with ERP, Project Operations Core_

By default, every task in a project inherits the schedule mode set at the project level. Task-level schedule modes let you assign a different schedule mode to specific tasks, so the scheduling engine calculates effort, duration, and units according to the overridden mode for those tasks.

For example, a project might use **Fixed Duration** as its schedule mode, but a particular deliverable task requires that effort remains constant as resources are added or removed. You can set that task to **Fixed Effort** without affecting the rest of the project.

## How task-level schedule modes work

When you set a schedule mode on a task, the following behavior applies:

1. A task with no schedule mode override inherits the project-level schedule mode.
1. A task with an overridden schedule mode follows the scheduling calculation for the selected mode, independent of the project setting.
1. The overridden schedule mode is saved in both the MPP file and Dataverse.
1. Parent (summary) tasks always use **Fixed Duration**, regardless of the project or task-level schedule mode setting.

## Key behaviors

| Behavior | Detail |
| --- | --- |
| Default | Task with no override defaults to the project-level schedule mode. |
| Summary tasks | A summary task is always **Fixed Duration**. You can't change the schedule mode on a summary task. |
| Persistence | An overridden task schedule mode is saved in both the MPP file and Dataverse. |

## Set task-level schedule mode in the UI

Set the task-level schedule mode through the custom task details pane.

To set task-level schedule mode in the UI, follow these steps:

1. Open a project and go to the **Task grid**.
1. Select the information (**i**) icon next to the task you want to modify.
1. In the **Details: Project Operations** pane, find the **Task Schedule Mode** field.
1. Select the schedule mode you want to apply to the task.
1. Select **Save**.

> [!NOTE]
> Your organization must enable the custom task details pane. Learn more about setup instructions in [Customize task details pane](customize-task-details-pane.md).

## Set task-level schedule mode by using the Schedule API

You can set or update the task schedule mode programmatically through the Schedule API when you create or update tasks.

- Set the `msdyn_taskschedulemode` attribute on the Project Task entity to one of the five valid option values.
- The Schedule API validates the value. Invalid values, including `null`, are rejected with an error.
- Bulk updates on tasks that include a task schedule mode value are supported through the Schedule API.

| Schedule mode | Value to use in API |
| --- | --- |
| **Fixed Effort** | 192350000 |
| **Fixed Duration** | 192350001 |
| **Fixed Units** | 192350002 |
| **Fixed Duration Effort Driven** | 192350003 |
| **Fixed Units Effort Driven** | 192350004 |

> [!IMPORTANT]
> You can't set an invalid or `null` value for the task schedule mode through the Schedule API. The API returns an error if you attempt to do so.

## Copy and import behavior

Task-level schedule mode overrides follow specific rules during copy and import operations to preserve scheduling intent while adapting to the destination project.

### Copy a project

When you copy a project, the system preserves overridden task schedule modes on tasks. If the source task's schedule mode matches the source project's schedule mode (meaning no override was applied), the task's schedule mode defaults to the destination project's schedule mode.

| Source task schedule mode | Source project schedule mode | Destination behavior |
| --- | --- | --- |
| Different from source project | Any | Overridden value is preserved on the destination task. |
| Same as source project | Any | Task defaults to the destination project's schedule mode. |

### Copy a task

When you copy a task from one project to another, the system always copies the source task's schedule mode to the destination, regardless of the destination project's schedule mode.

> [!NOTE]
> This behavior differs from copy project. Copy task always carries the source task's schedule mode to the destination task.

### Import from MPP

When you import tasks from an MPP file, the system preserves overridden task schedule modes (task types). If the source project schedule mode equals the task schedule mode (no override), the task defaults to the destination project's schedule mode.

### Import tasks

When you import tasks between projects, the behavior follows the same rules as copy project and import from MPP:

- The system preserves overridden task schedule modes.
- The task where the schedule mode matches the source project's schedule mode defaults to the destination project's schedule mode.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
