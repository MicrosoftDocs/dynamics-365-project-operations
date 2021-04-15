---
title: What's new or changed in Project Operations, April 2021 for stocked/production-based scenarios
description: This topic provides information about the quality updates available in the April 2021 release of Project Operations for stocked/production-based scenarios.
author: andchoi
manager: tfehr
ms.date: 04/15/2021
ms.topic: article
ms.prod:
ms.service: project-operations
ms.reviewer: kfend 
ms.author: andchoi
---

# What's new or changed in Project Operations, April 2021 for stocked/production-based scenarios

_**Applies To:** Project Operations for stocked/production based scenarios_

This topic applies to the following Dynamics 365 Project Operations components and versions:

- Project management and accounting in Dynamics 365 Finance environment version 10.0.18
 
### Quality updates
                                                                                                                                                                                                                                                 |
| Feature area                      | Reference number| Quality update                                                                                                                                                                          |
|-----------------------------------|--------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Project management and accounting | 534393 | Project sorting grid error                                                                                                                                                      |
| Project management and accounting | 542850 | Committed Amount is overstated after correcting the unit price and   quantity on a Project PO                                                                                   |
| Project management and accounting | 543645 | ProjParameters variable declared but never assign a record buffer to it   before using it                                                                                       |
| Project management and accounting | 543674 | Delete ResRollup tables when 'Populate project resources across all   companies' batch job is executed                                                                          |
| Project management and accounting | 544417 | Issue updating Project Sales price field on purchase order via the   ‘Purchase order lines V2’ entity                                                                           |
| Project management and accounting | 547652 | Subprojects could not be created depending on the numbers in the ID.   Error: “Function Global::int642int has been incorrectly called."                                         |
| Project management and accounting | 484274 | Customer receive wrong accounts when invoicing the PO with procurement   category and Item on same invoice                                                                      |
| Project management and accounting | 509920 | Adjusting a Project Transaction with Indirect Costs from billable to   non-billable and back to billable is not clearing the WIP properly                                       |
| Project management and accounting | 511274 | Invoice amounts are incorrect when using retention and total discount in   sales order                                                                                          |
| Project management and accounting | 511315 | Address Name in Line details is not changed even when we select different   Transaction type in Lines                                                                           |
| Project management and accounting | 522983 | Committed costs with Item requirement and Purchase order are wrong in   purchase order invoice process with partly product receipt and partly   invoicing                       |
| Project management and accounting | 524226 | Incorrect Financial Dimensions on PO header, when Project FinDim are   changed                                                                                                  |
| Project management and accounting | 524979 | [Project] - The fixed price project report is being generated in blank.                                                                                                         |
| Project management and accounting | 529445 | Invoice not picking the Project ID reference when reviewing the Vendor   invoices when paid when paid                                                                           |
| Project management and accounting | 529982 | Timesheet entry incorrect for user with access restricted for one legal   entity on “HR manager” role – category not defaulted properly                                         |
| Project management and accounting | 530008 | Original Project date is not considered in Adjustment which caused error   when the "Use adjustment date as new project date" is No                                             |
| Project management and accounting | 530788 | Project Estimates when calculated through batch gives incorrect results                                                                                                         |
| Project management and accounting | 530834 | The ‘Spent amount’ on the project contract is not aligned to the   On-account amount on the project                                                                             |
| Project management and accounting | 530883 | Project accountant, project manager role cannot create hour journal with   approval group setup                                                                                 |
| Project management and accounting | 531974 | Can't post Excel imported Expense journal                                                                                                                                       |
| Project management and accounting | 532548 | Vendor transaction reversal from intercompany scenarios (vendor invoice   and expense reports) - is allowed                                                                     |
| Project management and accounting | 533426 | Project Adjustment not updating Sales amount correctly with Indirect   Costs                                                                                                    |
| Project management and accounting | 534869 | When a credit note for a Fixed-priced project invoice with the use of   unit of delivery billing rule gets created, the released units are no longer   available for rebilling. |
| Project management and accounting | 535428 | Project contract with different currency does not calculate Accounting   currency correctly on Item journal/Invoice proposal.                                                   |
| Project management and accounting | 537158 | Change project on PO line to transfer item requirement                                                                                                                          |
| Project management and accounting | 540603 | Import to project budget from forecast has incorrect amounts                                                                                                                    |
| Project management and accounting | 540622 | No GL entries get created when adjusting transaction from billable to   non-billable                                                                                            |
| Project management and accounting | 540633 | ProjTrans does not get created with pay when paid when feature key Enable   cost amount calculation feature for project vendor invoice retention term is   ON                   |
| Project management and accounting | 541421 | Multiple issues with Create invoice proposal window                                                                                                                             |
| Project management and accounting | 543390 | “ALL Project” form doesn’t show the list with the new language code.                                                                                                            |
| Project management and accounting | 543803 | Wrong unapproved budget amount in the project budget balance screen when   the budget is revised more than twice                                                                |
| Project management and accounting | 543968 | Purchase Agreement form is not visible in F&O legal entities   integrated with Project operations                                                                               |
| Project management and accounting | 545456 | Project Hours Journal Lines does not upload the correct voucher date                                                                                                            |
| Project management and accounting | 545878 | Project Operations for Resource based scenarios: Cannot convert quote to   won due to DW integration error                                                                      |
| Project management and accounting | 546604 | [ProjOps] Error message when trying to create contract line to ProjectId   association because of check for overlapping contract lines/transaction types                        |
| Project management and accounting | 546949 | Resource/project validation groups form perform poorly with 14,000+   records in ProjValEmplProjSetup table                                                                     |
| Project management and accounting | 547440 | ProjCDSProjectContractEntity can set funding source invoice address from   different customer                                                                                   |
| Project management and accounting | 547606 | Standard lookup of the resource in standard forms is not coming after   10.0.15 update                                                                                          |
| Project management and accounting | 547831 | Ledger account and posting type in PO invoice voucher is mismatch for   service item and with project group is set to Balance, ledger account is   incorrect.                   |
| Project management and accounting | 550030 | The Activity number is not being shown for Pending vendor invoice, even   though the 'Block parent activity selection' is set to No.                                            |
| Project management and accounting | 550379 | System creating project budget revisions for all projects, when using   path Project> Budget > Revisions> New> Import                                                           |
| Project management and accounting | 550577 | Wrong posting and GL entries when adjusting a transaction with different   trans and accounting currency                                                                        |
| Project management and accounting | 557376 | No dimensions get picked up when creating posting invoice for a   transaction                                                                                                   |
| Project management and accounting | 559416 | PurchTotals.purchNewTotalAmount() method is calling when creating Pending   vendor invoice which was not linked with any PO which causes performance   issue                    |
| Travel and Expense                | 480451 | Posting error related to mileage setup                                                                                                                                          |
| Travel and Expense                | 522084 | Split to personal for foreign currency expense transactions not working                                                                                                         |
| Travel and Expense                | 523938 | Expense category dropdown values are displaying incorrect categories if   delegates is a resource or even if delegate is NOT a resource                                         |
| Travel and Expense                | 539266 | Intercompany Expense Report cannot save due to Resource/Category   validation error                                                                                             |
| Travel and Expense                | 532610 | Wrong Mileage rate calculation in expense report posting has split lines                                                                                                        |
| Travel and Expense                | 537404 | Cannot post intercompany expense report when sales tax is included and   offset account type on the payment method is Worker                                                    |
| Travel and Expense                | 542927 | Rollback TrvRequisitionLine Data Entity and unique index associated to   the entity.                                                                                            |
| Travel and Expense                | 543239 | Instrumentation for expense report to support source document line   creation/upating                                                                                           |
| Travel and Expense                | 544323 | Incorrect subledger journal is presented to end user in Intercompany   scenario if Sales tax is posted to Destination legal entity                                              |
| Travel and Expense                | 546877 | [ProjOps] Expense Estimate is not getting deleted from FnO when deleted   from CE side.                                                                                         |
| Travel and Expense                | 550575 | When Expense category is Non-Project category, financial dimensions   selected on Expenses page does not get copied to Expense Report.                                          |

### Regulatory updates
For information about regulatory updates for Finance and Operations apps, see [Regulatory updates](https://docs.microsoft.com/dynamics365/finance/localizations/regulatory-updates). You can also sign in to LCS and view the planned regulatory updates using the Issue search tool. Issue search lets you search by country, type of feature, and release.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
