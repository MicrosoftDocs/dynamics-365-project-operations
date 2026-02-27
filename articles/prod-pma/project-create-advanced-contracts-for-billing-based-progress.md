---
title: Create advanced contracts for billing based on progress
description: This article explains how to create project contracts so that you can generate invoices for customers, based on a percentage of completed work.
author: ryansandness
ms.author: ryansandness
ms.date: 02/26/2026
ms.topic: how-to
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak

---

# Create advanced contracts for billing based on progress
[!include [banner](../includes/banner.md)]

This article explains how to create project contracts so that you can create invoices for customers, based on a percentage of completed work. The system automatically calculates invoice amounts for the budget categories of work that you set up for a project. Set the invoice timing when you negotiate the project contract with the customer.

Use the procedures in this article to set up a contract, an associated project, and the billing rules that calculate invoice amounts for the budget categories of work that you set up for the project.

After you create the contract and the project, you can set up the details of the project. For example, you can define activities and assign workers to the project.

## Example

Your organization is a software development firm. You agree to develop a payroll accounting package for a customer for a total fee of 20,000 US dollars (USD). Your organization agrees to invoice the customer as you complete specific percentages of the project. You set up the following project categories for the work, so that you can use them in the billing process:

- Consulting
- Design
- Installation

You also set up billing rules that automatically calculate the invoice amounts for the percentage of project work that you complete in each category.

The budget manager creates a budget for the project categories. The system automatically calculates the amount of completed work as a percentage of actual work in comparison to the budgeted amounts.

## Prerequisites

Before you create a project that uses billing rules, set up the number sequences for billing rules and a fee journal that the system uses to post progress billings.

1. Go to **Project management and accounting** \> **Setup** \> **Project management and accounting parameters**.
1. On the **Project management and accounting parameters** page, on the **Number sequences** tab, set up the number sequence that you want to use when creating billing rules.
1. Go to **Project management and accounting** \> **Journals** \> **Fee**.
1. On the **Fee journal** page, select **New**, and enter the journal name.

## Create a contract for progress billings

Use this procedure to create a project contract for a fixed-price project. You create a project invoice when the work that is completed on the project reaches a specified percentage.

1. Go to **Project management and accounting** \> **Projects** \> **Project contracts**.
1. On the **Project contracts** page, select **New**.
1. In the **New project contract** dialog box, set the following fields:

    - **Name**
    - **Funding type**
    - **Funding source**
    - **Sales currency** – By default, this currency is used for customer invoices that are associated with the project contract. However, you can change the sales currency on a specific customer invoice.

1. Select **OK**. The system copies the information to the header of the **Project contracts** page.
1. On the **Project contracts** page, fill in the rest of the required information for the project.

## Create a project for progress billings

Follow these steps to create a project and any subprojects that are associated with a project contract.

1. Go to **Project management and accounting** \> **Projects** \> **All projects**.
1. On the **All projects** page, select **New**.
1. In the **New project** dialog box, in the **Project type** field, select **Time and material**.
1. Select a project group. A project group defines the posting information for the projects that are assigned to the group.
1. Select **Create project**.
1. After the project is created, set the project stage to **In process**.

## Create a budget for a project

Use budget categories to automatically calculate the invoice amounts for the percentage of work that you complete for each category. Follow these steps to create budget categories for the estimated costs.

1. Go to **Project management and accounting** \> **Projects** \> **All projects**.
1. On **All projects**, select and open the project that you want.
1. On **Projects**, on the Action Pane, on the **Plan** tab, in the **Budget** group, select **Project budget**.
1. On **Project budget**, enter an estimated cost for each category in the project.

## Create billing rules for progress billings

1. Go to **Project management and accounting** \> **Projects** \> **Project contracts**.
1. On **Project contracts**, select and open a project contract.
1. On the project contract page, on the **Billing rules** FastTab, select **Add**.
1. On **Billing rule**, in the **Line type** field, select **Progress**.
1. On the **Billing rule line details** FastTab, in the **Contract value** field, enter the total value of the contract.
1. In the **Category** field, select the category to post the fee transaction to.
1. In the **Project** field, select the project that uses this billing rule.
1. (Optional) Assign the billing rule to additional projects. On the **Project** FastTab, in the **Available projects** section, select a project, and then select the right arrow button to add the project to the **Selected projects** section.
1. (Optional) Calculate the percentage amount that the customer withholds from payments on an invoice. On the **Payment retention terms** FastTab, select the funding source, and then, in the **Retention percentage** field, enter the retention percentage.
1. Repeat these steps to create additional billing rules for the project contract.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
