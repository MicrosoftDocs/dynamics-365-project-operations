---
title: Update progress of a task
description: This article provides information about the updating the percent complete from task grid.
author: dishantpopli
ms.date: 05/05/2025
ms.topic: how-to
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak
ms.author: dishantpopli
---

# Updating Percent Complete in Task Grid

_**Applies To:** Project Operations for resource/non-stocked based scenarios, Lite deployment - deal to proforma invoicing_

In Microsoft Dynamics 365 Project Operations, users can update the progress of a task directly from the task grid. Whether a user is allowed to update the **% Complete** depends on a field called **Allow percent complete update**. This field controls if users can make changes to the **% Complete** from the task grid. This field can have following values:
| Value            | Behavior |
|------------------|----------|
| **No**   | The **% Complete** field cannot be updated directly from the task grid. Instead, users must submit their time entries, which will update the **Effort** and, in turn, adjust the **% Complete** for the task.|
| **Yes** | The **% Complete** field can be updated directly from the task grid by either entering a number in the **% Complete** column or by clicking the checkbox next to the task name to mark it as complete.|


>[!NOTE]
> A task with no effort cannot be marked as completed. 


This field is available at two places:
- **Project Parameter** - This field is located under Settings > Parameters for the specific organization. The value set here will be used as the default for all newly created projects.
- **Project Summary Page** - A user can change the default value for a specific project by updating it directly at the project level.

For any existing project, the default value will be "No".

## Scenario 1: Allow percent complete update is set to Yes
- **Update the % Complete on task grid** - The **% Complete** field on the task grid is editable. Users can enter any value between 0 and 100 to update the task's completion status. In the background, the value entered in the **% Complete field** is used to calculate and update the **Effort** field on the task grid. Alternatively, users can submit time entries, which will update the **Effort** field and, in turn, adjust the **% Complete** value.
- **Complete the task instantly** - A user can instantly mark a task as complete by checking the box next to the task name, which sets the **% Complete** field to 100%. If the box is unchecked, the task completion resets to 0%, and any previous **% Complete** value is not saved.

## Scenario 2: Allow percent complete update is set to No
- **Update the % Complete on task grid** - The **% Complete** field cannot be edited directly on the task grid. To update it, users must submit time entries, which will adjust the **Effort** field and automatically update the **% Complete** value.
- **Complete the task instantly** - A user can instantly complete a task by checking the box next to the task name. This sets the **Effort Remaining** field to 0, which marks the task as 100% complete. If the checkbox is unchecked, the **% Complete** value returns to its previous state.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
