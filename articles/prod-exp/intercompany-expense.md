---
title: Intercompany expenses
description: This article provides information about how to use intercompany expenses to assign a worker’s expenses to the legal entity for which the work was performed.
author: mukumarm
ms.author: mukumarm
ms.date: 05/17/2024
ms.topic: article
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak

---

# Intercompany expenses

A worker who is employed by one legal entity in an organization might perform work for another legal entity in the same organization. You can use intercompany expenses to assign the worker’s expenses to the legal entity for which the  work was performed. The legal entity that employs the worker is called the loaning legal entity. The legal entity for which the worker incurs expenses is called the borrowing legal entity. 

Before a worker can create and submit intercompany expenses, you must enable intercompany expense lines. 

To enable intercompany expense lines, follow these steps:

1. Go to **Expense management** > **Setup** > **General** > **Expense management parameters** form.
2. On the **General** tab, select **Allow intercompany expense lines**. 

To manage **project intercompany expenses**, configure the setup for **default intercompany expense category** using **project management parameters** form following these steps. 

1. Go to **Project management and accounting** > **Setup** > **Project management and accounting parameters** > **Intercompany**.
2. Go to **When landing resources** grid.
3. Select **+New** to define the default categories for timesheet and expense categories.
4. Select **Borrowing legal entity**, **Default timesheet category**, **Default expense category**.

## Tax posting for intercompany expenses

[!include [banner](../includes/banner.md)]

Before you can use tax groups that are associated with the loaning (source) legal entity instead of the borrowing (destination) legal entity in your expense report, you must enable the functionality in the General ledger sales tax setup. 
When the **Legal entity for intercompany tax posting** parameter is set to **Source** and **Apply sales tax taxation rules** is set to **No**, the tax combination for the loaning legal entity is used. When the same parameter is set to **Destination**, the tax combination for borrowing legal entity will be used. 
For legal entities in the United States, when the parameter is set to **Source**, the **Sales tax receivable** field must also be configured on the new **Ledger posting groups** page. The accounting engine will use the information from this field for tax-related accounting entry.   
The behavior is consistent for expense lines posted with or without a project.  

## New expense expression builder

The new expense expression builder addresses issues with intercompany expense scenarios that use projects. This feature ensures that, when you create an intercompany expense, the expense policy is correctly validated against the project that is selected on the expense line, and that the expense report can be successfully submitted.

For the expense expression builder feature to work, it must be turned on. Additionally, the expense policy that has a project ID should be set up.

If you've already configured policies that validate the project ID on the expense line, those policies must be retired. You can then turn on the feature and reconfigure the policies.

To turn on the feature, follow these steps:

1. Go to **Workspaces** \> **Feature Management**.
2. In the list, select **New expense expression builder to address issues with the inter-company expenses scenarios that use projects**. Then select **Enable now**.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
