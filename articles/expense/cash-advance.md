---
title: Cash advance
description: Learn how to create, modify, and manage cash advance requests for business expenses. Follow step-by-step instructions to streamline your expense process.
author: ajitchandran
ms.author: ajitchandran
ms.date: 04/27/2026
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

## Cash Advance Exchange Rate Adjustments (Preview)

### Overview

The **Manage cash advance rate adjustments (Preview)** feature introduces exchange‑rate‑aware settlement logic for cash advances used in expense reporting. It resolves reconciliation and accounting issues that arise when cash advances and expenses are posted on different dates or in different currencies.

This feature ensures that:
- Cash advances are settled based on **transaction currency**, not only accounting currency.
- **Realized foreign exchange (FX) gains or losses** are explicitly calculated and posted.
- Employee (vendor) accounts always net to zero after settlement.
- Finance teams gain clear visibility and auditability into exchange rate variances.

### Business Problem

In the existing implementation, cash advance settlement is driven primarily by accounting currency values, without sufficient awareness of transaction currency or exchange rate timing.

Customers using foreign‑currency cash advances experience:

- Incorrect remaining cash advance balances
- Vendor (employee) accounts carrying balances that should not exist
- Missing realized FX gain/loss postings

### Feature Enablement

The **(Preview) Manage cash advance rate adjustments** feature can be enabled only when:

- **Mapping cash advances to expense lines** is enabled
- **No partially mapped cash advances** exist in the system
  
To enable the feature, go to **Feature Management** > search for **(Preview) Manage cash advance rate adjustments** > click **Enable**

## End‑to‑End Walkthrough

### Example Scenario

**Cash Advance**
- 100 EUR  
- Accounting currency equivalent: 140 USD

**Expense**
- 100 EUR  
- Accounting currency equivalent: 150 USD

### Settlement Behavior

- The expense is mapped to the cash advance in **transaction currency (EUR)**.
- The accounting currency difference (150 USD – 140 USD = 10 USD) is:
  - Recognized as a **realized FX loss**
  - Posted to the configured FX loss account
- Vendor balance nets to **zero**
- Cash advance balance is fully cleared in EUR

---

## Exchange Rate Handling Scenarios

### Case 1: Cash Advance and Expense in Accounting Currency
- ✅ No exchange rate variance generated

### Case 2: Expense in Accounting Currency
- ✅ No exchange rate variance generated

### Case 3: Same Transaction Currency (Not Accounting Currency)
- Exchange rate variance can occur due to **different posting dates**

### Case 4: Different Transaction Currencies (Neither Is Accounting Currency)
- Exchange rate variance is calculated using:
  - Cash advance posting date exchange rate
  - Expense transaction date exchange rate
- ❌ Mapping is **blocked** if required exchange rates are missing

---

## User Experience (UI Design)

### Cash Advance Visibility
- Cash advance balances are displayed in **cash advance currency**

### Exchange Rate Indicators
- A **visual indicator** is shown when:
  - Exchange rates differ between cash advance and expense
- No indicator is shown when:
  - Exchange rates match

---


## Accounting and Voucher Behavior

- Separate voucher lines are created for:
  - Expense settlement
  - Realized FX gain or loss
- Voucher descriptions include:
  - Cash advance number
  - Expense report number
- Vendor (employee) account always nets to **zero**

---

## Auditability and Traceability

- **Related vouchers** navigation opens the expense voucher
- **Original document** navigation opens expense line details
- Clear linkage between:
  - Cash advance
  - Expense report
  - FX variance posting

This ensures:
- Strong audit trails
- Easier reconciliation
- Reduced manual corrections

---



## Summary

The **Cash Advance Exchange Rate Variance** feature:

- Fixes incorrect foreign‑currency cash advance settlement
- Ensures accurate FX gain/loss recognition
- Eliminates residual vendor balances
- Improves transparency, auditability, and reconciliation
- Reduces finance team manual effort


[!INCLUDE[footer-include](../includes/footer-banner.md)]
