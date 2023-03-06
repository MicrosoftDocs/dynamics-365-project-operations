---
# required metadata

title: Post expense reports
description: This article explains how to post expense reports.
author: ramagadu
ms.date: 08/12/2022
ms.topic: article
ms.prod: 
#

# optional metadata

ms.search.form: 
audience: Application User
# ms.devlang: 
ms.reviewer: johnmichalak
ms.search.scope: 
# ms.tgt_pltfrm: 
# ms.custom: 
ms.search.region: 
# ms.search.industry: 
ms.author: shylaw
ms.search.validFrom: 
ms.dyn365.ops.version: 
---

# Post expense reports

After an expense report has been approved and transferred to the general journal, it can be posted. When you post an expense report, expenses that are eligible for recovery of value-added tax (VAT) are identified. The task of verifying and recovering VAT payments is assigned to the employee who is responsible for verifying the expense report.

If expenses on an expense report are charged to a company other than the company that employs the employee, you must verify both the company that those expenses are owed to and the company that they are owed from. For example, the employee who submitted an expense report works for the DAT company but charged an expense to the DIR company. In this case, DAT is the company that the expense is owed to, and DIR is the company that the expense is owed from. After you verify these journal lines, you can post the expense lines to the general ledger.

To post an expense report, on the **Approved expense reports** page, select the expense report, and then, on the Action Pane, select **Post**.

You can also post all the expense reports in the list at the same time. Select all the expense reports, and then select **Post**.

## Enable the Ability to post expense liability in vendor currency for cash payment method feature

The **Ability to post expense liability in vendor currency for cash payment method** feature enables expense reports to be posted in a vendor currency for the cash payment method.

Currently, when you submit cash expenses, expense reports are posted in the accounting currency. Because of amount conversion among the transaction currency, accounting currency, and vendor currency, an incorrect amount is paid to vendors if the transaction date of the expense and the actual payment date have different exchange rates.

This feature will ensure that the vendor balance is recorded in the vendor currency when the expense report is posted.

1. Go to **Workspaces** \> **Feature Management**.
2. In the list, find and select **Ability to post expense liability in vendor currency for cash payment method**, and then select **Enable now**.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
