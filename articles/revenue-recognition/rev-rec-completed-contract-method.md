---
title: Manage revenue estimates
description: This article provides information about how to work with revenue estimates for projects.
author: sigitac
ms.date: 10/27/2023
ms.topic: how-to
ms.reviewer: johnmichalak
ms.author: sigitac
---

# Manage revenue estimates

_**Applies To:** Project Operations Integrated with ERP_

 > [!NOTE]
   > Estimates have been renamed to revenue recognition in a recent product update with the **Update labels for revenue recognition and related forms and processes in Project Operations** feature. Terminology may reference either estimate or revenue recognition depending on if the feature is enabled.

You can create, calculate, post, reverse, or eliminate revenue estimates. You can do this either manually or by using a periodic process. This article provides information about how to work with revenue estimates for projects.

### Manage revenue estimates manually

On the fixed price revenue estimate project or the **Estimate inquiry** page (**Project management and accounting** > **Reports and inquiries** > **Estimates inquiries and reports**), select **Estimates**.

### Manage revenue estimates using a periodic process

Go to **Project management and accounting** > **Periodic** > **Estimates** and select the corresponding process.

## Create a revenue estimate

Complete the following steps to create a revenue estimate. 

1. Go to**Project management and accounting** > **Periodic** > **Estimates**.
2. Select **New**. On the **Estimate creation** page, select the following parameters:

   - **Period code**: This code determines how frequently estimates are posted.
   - **Estimate date**: The date the estimate is processed.
   - **Continuous**: Select this check box to create estimates only if estimates were posted in the previous period, or if the estimate is the first estimate that has been created. If this is not selected, estimates are created even if estimates were not posted in the previous period.
   - **Cost to complete method**: Define how to estimate the remaining project work. For more information, see [Cost to complete methods](cost-complete-methods.md).
   - **Completion method**: Select a completion method from the following options:
     - **Automatic**: The completion percentage is calculated automatically and based on the cost lines included in the calculation. The cost template defines the cost lines that are included.
     - **Manual**: The completion percentage equals the completion percentage of the last estimate. After the estimate is created, you can change the **Manual calculation** on the **Estimates** page.
     - **From cost template**: A combination of the automatic and manual methods. This option is set automatically or manually, depending on the default value in the cost template.
   - **Forecast model**: Select a forecast model for the estimate.
   - **Print estimate list**: Create and show an estimate list. The list contains the status of the current function. You can print any warnings about the estimate on the report. The following conditions cause warnings to appear in the estimate list:
     - A completion percentage of more than 100 percent.
     - A completion percentage less than zero percent.
     - A negative amount in the **To complete** column.
     - An estimate with no corresponding contract amount.
     - An estimate with no attached cost estimate.
   - **Show Infolog**: Select this option to receive a message that contains information about the estimate projects that were processed when the job was run.


## Post WIP or accruals

After the estimates are evaluated, they are maintained, decreased, or increased. You can then post the WIP when you work with the **Completed contract** assessment principle, or post the accruals when you work with the **Completed percentage** assessment principle.
  
The estimate period status changes from **Created** to **Posted**.

## Reverse WIP or accruals

Use the reverse option to credit already posted WIP or accruals, and then create estimates for the period.

> [!NOTE]
> To reverse a period that is in between other periods, reverse the necessary estimate periods and then repost them. Because all subsequent periods depend on the estimates from the previous period, don't skip any periods.

## Eliminate the estimate project and finish the project

The final step in the estimate process is to eliminate the estimate project and end the fixed price project when the percentage of completion reaches 100 percent.

The following occurs when you run the elimination:

- For a fixed price project with a completed contract, the WIP values clear from the balance accounts and post to the profit and loss accounts.
- For a fixed-price project with a completed percentage, the accruals are removed from the profit and loss accounts.

The estimate changes the status to **Eliminated**.

> [!NOTE]
> In special cases, the percentage can extend beyond 100 percent. When this happens, reduce the percentage of completion by using the **Set cost to complete to zero method** to reach 100 percent.

## Reverse elimination

1. Go to **Project management and accounting** > **Periodic** > **Estimates** > **Reverse elimination**. 
2. On the Action Pane, on the **Process** tab, in the **Maintain** group, select **Estimate**. 
3. Select **Reverse elimination**.

Use this page to reverse all eliminations with a specified estimate date and with an estimate status of **Eliminated**. The transaction status changes after you select the appropriate fields.

This also automatically changes the project status to **In process** if the project stage is set to finished. The estimate status of the project period changes back to **Posted**.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
