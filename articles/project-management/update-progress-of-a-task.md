---
title: Update the progress of a task
description: Learn how to update the progress of a task directly from the task grid.
author: dishantpopli
ms.date: 05/05/2025
ms.topic: how-to
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak
ms.author: dishantpopli
---

# Update the progress of a task

_**Applies To:** Project Operations Integrated with ERP, Core deployment - deal to proforma invoicing._

In Microsoft Dynamics 365 Project Operations, users can update the progress of a task directly from the task grid.

An option that is named **Allow percent complete update** determines whether users can update the **% complete** field directly in the task grid. This option is available in two places:

- **Project Parameter page** – The value that is set on this page is used as the default value for all projects for the selected organization. To change the value on the **Project Parameter** page, go to **Settings** \> **Parameters**.

    :::image type="content" source="media/allow-percent-complete-update-project-parameter.png" alt-text="Screenshot that highlights the location of the Allow percent complete update option on the Project Parameter page.":::

- **Summary tab on the project page** – Users can change the default value for a specific project by setting the option directly at the project level.

    :::image type="content" source="media/allow-percent-complete-update-project-summary.png" alt-text="Screenshot that shows highlights the location of the Allow percent complete update option on the Summary tab of the project page.":::

The **Allow percent complete update** option can have the following values.

| Value | Behavior |
|-------|----------|
| No | Users can't update the **% complete** field directly in the task grid. Instead, they must submit a time entry. The time entry updates the **Effort** field and adjusts the **% complete** value for the task.|
| Yes | Users can update the **% complete** field directly in the task grid by entering a number in the **% complete** column. Alternatively, they can update the **% complete** field by selecting the checkbox next to the task name to mark the task as completed. |

In the following screenshot, a user updated the **% complete** field by entering a number in the **% complete** column of the task grid. The screenshot also shows the location of the checkbox that is used to mark a task as completed.

:::image type="content" source="media/allow-percent-complete-update-task-grid.png" alt-text="Screenshot that highlights the location of the % complete column in the task grid, where a value is entered. It also highlights the location of the checkbox for marking a task as completed.":::

> [!IMPORTANT]
> - Tasks can be marked as completed only if effort is assigned to them.
> - If a project is associated with a contract line, the **Allow percent complete update** option is automatically set to **No**, and users can't change the value to **Yes**.
> - After the **Allow percent complete update** option is set to **Yes**, the value can't be changed back to **No**.

## Scenario 1: Allow percent complete update is set to Yes

If the **Allow percent complete update** option is set to **Yes**, users have the following options for updating the **% complete** value in the task grid:

- The **% complete** field can be edited directly in the task grid. Users can enter any value between 0 and 100 to update the task's completion status. In the background, the value that is entered is used to calculate and update the **Effort** field in the task grid.
- Users can submit a time entry. The time entry updates the **Effort** field. This update, in turn, adjusts the **% complete** value.
- Users can instantly mark a task as completed by selecting the checkbox next to the task name. The **% complete** field is automatically set to 100%. If the checkbox is cleared, task completion is reset to 0%, and any previous **% complete** value isn't saved.

## Scenario 2: Allow percent complete update is set to No

If the **Allow percent complete update** option is set to **No**, users have the following options for updating the **% complete** value in the task grid:

- The **% complete** field can't be edited directly in the task grid. Instead, users must submit a time entry. The time entry updates the **Effort** field. This update, in turn, adjusts the **% complete** value.
- Users can instantly mark a task as completed by selecting the checkbox next to the task name. This action sets the **Effort Remaining** field to **0** and, in turn, marks the task as 100% completed. If the checkbox is cleared, the **% complete** field reverts to its previous value.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
