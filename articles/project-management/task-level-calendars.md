---
title: Configure task-level calendar overrides
description: Configure task-level calendars in Project Operations to use task-specific working hours and control whether scheduling honors resource calendars.
author: dishantpopli
ms.author: dishantpopli
ms.reviewer: johnmichalak
ms.date: 11/23/2026
ms.topic: how-to
ms.custom:
  - bap-template

---

# Configure task-level calendar overrides

[!INCLUDE [banner](../includes/banner.md)]

***Applies To:** Project Operations Integrated with ERP, Project Operations Core*

Task-level calendars in Dynamics 365 Project Operations let you give individual tasks different working hours without changing the project's calendar. As a project manager, you can assign a work hour template to a task and separately control whether scheduling honors the calendars of its assigned resources. Task-level calendars are enabled by default and don't require a separate enablement step.

## Key concepts

- **Work hour template** - A reusable record that defines working hours.
- **Task Work Hour Template** - The field that assigns a work hour template to an individual task. Project Operations creates a task-specific calendar from the selected template.
- **Ignore Resource Calendar** - A separate task setting that controls whether scheduling honors the calendars of all resources assigned to the task. Its default value is **No**.

## How task-level calendar overrides work

The task template and resource-calendar setting work together. Assigning a template doesn't automatically ignore resource calendars.

| Task Work Hour Template | Ignore Resource Calendar | Calendars honored for scheduling |
| ----------------------- | ------------------------ | -------------------------------- |
| **Not assigned** | **No** | Project calendar and assigned resource calendars. |
| **Assigned** | **No** | Task calendar and assigned resource calendars. |
| **Not assigned** | **Yes** | Project calendar only. |
| **Assigned** | **Yes** | Task calendar only. |

For example, assigning a weekend work hour template doesn't by itself allow work outside an assigned resource's working hours. If that task must follow only the weekend task calendar, also set **Ignore Resource Calendar** to **Yes**.

When you select a different task template, Project Operations creates a new task-specific calendar from that template. Clearing the template removes the task-calendar override. The **Ignore Resource Calendar** setting still determines whether resource calendars are honored.

## Prerequisites

- You need permission to edit the project task and the relevant fields.
- To assign a task template, you need an existing work hour template with the working hours you want to use.

## Assign a work hour template to a task

Use this procedure to apply task-specific working hours instead of the project calendar.

To assign a work hour template to a task, follow these steps:

1. Open the task details pane for the task you want to configure.
1. In the task details form, on the **Plan** tab, go to **Task Work Hour Template**, and select an existing work hour template.
1. Leave **Ignore Resource Calendar** set to **No** to honor assigned resource calendars, or set it to **Yes** to use only the task calendar.
1. Select **Save**.

Project Operations creates a dedicated calendar for the task and applies the calendar change to scheduling. Calendar changes are processed asynchronously, so saving the form and applying the scheduling change aren't the same event.

## Remove a task calendar override

Remove the template when the task should use the project calendar again.

To remove a task calendar override, follow these steps:

1. Open the task details pane.
1. In the task details form, on the **Plan** tab, clear **Task Work Hour Template**.
1. Set **Ignore Resource Calendar** to **No** if you also want scheduling to honor assigned resource calendars.
1. Select **Save**.

The task uses the project calendar after the calendar change is applied. If you leave **Ignore Resource Calendar** set to **Yes**, scheduling continues to ignore resource calendars.

## Ignore the resource calendar for a task

Use this procedure when scheduling should ignore the working hours or time off of every resource assigned to a task.

To ignore the resource calendar for a task, follow these steps:

1. Open the task details pane.
1. In the task details form, on the **Plan** tab, set **Ignore Resource Calendar** to **Yes**.
1. Select **Save**.

Scheduling uses the task calendar if **Task Work Hour Template** is assigned. Otherwise, it uses the project calendar. Set **Ignore Resource Calendar** back to **No** to honor assigned resource calendars again.

## Import tasks with task-level overrides

When you import tasks from another project, Project Operations preserves each source task's **Task Work Hour Template** assignment and **Ignore Resource Calendar** value. Each imported task with a template gets its own calendar based on that template, rather than reusing the source task's dedicated calendar.

The imported settings determine which calendars scheduling honors:

- If a template is assigned, scheduling uses the task calendar instead of the target project's calendar. Otherwise, it uses the target project's calendar.
- If **Ignore Resource Calendar** is **No**, scheduling also honors the calendars of resources assigned to the imported task. If it's **Yes**, scheduling ignores those resource calendars.

This behavior applies to importing tasks from another project, not importing an MPP file.

## Copy a project with task-level overrides

When you copy a project, Project Operations carries forward each source task's **Task Work Hour Template** assignment to the corresponding task in the new project. Each copied task with a template gets its own calendar based on that template, rather than reusing the source task's dedicated calendar.

## Field reference

The following table describes the calendar fields on the **Plan** tab in the task details form. The default values apply to new tasks. Importing tasks from another project preserves the source values.

| Field | Location | Description | Default value |
|-------|----------|-------------|----------------|
| **Task Work Hour Template** | **Plan** tab | Creates a task-specific calendar from the selected work hour template. Doesn't by itself ignore resource calendars. Task import preserves the template assignment and creates a separate calendar for the imported task. | Not set |
| **Ignore Resource Calendar** | **Plan** tab | **Yes** ignores all assigned resource calendars. Scheduling still honors the task calendar, or the project calendar if no task template is assigned. Task import preserves the source value. | **No** |

## Check unexpected scheduling results

Check both settings before changing a project or resource calendar.

| Result | Setting to check | Action |
| ------ | ---------------- | ------ |
| **A task template doesn't allow work during a resource's nonworking hours.** | **Ignore Resource Calendar** is **No**, so scheduling also honors resource calendars. | Set it to **Yes** only if the task should follow its task calendar without considering resource availability. |
| **A task still ignores resource availability after you remove its template.** | **Ignore Resource Calendar** remains **Yes**. | Set it to **No** to honor resource calendars along with the project calendar. |
| **A task with no template doesn't schedule outside the project's working hours.** | **Ignore Resource Calendar** doesn't remove the project-calendar constraint. | Assign an appropriate **Task Work Hour Template** if the task needs different working hours. |
| **An imported task doesn't follow the target project's working hours.** | **Task Work Hour Template** retains the source task's template assignment. | Clear the template to use the target project's calendar, or select a different template for task-specific working hours. |
| **An imported task ignores resource availability.** | **Ignore Resource Calendar** retains the source task's **Yes** value. | Set it to **No** if scheduling should honor the calendars of resources assigned to the imported task. |

[!INCLUDE [footer-include](../includes/footer-banner.md)]
