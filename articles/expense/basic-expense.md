---
title: Expense entry (Core deployment - deal to proforma invoicing) 
description: This article provides information about how to work with expense entry in a Core deployment.
author: mohitmenon
ms.date: 05/22/2024
ms.topic: how-to
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak
ms.author: mohitmenon
---

# Expense entry (Core deployment - deal to proforma invoicing)

[!INCLUDE[banner](../includes/banner.md)]

_**Applies to:** Core deployment - deal to proforma invoicing_

Basic, or Core deployment, expense management is the capability to record simple expenses. You can record expenses against a project, and then the project approver reviews and approves them.

For more information about expense capabilities in Dynamics 365 Project Operations, see [Expense overview](expense-overview.md).

## Capture a basic expense

You can capture your expenses so that you can submit them to the approver.

1. Go to **Expenses**, and select **New**.
2. On the **New Expense** page, enter the required expense information, and then select **Save**.

## Submit a basic expense

After you finish capturing all your expenses, and you're ready to approve them, you must submit them.

1. Go to **Expenses**, and select an expense. Or, select all the expenses by using the check box on the header.
2. Select **Submit**. The system processes the selected entries and then creates expense approval requests.

## Add an attachment

You may have to provide the approver with more documentation about your expense. You can attach a receipt in the timeline of the expense entry. Select **Edit** and in the **Timeline** section, and then select the paperclip icon to attach your receipt.

## Recall a basic expense

When you submit an expense by mistake, you can recall it. The time that is required to recall an expense entry depends on its approval stage.  If the approver hasn't yet approved the entry, the recall can occur immediately. However, if the entry has already been approved, the approver is asked to approve the recall and reverse the transactions.

1. Go to **Expenses**, and then, in the list of expenses, select the expense to recall.
2. Select **Recall**. If the expense entry hasn't yet been approved, the system immediately recalls it. If the expense entry has already been approved, a recall request is created to notify the approver that you want to reverse the expense. The approver then confirms that the reversal can be done, and the entry is returned.

## Delete a basic expense

Expenses that haven't yet been submitted can be deleted. To delete an expense that has already been submitted, you must first recall it.

## See also

- [Approvals overview](../approvals/approvals-overview.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
