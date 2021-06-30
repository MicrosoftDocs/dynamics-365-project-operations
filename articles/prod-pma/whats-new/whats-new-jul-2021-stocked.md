---
title: What's new or changed in Project Operations, July 2021 for stocked/production-based scenarios
description: This topic provides information about the quality updates available in the July 2021 release of Project Operations for stocked/production-based scenarios.
author: andchoi
ms.date: 07/01/2021
ms.topic: article
ms.prod:
ms.reviewer: kfend 
ms.author: andchoi
---

# What's new or changed in Project Operations, July 2021 for stocked/production-based scenarios

_**Applies To:** Project Operations for stocked/production based scenarios_

This topic applies to the following Dynamics 365 Project Operations components and versions:

- Project management and accounting in Dynamics 365 Finance environment version 10.0.20
 
### Quality updates
                                                                                                                                                                                  
| Feature area                      | Reference number| Quality update                                                                                                                                                                          |
|-----------------------------------|--------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Project management and   accounting | 485394 | Cost commitment records from PR are cleared as soon as PO is   released from PR issue                                                                           |
| Project management and   accounting | 529602 | Budget validation on Purchase requisition                                                                                                                       |
| Project management and   accounting | 539439 | The Percent to bill on Billing rule could not be completed due   to rounding issue                                                                              |
| Project management and   accounting | 540023 | When we try to adjust the transaction and the percentage has   decimals, the Cost & Sales price is not adjusted correctly.                                      |
| Project management and   accounting | 540927 | Accounting source explorer displays hours for single timesheet   line for multiple timesheet lines with different activity                                      |
| Project management and   accounting | 541471 | Saved Views feature and timesheet line detail personalization   causes system to always open the details for first timesheet when trying to   open a timesheet  |
| Project management and   accounting | 548677 | Project root node disappears and WBS records deleted after   import                                                                                             |
| Project management and   accounting | 548999 | When the items are received and issued partially from the item   requirement, the system update wrong budget consumption balance - Regression   from bug 239215 |
| Project management and   accounting | 550959 | Project Retainage PO’s not showing totals correctly in totals   window or Pending Invoice Grid                                                                  |
| Project management and   accounting | 554593 | When closing inventory, project item cost adjustments are   posted to Balance account instead of P&L                                                            |
| Project management and   accounting | 557394 | Project posted transaction voucher and estimate voucher uses   USD as accounting currency but amount is showing what the CAD equivalent   would be              |
| Project management and   accounting | 560140 | Committed costs with Item requirement and Purchase order are   wrong in purchase order invoice process with partly product receipt and   partly invoicing       |
| Project management and   accounting | 560567 | Project Adjustment not updating Sales amount correctly with   Indirect Costs                                                                                    |
| Project management and   accounting | 561137 | Timesheet table is missing a defined relationship with Worker   Resource view                                                                                   |
| Project management and   accounting | 563330 | Unable to populate Activity number when we select it from the   drop down menu for IC Timesheet                                                                 |
| Project management and   accounting | 563840 | Cannot personalize forms to add Purpose/Activity description   in Project posted transaction form, Invoice proposal creation form and   Invoice proposal form.  |
| Project management and   accounting | 566348 | Wrong delivery date control when creating item requirements   via data management (ProjSalesItemRequirementEntity)                                              |
| Project management and   accounting | 566544 | Project contract ID link to Project Operations                                                                                                                  |
| Project management and   accounting | 567300 | Label ”@SYS4083080” (”Unable to find a unique Worker record   corresponding to the entered values”) is not translated to Danish.                                |
| Project management and   accounting | 569901 | Project operations: Item sales tax group field not editable in   Invoice proposal                                                                               |
| Project management and   accounting | 557049 | Committed cost is overstated with non-deductible tax amounts                                                                                                    |
| Project management and   accounting | 565080 | Posting of intercompany timesheet with multiple projects and   different financial dimensions is generating unexpected values in GL                             |
| Project management and   accounting | 567962 | [ProjOps] Invoice proposal lines get duplicated due to   multiple Import from staging periodic processes running at a time                                      |
| Project management and   accounting | 571339 | Error in credit note Invoice Proposal Posting. The   transactions on voucher XXXXXXX do not balance as per (accounting currency: -   - reporting currency: )    |
| Project management and   accounting | 573567 | Project Committed Costs become incorrect after releasing   on-hold pending invoices                                                                             |
| Project management and   accounting | 573886 | Cannot create a credit note for a Project sales order where   the tax is in a different currency than the company currency                                      |
| Project management and   accounting | 582329 | Deleting a contract also deletes the address associated with   the customer                                                                                     |
| Project management and   accounting | 585811 | [ProjOps] Cannot post invoice proposal resulting from negative   time transaction correction                                                                    |
| Travel and Expense                  | 532075 | Tax calculated differently in expense reports.                                                                                                                  |
| Travel and Expense                  | 546450 | ReleaseUpdateDB72_Expense.updateTrvExpTransProjTransId()   doesn't honor trvExpTrans.ReferenceDataAreaId to create the new Number   Sequence                    |
| Travel and Expense                  | 568805 | Amount filed is not displaying with mandatory field                                                                                                             |
| Travel and Expense                  | 568831 | Performance improvement while attaching expense to the expense   report using Expense Reimagined UI                                                             |
| Travel and Expense                  | 570790 | Expense reports re-imagined: Able to delete posted expense   reports.                                                                                           |
| Travel and Expense                  | 571317 | Expense policy message is being displayed multiple times                                                                                                        |
| Travel and Expense                  | 573969 | Display "Payment method" field on the "New   expense pane"                                                                                                      |
| Travel and Expense                  | 523557 | The 'Reset Expense document status' tool should be able to   reset expense report to draft status if the workflow was not found. 

### Regulatory updates
For information about regulatory updates for Finance and Operations apps, see [Regulatory updates](/dynamics365/finance/localizations/regulatory-updates). You can also sign in to LCS and view the planned regulatory updates using the Issue search tool. Issue search lets you search by country, type of feature, and release.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
