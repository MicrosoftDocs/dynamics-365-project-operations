---
# required metadata

title: Transfer project budgets at fiscal year end
description: This article provides information about how to transfer remaining budget amounts to future years and create budget register details. 
author: niranjanmaski
ms.author: nimaski
ms.date: 02/26/2026
ms.topic: how-to
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak

---

# Transfer project budgets at fiscal year end

[!include [banner](../includes/banner.md)]

When working on a multiyear project, you might have remaining budget at the end of the fiscal year. You can transfer the remaining budget amounts to a future year, and create budget register details for the amounts in the associated general ledger accounts. Before you carry forward the remaining amounts, review and analyze the remaining budget amounts.

## Review and analyze remaining budget amounts

Complete the following steps to review the year-end budget amounts for projects, but don't carry the amounts forward.

1. Go to **Project management and accounting** > **Periodic** > **Budgets** > **Carry forward budgets**. 
1. On the **Project budget carry-forward process** page, on the **Year-end options** tab, verify that **Carry forward remaining project budget amounts** isn't enabled.
1. On the **Parameters** tab, in the **Project budget year** field, select the fiscal year for which you want to view the remaining budget amount. 
1. In the **Opening fiscal year** field, select the fiscal year for which you want to view the remaining budget amount. 
1. In the **From forecast model** field, select **Remaining budget**. 
1. To include projects that meet your selected criteria and have no remaining budget, select **Show zero remaining**.  
1. On the **Select Budgets** tab, select **Retrieve all budgets** to load all budgets that match your selected criteria, and then select **Process**. 
1. To design a database query that loads a specific set of budgets into the pane, select **Retrieve selected budgets**.

For more information about a specific line in the pane, select the line, and then select **View budget details** or **View accounts**.

## Carry forward remaining budget amounts 

When you process remaining budget amounts, you can create transactions in the general ledger for the amounts that you're carrying forward. To create general ledger transactions, complete the steps in the section, [Carry forward budget amounts and create general ledger transactions](#carry-forward). 

> [!NOTE]
> Budget amounts that you carry forward are transferred to the forecast model that you select in the **Forecast models** page as the carry-forward forecast model.  

## <a name="carry-forward"></a>Carry forward budget amounts and create general ledger transactions

1.  Select **Project management and accounting** > **Periodic** > **Budgets** > **Carry forward budgets**. 
1. On **Project budget carry-forward process**, select **Year-end**, and then enable **Carry forward remaining project budget amounts** and **Create budget register entries in general ledger**. 
1. On the **Parameters** tab, in the **Project parameters** field group, select the following values:

   - **Project budget year**: Select the beginning of the fiscal year for which you want to view the remaining budget amounts. 
   - **Profit and loss**: Create profit and loss transactions in the general ledger. 
   -  **WIP**: Create Work in Progress (WIP) transactions in the general ledger.
   -  **Payroll**: Create payroll allocation transactions in the general ledger. 

1. In the **General ledger** field group, provide the following information: 

   - In the **Opening fiscal year** field, select the fiscal year that you want to transfer remaining budget amounts to for the projects. The default value is one year after the value in the **Project budget year** field.
   -  In the **Carry-forward period** field, select the period that you want to create the budget register details for in the general ledger. This period is typically the first period in the opening fiscal year.

1. In the **Copy from/to** field group, provide the following information:

   - In the **From forecast model** field, select the project budget forecast model associated with the remaining budget amounts you want to transfer for the projects. 
   - In the **To ledger budget model** field, select the ledger budget model associated with the budget amounts you want to transfer to the general ledger. 
   -  Select **Transfer sales currency** to use the project's sales currency for the general ledger transactions that are created when you transfer the budget amounts for the projects. When you don't select the option, the transactions use the accounting currency. 
   -  Select **Show zero remaining** to include projects that have no remaining budget amounts, but meet the other criteria that you select in the projects displayed in the bottom pane.

1. On the **Select Budgets** tab, select **Retrieve all budgets** to load all budgets that match the criteria you selected. If you prefer to design a database query that loads a specific set of project budgets into the pane, select **Retrieve selected budgets**.
1. For each project that you want to process, select the option at the beginning of the line for the project.

    > [!TIP]
    > To select all or most of the projects, select the check mark in the upper-left corner. To exclude processing any project, clear the check mark for that project.

1. To transfer the remaining budget amounts for the selected projects to the selected fiscal year and create budget register details in the general ledger, select **Process**.

## Carry forward budget amounts without creating general ledger transactions

1. Go to **Project management and accounting** > **Periodic** > **Budgets** > **Carry forward budgets**.
1. On **Project budget carry-forward process**, in the **Year-end options** field, select **Carry forward remaining project budget amounts**.
1. In the **Parameters** group, in the **Project budget year** field, select the fiscal year for which you want to view the remaining budget amounts.
1. In the **Copy from/to** group, provide the following information:

   - In the **From forecast model** field, select the project budget forecast model that is associated with the remaining budget amounts that you want to transfer for the projects. 
   - Select **Show zero remaining** to include projects that have no remaining budget amounts, but that meet the other criteria you selected.
   - In the **Select Budgets** group, select **Retrieve all budgets** to load all budgets that match the criteria that you selected. To design a database query that loads a specific set of project budgets into the pane, select **Retrieve selected budgets**.

1. For each project that you want to process, select the option at the beginning of the line for the project. 
1. Select **Process** to transfer the remaining budget amounts for the selected projects to the selected fiscal year.



[!INCLUDE[footer-include](../includes/footer-banner.md)]
