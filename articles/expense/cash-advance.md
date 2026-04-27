---
title: Cash advance
description: Learn how to create, modify, and manage cash advance requests for business expenses. Follow step-by-step instructions to streamline your expense process.
author: mukumarm
ms.author: mukumarm
ms.date: 02/04/2026
ms.topic: how-to
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak

---

# Cash advance

[!INCLUDE[banner](../includes/banner.md)]

_**Applies To:** Project Operations Integrated with ERP_

A cash advance enables employees to borrow money from their company before incurring any expenses. When you approve and pay a requested cash advance, the employee can use the money for business expenses they might incur.

## Create and submit a cash advance request

To create and submit a new cash advance request, follow these steps:

1. Under **My Expenses**, select **Cash advances** > **New**.
1. On the **New cash advance request** page, enter the expense purpose and select the location where the expense occur.
1. Enter the requested amount and currency, and then select **Save**.
1. When you're ready to submit the cash advance request, on the **Cash advance request** page, select **Workflow** > **Submit**.

## Modify a cash advance request

You can modify a cash advance request if you didn't submit it for approval.

1. Under **My Expenses: Cash Advances**, locate and select the cash advance that you want to edit.
1. Select **Edit**, and make the necessary changes to the cash advance request.
1. Select **Save and close**.

## View cash advance requests

You can review the list of all the cash advances that are in draft, submitted, under review, or paid under **My Expenses: Cash Advances**.

## Approve cash advance requests

Managers or users configured as approvers in the workflow can approve the cash advances submitted to them for review.

1. To approve a cash advance, under **Process cash advances**, select **Cash advances for my review**.
1. Select the cash advance you need to review and select **Approve**.  

## Pay cash advances

An accountant or a user with accounting permissions typically completes the following procedure.

1. To post approved cash advances, select **Approved cash advances**, and then select **Pay and transfer**.  
1. Provide the journal details for the cash advances, and then select **OK**.

## Submit an expense report against a paid cash advance

When you create and submit an expense report for the cash advance that you already received, the expenses automatically adjust against that advance. If your cash advance is greater than the expensed amount, you must return the balance to the company by using the **Return cash** expense category. If the company-paid cash advance is less than the amount that you expensed, the company must reimburse you the balance.

### Select cash advances that apply to your expenses

Before you submit an expense report, select the cash advance that aligns with the expense transactions on the report. To use this functionality, enable the following two features from the **Feature management** workspace:

- Expense reports re-imagined
- Ability to map cash advances to expense lines

 When you enable these features:

- You can add one or more cash advances for each expense line.
- You see the available balance of a cash advance in real time when you save an expense report. This feature allows you to process expense transactions and return cash transaction at the same time.
- You can select multiple cash advances for one expense transaction.
- Cash advance reconciliation data is available by using a query.

If you don't use these features, functionality remains the same, with existing cash advances automatically reduced after an expense is submitted.

### Example

You plan to travel from Seattle to New York City for a conference. You create a cash advance request for 3,000 USD based on the estimated cost of the conference ticket, flights, hotel, meals, and taxi. You aren't paid unless your manager approves this request. After your manager approves the request, you receive the cash advance of 3,000 USD in your bank account. You then attend the conference. After completing your trip, you find that the total expenditure was only 2,790 USD. Select **Cash** in the **Payment method** field, and submit your expense for 2,790 USD. Your submitted expense amount automatically adjusts against the cash advance of 3,000 USD that was loaned to you. You now owe a balance of 210 USD (3,000 - 2,790), which you can return to the company by using the **Return cash** expense category.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
