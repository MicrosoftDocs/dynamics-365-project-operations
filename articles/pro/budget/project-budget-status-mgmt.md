---
title: Project budget status management
description: This article provides information that will help you manage the status of a project budget.
author: nimaski
ms.date: 02/26/2026
ms.topic: how-to
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak
ms.author: nimaski
---

# Project budget status management

[!INCLUDE[banner](../../includes/banner.md)]

_**Applies To:** Project Operations Integrated with ERP, Project Operations Core._

This article helps you manage the status of a project budget. It explains the different statuses that a project budget can have, the triggers for transitions from one status to another, and the statuses in which you can edit a project budget.

> [!NOTE]
> You can track actuals only against project budgets that have an **Approved** status.

As a prerequisite for the procedures in this article, create a project budget. For information about how to create a budget for a project, see [Create and delete project cost budgets](create-delete-project-budget.md).

The following table describes the different project statuses.

| Budget status | Description |
|---|---|
| Draft | While a budget is in this status, you can update and save budget dimensions, quantities, prices, and budget amounts. Budget lines are editable. You must submit the budget to move to **In Review** status. |
| In Review | The budget is submitted for approval and is under review. If the budget is approved, it moves to **Approved** status. If it's rejected, it moves to **Rejected** status. While a budget is in this status, you can't edit it. |
| Approved | The budget is approved, and you track actuals against the budget lines. While a budget is in this status, you can't edit it. |
| Rejected | The budget that you submitted for review is rejected. You must update budget lines according to the user's needs and then resubmit to move back to **In Review** status. While a budget is in this status, you can edit budget lines. |
| Revised | An approved budget version is revised, and the new budget version is approved. The previously approved version moves to **Revised** status. While a budget is in this status, you can't edit budget lines. |

The following illustration shows the transitions between project budget statuses.

:::image type="content" source="media/2-project-budget-state-management-pic.png" alt-text="Screenshot of project budget status transitions.":::

## Approve a budget

To approve a project budget, follow these steps:

1. Sign in to Microsoft Dynamics 365 Project Operations.
1. In the left navigation, change the area to **Projects**.

    If you create a budget, you see the **Budget** tab. Create budget lines that match the requirements of your project.

1. Make sure that all the budget lines are created, and that you want to approve the budget.
1. On the command bar, select **Submit budget**.

    The budget moves to **In Review** status and you can no longer edit it.

1. After the system validates the submitted budget, select **Budget** on the command bar. The menu that appears has two options: **Approve** and **Reject**. Follow one of these steps:

    - To approve the submitted budget, select **Approve**.
    - If you want to make additional changes to the budget, select **Reject**. The budget moves to **Rejected** status and you can edit it. After you make the required edits, you can submit the budget again for approval.

> [!NOTE]
> Currently, no workflow for budget approval is implemented.

## Delete a budget

To delete a project budget, follow these steps:

> [!IMPORTANT]
> You can't recover budget data after you delete a budget.

1. Sign in to Project Operations.
1. In the left navigation, change the area to **Projects**.

    If you create a budget, you see the **Budget** tab. Create budget lines that match the requirements of your project.

1. On the command bar, select **Budget**, and then select **Delete**.

    The **Delete** option is available only if the budget is in a status that allows deletion. You can delete a budget only if it's in **Draft** or **Rejected** status. You can't delete a budget if it's in **In Review**, **Approved**, or **Revised** status.

1. In the dialog box, select **Confirm** to confirm that you want to delete the budget, or select **Cancel** to cancel the deletion.

> [!NOTE]
> You can't delete a project that has a budget unless you first delete the project budget.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]

[Microsoft](https://www.microsoft.com)
