---
title: What's new or changed in Project Operations, October 2021 for stocked/production-based scenarios
description: This topic provides information about the quality updates available in the October 2021 release of Project Operations for stocked/production-based scenarios.
author: andchoi
ms.date: 10/01/2021
ms.topic: article
ms.prod:
ms.reviewer: kfend 
ms.author: andchoi
---

# What's new or changed in Project Operations, October 2021 for stocked/production-based scenarios

_**Applies To:** Project Operations for stocked/production based-scenarios_

This topic applies to the following Dynamics 365 Project Operations components and versions:

- Project management and accounting in Dynamics 365 Finance environment version 10.0.22
 
### Quality updates
                                                                                                                                                                                  
| Feature area                              | Reference number     | Quality update                                                                                                                                                                               |
|-----------------------------------|--------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Project management and accounting | 557017 | Project WIP/Accrued revenue amounts are not reversed properly once   intercompany customer invoice is posted                                                                        |
| Project management and accounting | 558232 | Prevent project closure if open transactions exist” is not working                                                                                                                  |
| Project management and accounting | 559271 | Free Text Invoice – Billing Classification does not auto   populate dimensions from Projects when enabled                                                                           |
| Project management and accounting | 574013 | WIP/Accrued revenue amounts are not reversed properly once project   invoice is posted (non intercompany scenario)                                                                  |
| Project management and accounting | 577857 | Debits and credits switch using Excel Add-In with Project Expense Journal   and Offset Account Type set to Project                                                                  |
| Project management and accounting | 577972 | Amount in posted project transactions is overstated in a project purchase   order with stocked items and with non-deductible tax amounts when UseTax is   marked                    |
| Project management and accounting | 581216 | System is splitting the amount between project Profit and Loss and   Project WIP reports.                                                                                           |
| Project management and accounting | 582065 | On-hand is incorrect after adjusting partially returned item requirement                                                                                                            |
| Project management and accounting | 582682 | Resource names are duplicating on D365 when edited in MS Project                                                                                                                    |
| Project management and accounting | 583873 | Intercompany cost Posting type issue with AP Pending vendor invoice on   Projects with Project group having Post costs to Balance and Line property   set to Capitalize costs = YES |
| Project management and accounting | 584732 | Vendor retainage results in project expense transactions not showing up                                                                                                             |
| Project management and accounting | 587453 | Timesheet needs to round amount in transaction currency to X decimals on   Accounting distributions and GJAE entries.                                                               |
| Project management and accounting | 589409 | Quantities of Project Item requirements are updated automatically when   the planned orders are firmed.                                                                             |
| Project management and accounting | 590206 | PO Prepayment invoice is not able to remove. Voucher number***,   transaction type Vendor balance, and account number*** can't be reversed.                                         |
| Project management and accounting | 593068 | Intercompany vendor invoice is broken when vendor invoice integration is   turned on                                                                                                |
| Project management and accounting | 593335 | While creating Project expense journal - cost amount showing in credit   field.                                                                                                     |
| Project management and accounting | 593382 | The Terms of payment on the Project Invoices doesn't work as expected                                                                                                               |
| Project management and accounting | 593565 | Timesheet vouchers might be reused in continuous number sequence setup                                                                                                              |
| Project management and accounting | 593652 | FRANCE - Manual retention amount logic doesn't match the Automatic   retention amount logic in Project Contract Invoice proposal                                                    |
| Project management and accounting | 596263 | Project Management - When releasing vendor retention the voucher posting   has incorrect additional lines                                                                           |
| Project management and accounting | 596650 | Changing 'Invoice date' field in the 'Create invoice proposal' form may   cause 'Object reference not set to an instance of an object' error'.                                      |
| Project management and accounting | 597679 | Violation error is received, when you try to approve Timesheet from   TSLine workflow and there is a TS policy for Saturday and Sunday.                                             |
| Project management and accounting | 597801 | Beginning balance project item type is excluded from the "Invoice   proposal transaction summaries" when calculating the Invoice proposal   invoice amount total.                   |
| Project management and accounting | 597886 | "Attempted to divide by zero" error when estimating Project   production order if consumption cost = 0                                                                              |
| Project management and accounting | 598706 | Project Timesheet Mobile Android - TimeEntryDataManager   ArgumentNullException                                                                                                     |
| Project management and accounting | 598758 | Project Operations integration journal fails on posting due to missing   dimensions for an account that is not being posted to                                                      |
| Project management and accounting | 598929 | ToDate filter is not cleared on search when removed from Post Cost form   Select dialog                                                                                             |
| Project management and accounting | 599757 | Reset all distribution failed with error for the timesheets that are   created for Time only type project.                                                                          |
| Project management and accounting | 602650 | Project tab is not editable on pending vendor invoice when the   Procurement category is assigned to the Item                                                                       |
| Project management and accounting | 605121 | [ProjOps] Navigation pane missing if not logged in Project Operations   Dataverse                                                                                                   |
| Project management and accounting | 546467 | Intercompany project adjustment transaction issue in destination company                                                                                                            |
| Project management and accounting | 563579 | Project committed costs calculate the wrong quantity and cost price if   the purchase order was processed by the Purchase Order Year End Process in   General Ledger                |
| Project management and accounting | 581454 | Error when report as finished project production order with quality   orders "No virtual transaction marked with inventory transaction"                                             |
| Project management and accounting | 596408 | "Enumerated text Project - cost - item does not exist" error is   appearing when a project related AP Invoice is posted.                                                            |
| Project management and accounting | 597237 | Indirect Costs are doubled when manually accruing revenue                                                                                                                           |
| Project management and accounting | 601198 | Accrue revenue / WIP posting does not result in transactions                                                                                                                        |
| Project management and accounting | 602095 | Activation of pending price failed for standard cost item when received   project purchase order exists                                                                             |
| Project management and accounting | 602677 | The WIP reversed value from Invoice posting is different than the   original posted WIP value from time entry                                                                       |
| Project management and accounting | 602728 | Project invoiced revenue posting issue in applied retainer case:   transactions on voucher do not balance                                                                           |
| Project management and accounting | 603624 | [ProjOps] Estimate creation after posting invoice proposal blocks import   of correction lines                                                                                      |
| Project management and accounting | 606083 | Modifying full invoiced milestone record must not be possible                                                                                                                       |
| Project management and accounting | 611389 | Intercompany customer invoice for timesheet cannot be posted with error   message when automatic charges are used                                                                   |
| Project management and accounting | 612991 | Address not updating correctly on subproject                                                                                                                                        |
| Project management and accounting | 613418 | Item Requirements cost price updated with Purchase price for consolidated   Purchase orders                                                                                         |
| Project management and accounting | 614145 | The Posted cost not correct after the purchase price updated and Enable   the Activate change management                                                                            |
| Travel and Expense                | 575305 | Able to see everyone's expense when searching for a category on the   mobile app                                                                                                    |
| Travel and Expense                | 583101 | Incorrect amounts on Vendor transaction and Sales tax transaction posted   from Expense created from Credit card transaction                                                        |
| Travel and Expense                | 583760 | Expense Report - Irrelevant warning message pop up after refreshing the   expense report pages                                                                                      |
| Travel and Expense                | 598656 | wrong interim approve is used when you delete an interim approve and   re-submit through Workflow                                                                                   |
| Travel and Expense                | 612742 | Posting error related to mileage setup                                                                                                                                              |
| Travel and Expense                | 620773 | Intercompany expense lines - Distribution does not update Legal Entity   when unattached transaction is re-added to expense report                                                  |

### Regulatory updates
For information about regulatory updates for Finance and Operations apps, see [Regulatory updates](/dynamics365/finance/localizations/regulatory-updates). You can also sign in to Lifecycle Services (LCS) and view the planned regulatory updates using the Issue search tool. Issue search lets you search by country, type of feature, and release.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
