---
title: Map projects and tasks to project quote lines
description: This article provides information about how to map projects and tasks to project quote lines.
author: poojafandan
ms.date: 06/07/2024
ms.topic: how-to
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak
ms.author: poojafandan
---

# Map projects and tasks to project quote lines

[!INCLUDE[banner](../../includes/banner.md)]

_**Applies To:** Project Operations Integrated with ERP, Core deployment - deal to proforma invoicing_

On project quote lines, you can map the specific tasks of a project that is already associated to a quote line.

When you map tasks to a quote line, the following items you defined on the quote line will only apply to those tasks:

- Billing method
- Chargeability options
- Not-to-exceed limits
- Customers

For example, you might have a project where one phase is fixed price and all the other phases are time and materials. In this case, you can associate the first phase, and all of its child tasks, to the quote line for that phase with a fixed price billing method. You can then associate all the other phases to the time and materials-based quote line.

## Associate tasks to project-based quote lines

You can associate tasks with quote lines from the following locations:

- **Project** page > **Task billing** tab (optimal)
- **Quote Line** page > **Chargeable tasks** tab 

### From the Project page

The **Project** page provides the optimal experience for associating tasks to quote lines. You can use this page to select multiple tasks and associate all of them, plus their child tasks, to the selected quote line.

1. On the **General** tab of a project–based quote line, verify the **Project** field is filled out.
2. In the **Included tasks** field, select **Selected tasks only**.
3. Save the project-based quote line. When the form refreshes, the **Chargeable tasks** tab displays.
4. On the **General** tab, select the link for the project from the **Project** field.
5. On the **Project** page, select the **Task billing** tab.
6. In the second grid, which applies to task-specific billing setup, select one or more tasks and then select **Associate quote lines**.
7. In the dialog page that appears, select a quote line that displays project-based quote lines on the quote.
8. In the **Billing type** field, indicate if these tasks are chargeable or non-chargeable.
9. Select the check box to indicate if the association should include child tasks of the selected tasks. Checking the box will associate the child tasks of the selected tasks to the quote line.
10. Select **OK** to close the dialog.

### From the Quote line page

You can associate project tasks to quote lines from the **Chargeable tasks** tab on **Quote line** page.

>[!NOTE]
>The optimal place to associate project tasks to quote lines is on the **Task billing** tab on the **Project** page. If you associate tasks from the **Chargeable tasks** tab on **Quote line** page, you must manually associate each project.

1. On the **General** tab of a project–based quote line, verify that there is a project selected in the **Project** field.
2. In the **Included tasks** field, select **Selected tasks only**.
3. Save the project-based quote line. When the form refreshes, the **Chargeable tasks** tab displays.
4. On the **Chargeable tasks** tab, select **Add a quote line task**.
5. On the **Quote line task** page, in the **Tasks** field, select the task and in the **Billing type** field, select **Save**. 
6. Close the page. The selected task is now associated to the quote line.

## Disassociate tasks from project–based quote lines

### From the Project page

This method provides the most optimal experience for disassociating tasks from quote lines. You can select multiple tasks and disassociate all of the them, plus their child tasks, from the selected quote line.

1. On the **General** tab of a project–based quote line, in the **Project** field, select the project link.
2. On the **Project** page, select the **Task billing** tab.
3. In the second grid, which applies to task-specific billing setup, select one or more tasks, and then select **Disassociate quote lines**.
4. In the dialog page that appears, select a quote line.
5. Select the check box to indicate whether the association should also be removed from child tasks of the selected tasks. Checking the box will also disassociate the child tasks of the selected tasks to the quote line.
6. Select **OK**. A warning message informs you that if you remove this association, any actuals previously recorded on the task could be reversed. 
7. Select **OK** to continue and remove the association between the task and the project-based quote line.

### From the Quote line page

You can also disassociate project tasks to quote lines from the **Chargeable tasks** tab on **Quote line** page.

1. On the **Chargeable tasks** tab, select **Delete a quote line task**.
2. Select **OK**. A warning message informs you that if you remove this association, any actuals previously recorded on the task could be reversed. 
3. Select **OK** to continue and remove the association between the task and the project-based quote line.

>[!NOTE]
> This procedure doesn't delete the task from the project. It only removes the task association from the project-based quote line.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
