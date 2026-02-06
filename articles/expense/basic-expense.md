---
title: Expense entry (Project Operations Core)
description: Learn how to manage expense entries in Project Operations Core. This guide covers capturing, submitting, recalling, and deleting expenses with ease.
author: mohitmenon
ms.date: 02/04/2026
ms.topic: how-to
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak
ms.author: mohitmenon
---

# Expense entry (Project Operations Core)

[!INCLUDE[banner](../includes/banner.md)]

_**Applies to:** Project Operations Core_

In a basic or Core deployment, expense management is the capability to record simple expenses. You can record expenses against a project, and then the project approver reviews and approves them.

For more information about expense capabilities in Dynamics 365 Project Operations, see [Expense overview](expense-overview.md).

## Capture a basic expense

Capture your expenses so that you can submit them to the approver.

To capture a basic expense, follow these steps:

1. Go to **Expenses**, and select **New**.
1. On the **New Expense** page, enter the required expense information, and then select **Save**.

## Submit a basic expense

After you finish capturing all your expenses and you're ready to approve them, submit them.

To submit a basic expense, follow these steps:

1. Go to **Expenses**, and select an expense. Or, select all the expenses by using the check box on the header.
1. Select **Submit**. The system processes the selected entries and then creates expense approval requests.

## Add an attachment

You might need to provide the approver with more documentation about your expense. You can attach a receipt in the timeline of the expense entry. Select **Edit** and in the **Timeline** section, select the paperclip icon to attach your receipt.

## Recall a basic expense

If you mistakenly submit an expense, you can recall it. The time it takes to recall an expense entry depends on its approval stage.  If the approver didn't approve the entry yet, you can recall it immediately. However, if the entry is already approved, the approver needs to approve the recall and reverse the transactions.

To recall a basic expense, follow these steps:

1. Go to **Expenses**, and then, in the list of expenses, select the expense to recall.
1. Select **Recall**. If the expense entry isn't approved yet, the system immediately recalls it. If the expense entry is already approved, the system creates a recall request to notify the approver that you want to reverse the expense. The approver then confirms that the reversal can be done, and the entry is returned.

## Delete a basic expense

You can delete expenses that aren't submitted yet. To delete an expense that you already submitted, you must first recall it.

## See also

- [Approvals overview](../approvals/approvals-overview.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
