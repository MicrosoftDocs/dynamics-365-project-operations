---
title: Map projects and tasks to a project contract line 
description: This article provides information about adding and removing projects and tasks to a contract line.
author: poojafandan
ms.author: poojafandan
ms.date: 03/10/2024
ms.topic: how-to
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak

---

# Map projects and tasks to a project contract line 

[!INCLUDE[banner](../../includes/banner.md)]

_**Applies To:** Core deployment - deal to proforma invoicing, Project Operations Integrated with ERP_

On project contract lines, you can map specific tasks in a project to the contract line.

When you map specific tasks to a contract line, the billing method, chargeability options, Not-to-exceed limits, and the customers defined on the contract line will be applicable to those specific tasks only.

If you have a scenario where one phase of a project, for example the Prototype Phase, is fixed price and all the other phases are time and material, you will be able to associate the Prototype phase and all the associated child tasks to the contract line for that phase with a fixed price billing method.

All the other phases in your project work breakdown structure (WBS) can be associated to the time and material-based contract line.

## Associate tasks to project contract lines

Tasks can be associated to contract lines from the **Chargeable Tasks** tab on the **Contract Line** page or from the **Task Billing** tab on the **Project** page.

### From the Contract line page

Complete the following steps to associate project tasks to the contract line from the **Chargeable Tasks** tab of the **Contract Line** page.

1. On the **General** tab of a project-based contract line, verify that the **Project** field is filled out.
2. In the **Included Tasks** field, select the **Selected Tasks Only**.
3. Save your changes. The form will refresh and the **Chargeable Tasks** tab will be visible.
4. Select the **Chargeable Tasks** tab, and in the subgrid, select **Add a Contract Line Task**.
5. On the **Contract Line Tasks** page, in the **Tasks** drop-down, select the task. 
6. Enter information in the **Billing Type** field, and then select **Save and Close**. The selected task is associated to the contract line.

> [!NOTE]
> This is not the most optimal experience for associating project tasks to contract lines. Each project will have to be manually associated in this experience. The preferred way is from the **Task Billing** tab on the **Project** page.

### From the project page

This is the optimal method to associate tasks to contract lines. You can select multiple tasks and associate all of the them and their child tasks to the selected contract line. Complete the following steps to associate tasks to the contract line from the **Project** page.

1. On the **General** tab of a project-based contract line, verify that the **Project** field is filled out.
2. On the **Included Tasks** field, select **Selected Tasks Only**.
3. Save the project-based contract line. The form will refresh and the **Chargeable Tasks** tab will be visible. This is just for verification purposes only.
4. On the **General** tab of the project-based contract line, in the **Project** field, select the project link.
5. On the **Project** page, select the **Task Billing Setup** tab.
6. There are two grids. One grid is for contract lines that apply to the whole project. The second grid applies to task-specific billing setup. In the second grid, select one or more tasks, and then select **Associate Contract Lines**.
7. In the dialog page that opens, select a contract line from the drop-down.
8. Use the **Billing Type** drop-down to mark the tasks as chargeable or non-chargeable.
9. Select the check box to indicate if the association should also include child tasks of the selected tasks. Checking the box will also associate the child tasks of the selected tasks to the contract line.
10. Select **OK** to close the dialog.

## Unassociate tasks from project-based contract lines

### From the contract line page

Complete the following steps to unassociate project tasks from the contract line on the **Chargeable Tasks** tab of the **Contract Line** page.

1. On the **Chargeable Tasks** tab, select **Delete a Contract Line Task**.
2. A warning message indicates that removing this association could result in reversal of any actuals previously recorded on the task. Select **OK** on the dialog to remove the association between the task and the project-based contract line. 

> [!NOTE]
> This doesn't delete the task from the project. Instead, it removes the task association from the project-based contract line.

### From the project page

This is the more optimal experience for unassociating tasks from contract lines. You can select multiple tasks and unassociate all of the them and their child tasks from the selected contract line. Complete the following steps to unassociate tasks from the contract line.

1. From **General** tab of the project-based contract line, in the **Project** field, click on the link for project.
2. On the **Project** page, select the **Task Billing Setup** tab.
3. There are two grids on the page. One grid is for contract lines that apply to the whole project and the second applies to task-specific billing setup. In the second grid, select one or more tasks and the select **Disassociate Contract Lines**.
4. In the  dialog page that opens, select a contract line from the drop-down.
5. Select the check box to indicate if the association should also be removed from any child tasks of the selected tasks. Checking the box will also unassociate the child tasks of the selected tasks from the contract line.
6. Select **OK**. A warning message indicates that removing this association could result in reversal of any actuals recorded on the task previously. Select **OK** on the warning dialog to remove the association between the task and the project-based contract line.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
