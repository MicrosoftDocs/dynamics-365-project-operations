---
title: Control deletion of project tasks
description: Learn how to protect project tasks from deletion and how protection applies to summary tasks, copied tasks, and Microsoft Dataverse operations.
author: dishantpopli
ms.author: dishantpopli
ms.reviewer: johnmichalak
ms.date: 10/05/2026
ms.topic: how-to
ms.custom: 
    - bap-template

---

# Control deletion of project tasks

[!INCLUDE[banner](../includes/banner.md)]

_**Applies To:** Project Operations Integrated with ERP, Project Operations Core_

Controlled task deletion helps you protect selected project tasks independently of the existing deletion checks for time entries and actuals. Project managers can protect governance tasks, contractual milestones, and other important work breakdown structure elements. Organizations can also set protection through Microsoft Dataverse automation to enforce their own policies.

## Key concepts

Controlled task deletion uses the **User block delete** column on a project task. The underlying Dataverse column is `msdyn_userblockdelete`.

- **Direct protection** - A task is directly protected when **User block delete** is `Yes` on that task.
- **Inherited protection** - A summary task is protected when any task below it in the hierarchy is directly protected. The summary task's own **User block delete** value can remain `No`.
- **System protection** - Project Operations can also prevent deletion for system-managed reasons, such as when a task has actuals. User protection doesn't replace these existing checks.

> [!NOTE]
> New tasks have **User block delete** set to `No` by default.

## How controlled task deletion works

When you set **User block delete** to `Yes`, Project Operations blocks deletion of that task. Dynamics 365 Project Operations also applies protection up the task hierarchy so that deleting a summary task can't indirectly delete a protected descendant.

1. You set **User block delete** to `Yes` on a task.
1. Project Operations protects the task and each of its ancestors from deletion.
1. Other branches and sibling tasks remain unaffected unless they have their own deletion constraint.
1. When you set the value back to `No`, Project Operations removes inherited protection from ancestors that have no other protected descendants or system-managed deletion constraints.

> [!IMPORTANT]
> Setting **User block delete** to `No` doesn't guarantee that you can delete the task. Actuals, a protected descendant, or another system-managed constraint can still prevent deletion.

## Prerequisites

- You must have permission to update the project and its tasks.
- An admin must include **User block delete** in the task grid column configuration. The column is available for configuration but hidden by default.
- The task column access configuration must allow you to edit **User block delete**. An admin can make the column noneditable.

Existing environments receive the column in their task grid configuration data automatically. An admin still needs to make the column visible for users who manage task protection.

## Protect a task from deletion

Use the task grid to protect an individual task. To protect a task from deletion, follow these steps:

1. Open the task grid for the project that contains the task.
1. Find the task that you want to protect.
1. In the **User block delete** column, set the value to `Yes`.

Project Operations prevents deletion of protected tasks by disabling the **Delete task** option in the task context menu. If the task is below a summary task, Project Operations also prevents deletion of every summary task above it. The protection doesn't change the values on sibling tasks.

## Remove user protection from a task

Remove protection only when your organization's policy allows the task to be deleted. To remove user protection from a task, follow these steps:

1. Open the task grid for the project that contains the protected task.
1. In the **User block delete** column, set the value to `No`.

Project Operations reevaluates the task hierarchy. An ancestor becomes deletable only when it has no other protected descendants and no system-managed deletion constraint.

## Apply protection with Dataverse automation

The `msdyn_userblockdelete` column supports schedule API operations. You can use a schedule API automation to set the value from an organization-specific rule.

Set `msdyn_userblockdelete` to `true` to protect a task and to `false` to remove its user protection. Standard task update permissions apply.

## Protection during copy operations and import task

Project Operations preserves user protection in these operations:

- Copy a project.
- Copy and paste an individual task.
- Copy and paste a summary task and its descendants.
- Import a task.

Project Operations recalculates inherited protection in the new hierarchy. A copied or imported task that has **User block delete** set to `Yes` remains protected, and its ancestors are also protected from deletion.

## Field reference

| Field | Dataverse column | Description | Required | Default value |
|-------|------------------|-------------|----------|---------------|
| **User block delete** | `msdyn_userblockdelete` | Controls whether a user or automation directly protects the task from deletion. | No | `No` |

## Known issues

| Issue | Cause | Resolution |
|-------|-------|------------|
| **User block delete** isn't visible in the task grid. | The column is hidden by default. | Ask an admin to include the column in the task grid column configuration. |
| You can see **User block delete**, but you can't change it. | Task column access configuration makes the column noneditable for your access level. | Ask an admin to review your task column access configuration. |
| You set **User block delete** to `No`, but you still can't delete the task. | The task has a protected descendant, actuals, or another system-managed deletion constraint. | Check the task's descendants and existing task deletion restrictions. Remove only the constraints that your organization's policy allows you to remove. |
| You can't delete a summary task whose value is `No`. | At least one descendant has **User block delete** set to `Yes`, so the summary task inherits protection. | Review the descendant tasks. Remove direct protection only when your organization's policy permits it. |
| A copied task remains protected. | Project and task copy operations preserve user protection by design. | Set **User block delete** to `No` on the copied task if the new project doesn't require the protection. |

[!INCLUDE[footer-include](../includes/footer-banner.md)]
