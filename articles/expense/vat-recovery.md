---
title: VAT recovery in Expense management
description: Learn how to recover VAT in Expense management by identifying, verifying, and submitting eligible transactions. Follow step-by-step guidance for accurate refunds.
author: mukumarm
ms.author: mukumarm
ms.date: 02/04/2026
ms.topic: how-to
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak

---

# VAT recovery in Expense management

[!INCLUDE[banner](../includes/banner.md)]

_**Applies To:** Project Operations Integrated with ERP_

To get refunds on eligible value-added tax (VAT) transactions, a company or organization must identify, collect, verify, and submit accurate information. This process includes multiple tasks and, depending on the size of your company, can include several employees or roles.

To recover VAT in the **Expense management** module, complete the following prerequisites:

- Create tax codes for countries or regions and allocate them to expense categories.
- Create a sales tax group for each tax code.
- Create an item sales tax code for each sales tax group.

After you complete the prerequisites, follow these steps to request refunds for VAT transactions.

1. On an expense report, enter tax information about credit card transactions to identify eligible VAT refunds.
1. Verify that all tax information is complete, and then post the expense report.
1. Process expenses that are eligible for international VAT recovery.
1. Send VAT recovery data to the third-party vendor to file international recovery returns.
1. Process expenses for domestic VAT recovery.

The following sections provide examples that show how Contoso employees complete each step.

## Enter tax information about credit card transactions to identify eligible VAT refunds

Nancy, a Contoso sales representative who is based in the United States, recently returned from a sales trip to the United Kingdom. During the trip, Nancy incurred some personal credit card expenses for meals. Nancy must now create an expense report to reconcile the expenses.

When Nancy enters information on the expense report, she selects **United Kingdom** in the **Country/region** field on the **Edit expense report** page. The list of sales tax groups is then filtered so that it shows only the groups that apply to the United Kingdom. Nancy selects the **United Kingdom 001** sales tax group and then selects the **Meals** item sales tax group. Next, Nancy adds a new transaction for lodging. Because there's only one sales tax group and one item sales tax group for lodging in the United Kingdom, this information is automatically filled in on Nancy's expense report.

Per Contoso policy, all expenses must have a matching receipt. Therefore, on saving the expense report, Nancy receives a message stating that a receipt must be attached for each transaction that she listed on the expense report. Nancy verifies that a digital image of each transaction receipt is attached to the expense report and then submits the report for approval. She then sends the paper receipts to the back-office processing team. This team sends the VAT recovery data to the third-party vendor that files international VAT recovery returns for Contoso.

## Verify tax information and post an expense report

Before April, the Accounts payable coordinator for Contoso, can post an expense report, April must enter any tax information that is missing from it. April opens the **Expense report details** page and sees Nancy's approved expense report. April then opens the expense report to view the details of the transactions. April sees that Nancy didn't enter an item sales tax group for one of the transactions. Because this information isn't provided, April can't post the expense report. Therefore, April looks on the **Tax configurations** page in Expense management, and finds the appropriate item sales tax group for the country/region and the transaction type. April can now post the expense report to the general ledger.

When April posts the expense report, a VAT recoverable work item is created. This work item is assigned to a member of the back-office processing team. April receives a message that confirms that posting was successful. This message also lists the number of VAT transactions that were identified for recovery.

## Process expenses that are eligible for international VAT recovery

Arnie, a member of Contoso's back-office processing team, is responsible for verifying that all the required information for VAT recovery is included on expense reports. Arnie opens the **Expense tax recovery** page and selects the expense report that Nancy submitted. Arnie then verifies that all the required receipts are attached, and that the correct sales tax group and item sales tax codes were entered.

On receiving the paper receipts from Nancy, Arnie verifies them against the digital receipts and then changes the status of the expense report to **Ready for recovery**.

## Send VAT recovery data to the third-party vendor

When Arnie is ready to send the expense report data to the third-party vendor that will file the VAT recovery returns, he opens the **Expense tax recovery** page. Arnie filters the page so that it shows only the expense reports that are marked as **Ready for recovery** and then selects **File** &gt; **Export to Excel**. The VAT information from the expense reports is exported to a Microsoft Excel worksheet. Arnie submits this worksheet to the third-party vendor and includes a message that states that the paper receipts have been sent by courier.

## Process expenses for domestic VAT recovery

Arnie must verify that the expense report transactions are eligible for VAT recovery, and that the digital receipts are attached to the reports. To start processing eligible expenses for domestic recovery, Arnie opens the **Expense tax recovery** page and selects the expense report that requires verification. Arnie verifies that receipts are in the name of the company instead of the employee. For VAT recovery, receipts must be in the name of the company. Arnie then verifies that the correct sales tax group and item sales tax codes are entered.

When Arnie receives the paper receipts, he changes the status of the expense report to **Ready for recovery**. Arnie can then file the return with the appropriate tax authority. In this case, the appropriate tax authority in the United States is the Internal Revenue Service (IRS).

[!INCLUDE[footer-include](../includes/footer-banner.md)]
