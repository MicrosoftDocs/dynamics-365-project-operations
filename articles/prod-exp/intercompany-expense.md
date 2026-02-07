---
title: Intercompany expenses
description: Learn how to manage intercompany expenses effectively by assigning a worker's expenses to the legal entity for which the work was performed.
author: mukumarm
ms.author: mukumarm
ms.date: 02/06/2026
ms.topic: concept-article
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak

---

# Intercompany expenses

[!INCLUDE[banner](../includes/banner.md)]

A worker who is employed by one legal entity in an organization might perform work for another legal entity in the same organization. Use intercompany expenses to assign the worker’s expenses to the legal entity for which the work was performed. The legal entity that employs the worker is the loaning legal entity. The legal entity for which the worker incurs expenses is the borrowing legal entity. 

Before a worker can create and submit intercompany expenses, you must enable intercompany expense lines. 

To enable intercompany expense lines, follow these steps:

1. Go to **Expense management** > **Setup** > **General** > **Expense management parameters** form.
1. On the **General** tab, select **Allow intercompany expense lines**. 

To manage **project intercompany expenses**, configure the setup for **default intercompany expense category** by using the **project management parameters** form. Follow these steps: 

1. Go to **Project management and accounting** > **Setup** > **Project management and accounting parameters** > **Intercompany**.
1. Go to **When landing resources** grid.
1. Select **+New** to define the default categories for timesheet and expense categories.
1. Select **Borrowing legal entity**, **Default timesheet category**, **Default expense category**.

## Tax posting for intercompany expenses

[!INCLUDE [banner](../includes/banner.md)]

Before you can use tax groups that are associated with the loaning (source) legal entity instead of the borrowing (destination) legal entity in your expense report, you must enable the functionality in the General ledger sales tax setup.
When you set the **Legal entity for intercompany tax posting** parameter to **Source** and set **Apply sales tax taxation rules** to **No**, the system uses the tax combination for the loaning legal entity. When you set the same parameter to **Destination**, the system uses the tax combination for the borrowing legal entity. 
For legal entities in the United States, when you set the parameter to **Source**, you must also configure the **Sales tax receivable** field on the new **Ledger posting groups** page. The accounting engine uses the information from this field for tax-related accounting entry.
The behavior is consistent for expense lines posted with or without a project.  

## New expense expression builder

The new expense expression builder addresses problems with intercompany expense scenarios that use projects. This feature ensures that, when you create an intercompany expense, the expense policy correctly validates against the project that you select on the expense line, and that the expense report can be successfully submitted.

For the expense expression builder feature to work, turn it on. Also, set up the expense policy that has a project ID.

If you already configured policies that validate the project ID on the expense line, retire those policies. Then, turn on the feature and reconfigure the policies.

To turn on the feature, follow these steps:

1. Go to **Workspaces** \> **Feature Management**.
1. In the list, select **New expense expression builder to address issues with the inter-company expenses scenarios that use projects**. Then select **Enable now**.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
