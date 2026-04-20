---
title: Map projects and tasks to a project contract line
description: Learn how to map specific tasks to project contract lines for better billing control. Follow step-by-step instructions to optimize task associations.
author: poojafandan
ms.author: poojafandan
ms.date: 02/05/2026
ms.topic: how-to
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak

---

# Map projects and tasks to a project contract line

[!INCLUDE[banner](../../includes/banner.md)]

_**Applies To:** Project Operations Core, Project Operations Integrated with ERP_

On project contract lines, you can map specific tasks in a project to the contract line.

When you map specific tasks to a contract line, the billing method, chargeability options, not-to-exceed limits, and the customers you define on the contract line apply to those specific tasks only.

If you have a scenario where one phase of a project, such as the Prototype Phase, is fixed price and all the other phases are time and material, you can associate the Prototype phase and all the associated child tasks to the contract line for that phase with a fixed price billing method.

You can associate all the other phases in your project work breakdown structure (WBS) to the time and material-based contract line.

## Associate tasks to project contract lines

You can associate tasks to contract lines from the **Chargeable Tasks** tab on the **Contract Line** page or from the **Task Billing** tab on the **Project** page.

### From the Contract line page

Complete the following steps to associate project tasks to the contract line from the **Chargeable Tasks** tab of the **Contract Line** page.

1. On the **General** tab of a project-based contract line, verify that the **Project** field is filled out.
1. In the **Included Tasks** field, select the **Selected Tasks Only** option.
1. Save your changes. The form refreshes and the **Chargeable Tasks** tab becomes visible.
1. Select the **Chargeable Tasks** tab, and in the subgrid, select **Add a Contract Line Task**.
1. On the **Contract Line Tasks** page, in the **Tasks** drop-down, select the task.
1. Enter information in the **Billing Type** field, and then select **Save and Close**. The selected task is associated to the contract line.

> [!NOTE]
> This method isn't the most optimal experience for associating project tasks to contract lines. You must manually associate each project in this experience. The preferred way is from the **Task Billing** tab on the **Project** page.

### From the project page

This method is the optimal method to associate tasks to contract lines. You can select multiple tasks and associate all of them and their child tasks to the selected contract line. Complete the following steps to associate tasks to the contract line from the **Project** page.

1. On the **General** tab of a project-based contract line, verify that the **Project** field is filled out.
1. On the **Included Tasks** field, select **Selected Tasks Only**.
1. Save the project-based contract line. The form refreshes and the **Chargeable Tasks** tab becomes visible. This tab is just for verification purposes only.
1. On the **General** tab of the project-based contract line, in the **Project** field, select the project link.
1. On the **Project** page, select the **Task Billing Setup** tab.
1. You see two grids. One grid is for contract lines that apply to the whole project. The second grid applies to task-specific billing setup. In the second grid, select one or more tasks, and then select **Associate Contract Lines**.
1. In the dialog box that opens, select a contract line from the drop-down.
1. Use the **Billing Type** drop-down to mark the tasks as chargeable or non-chargeable.
1. Select the check box to indicate if the association should also include child tasks of the selected tasks. Checking the box also associates the child tasks of the selected tasks to the contract line.
1. Select **OK** to close the dialog.

## Unassociate tasks from project-based contract lines

### From the contract line page

Follow these steps to unassociate project tasks from the contract line on the **Chargeable Tasks** tab of the **Contract Line** page.

1. On the **Chargeable Tasks** tab, select **Delete a Contract Line Task**.
1. A warning message indicates that removing this association could reverse any actuals previously recorded on the task. Select **OK** on the dialog to remove the association between the task and the project-based contract line.

> [!NOTE]
> This action doesn't delete the task from the project. Instead, it removes the task association from the project-based contract line.

### From the project page

This method is the more optimal experience for unassociating tasks from contract lines. You can select multiple tasks and unassociate all of them and their child tasks from the selected contract line. Follow these steps to unassociate tasks from the contract line.

1. From the **General** tab of the project-based contract line, in the **Project** field, select the link for the project.
1. On the **Project** page, select the **Task Billing Setup** tab.
1. Two grids appear on the page. One grid is for contract lines that apply to the whole project. The second grid applies to task-specific billing setup. In the second grid, select one or more tasks and then select **Disassociate Contract Lines**.
1. In the dialog, select a contract line from the drop-down.
1. Select the check box to indicate if the association should also be removed from any child tasks of the selected tasks. Checking the box also unassociates the child tasks of the selected tasks from the contract line.
1. Select **OK**. A warning message indicates that removing this association could reverse any actuals previously recorded on the task. Select **OK** on the warning dialog to remove the association between the task and the project-based contract line.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
