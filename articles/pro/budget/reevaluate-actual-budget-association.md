---
title: Reevaluate the cost actual-to-budget association
description: This article explains how to reevaluate the cost actual-to-budget association.
author: nimaski
ms.date: 06/24/2024
ms.topic: how-to
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak
ms.author: nimaski
---

# Reevaluate the cost actual-to-budget association

[!INCLUDE[banner](../../includes/banner.md)]

_**Applies To:** Project Operations Integrated with ERP, Project Operations Core._

This article explains how to reevaluate the cost actual-to-budget association.

Project cost actuals are created against the project and go through the approval process. They're available on the **Actuals** tab. You can add the **Actuals** tab to the project page by using related entities.

Actuals are also available under **Sales** in the left navigation. Change the area to **Sales**, select **Transactions**, and then select **Actuals** to open the **Active Actuals** view of the **Actuals** list page. To view all actuals for the project, filter by the **ProjectID** field, and enter the name of the project name that you're interested in.

After a project budget is [created](create-delete-project-budget.md) and [approved](project-budget-status-mgmt.md), project cost actuals are matched against the approved budget lines. Matching of actuals to a budget line follows the [budget line match priority](budget-line-match-priority.md).

The budget line that a project cost actual is matched to is available on the **Budget Associations** tab of the **Actuals** page.

## Reevaluate the association

To reevaluate the cost actual-to-budget association, follow these steps.

1. On the **Actuals** list page, in the **Active Actuals** view, select the cost actuals to reevaluate. The **Reevaluate Budget association** button appears on the Action Pane.
1. Select **Reevaluate Budget association**. The actuals are scheduled for reevaluation. The cost actual-to-budget matching periodic job then picks up the actuals for evaluation. By default, this job runs for every five minutes. 

To check the status, select the cost actual, and then select the **General** tab. The **Budget Evaluation Status** and **Budget Evaluation Result** fields show the status. The following table explains how to interpret the status information.

| Budget Evaluation Status value | Budget Evaluation Result value | Status of the actual-to-budget association |
|---|---|---|
| Blank | Blank | The budget isn't in approved status. |
| **Scheduled** | Blank |The periodic job hasn't yet picked up the actual for evaluation. |
| **Completed** | Blank | The actual is associated with a budget line. You can review the association on the **Budget Associations** tab. |
| **Completed** | **Error** | An error occurred during actual-to-budget matching. The error message is also shown. |

If a cost actual is associated with a budget line, it's available on the **Budget Associations** tab.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
