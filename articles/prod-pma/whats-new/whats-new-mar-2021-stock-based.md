---
title: What's new or changed in Project Operations, March 2021 for stocked/production-based scenarios
description: This topic provides information about the quality updates available in the March 2021 release of Project Operations for stocked/production based scenarios.
author: andchoi
manager: tfehr
ms.date: 3/16/2021
ms.topic: article
ms.prod:
ms.service: project-operations
ms.reviewer: kfend 
ms.author: andchoi
---

# What's new or changed in Project Operations, March 2021 for stocked/production-based scenarios

_**Applies To:** Project Operations for stocked/production based scenarios_

This topic applies to the following Dynamics 365 Project Operations components and versions:

- Project management and accounting in Dynamics 365 Finance environment version 10.0.17

## Features included in this release
The following features are included in this release:

  - [Project invoice proposal performance](dynamics-365-project-operations-pr/articles/prod-pma/project-invoice-proposal-performance.md)
 
### Quality updates

| Feature area                        | Reference number | Quality update                                                                                                                                                                                                                                                   |
|-------------------------------------|------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Project management and accounting | 420064 | Negative   Project Posted Transactions are not updated after Inventory Recalculation                                                                                                                      |
| Project management and accounting | 438692 | Deletion   of FS should be possible if there is no transaction/invoice allocated with   this FS                                                                                                           |
| Project management and accounting | 439470 | Actual   - Estimate transaction do not display Expense and item transactions from   previous period                                                                                                       |
| Project management and accounting | 452710 | Ledger   description filed is incorrect for the packing slip of project item   requirements                                                                                                               |
| Project management and accounting | 455602 | Financial   dimensions are not picking from Employee and Item Master in voucher while   posting journals against a project.                                                                               |
| Project management and accounting | 472988 | When   edit line net amount in Project Invoice Total sales amount is populated with   adjusted amount in Posted transaction                                                                               |
| Project management and accounting | 477969 | Invoice   not picking the Project ID reference when reviewing the Vendor invoices when   paid when paid                                                                                                   |
| Project management and accounting | 478667 | Incorrect   contract amount in On-account form for a fixed-price project with multiple   funding sources                                                                                                  |
| Project management and accounting | 481443 | FP   project accrued revenue remains un-adjusted after posting elimination                                                                                                                                |
| Project management and accounting | 483209 | Letter   of credit status is not updated when project sales order is invoiced through   invoice proposal                                                                                                  |
| Project management and accounting | 484274 | Customer   receive wrong accounts when invoicing the PO with procurement category and   Item on same invoice                                                                                              |
| Project management and accounting | 484817 | Project   Invoice Proposal via re-occurrence batch jobs creates duplicate transaction   with zero amount                                                                                                  |
| Project management and accounting | 486817 | Remove   error limit check while running Project profit and loss reports                                                                                                                                  |
| Project management and accounting | 488076 | Expenses   posted through IC recharge do not show the P&L entry when using the ‘Post   costs’ functionality on the Time and Material project code                                                         |
| Project management and accounting | 488382 | The   filter for Invoice status in Posted project transactions for Fixed-price   projects does not work                                                                                                   |
| Project management and accounting | 488783 | Duplicate   timesheet entries due to duplicate delegate records                                                                                                                                           |
| Project management and accounting | 491941 | Reverse   estimate elimination is not working in Periodic                                                                                                                                                 |
| Project management and accounting | 498010 | Inability   to get proper selection of data from Adjust transactions option in   PM&Accounting module when an additional range is added (the additional   filter added gets ignored)                      |
| Project management and accounting | 508494 | After   recording the job, it is not possible to reset the status of the production   order.                                                                                                              |
| Project management and accounting | 509716 | Items   with automatic reserve and CTP coming from a Project are not being reserved                                                                                                                       |
| Project management and accounting | 509773 | Accounting   Adjustment Feature in Project Management and Accounting - issue on ledger   accounts set with Do not allow manual entry                                                                      |
| Project management and accounting | 510079 | No   value should be displayed in “ACCRUDE REVENUE – SALES VALUE” in Project   Statements when eliminating the estimation                                                                                 |
| Project management and accounting | 510607 | Cost   and Sales price incorrect when doing a project adjustment with Role pricing                                                                                                                        |
| Project management and accounting | 510728 | [ProjOps]   Retainer correction invoice does not work after partial retainer correction                                                                                                                   |
| Project management and accounting | 510743 | “Remove   link” menu should be disabled unless user cancels ICPO                                                                                                                                          |
| Project management and accounting | 514364 | WIP   - sales value posting in Intercompany project invoicing picks unexpected   account                                                                                                                  |
| Project management and accounting | 514432 | Fee   from billing rule is not recalculated when Invoice proposal contains lines   “selected for credit notes”                                                                                            |
| Project management and accounting | 515820 | Schedule   of Expenditures of Federal Awards Inquiry display Receipts amounts when a   Project Invoice Proposal has not been run for an Expense Transaction                                               |
| Project management and accounting | 516301 | WIP   – Cost is incorrect in project statement for service item and with project   group is set to Balance                                                                                                |
| Project management and accounting | 516553 | Prevent   user from using correct with FTI with project                                                                                                                                                   |
| Project management and accounting | 517074 | Issue   when adjusting project transactions to a sales price of zero - makes new   adjusted transaction with Invoice status = Nonchargeable                                                               |
| Project management and accounting | 517414 | Project   adjustment posting issue while adjusting multiple lines together.                                                                                                                               |
| Project management and accounting | 518001 | Adjustment   posted with incorrect cost amount if product cost price and Item requirement   quantity changes after posting packing slip                                                                   |
| Project management and accounting | 518092 | Direct   Delivery PO Financial Dimensions are Incorrect. (Direct Delivery PO Financial   Dimensions pull in SO Financial Dimensions instead.)                                                             |
| Project management and accounting | 518605 | The   negative quantity project journal line will not update the forecast in case   the forecast quantity is zero.                                                                                        |
| Project management and accounting | 518657 | Cannot   import Item req via Excel: receipt date error                                                                                                                                                    |
| Project management and accounting | 519200 | Project   Item transaction Reference to Vendor Invoice transaction not updated on   Invoice posting                                                                                                       |
| Project management and accounting | 519716 | Project   Invoice proposal posting error: Transaction does not balance on reporting   currency when advance invoice deducted is added                                                                     |
| Project management and accounting | 520268 | Vendor   Payment Retention report does not populate Project ID and Project Name when   using Project layout                                                                                               |
| Project management and accounting | 520872 | Wrong   Ledger posting sort priority when the project is created through data entity                                                                                                                      |
| Project management and accounting | 521150 | Incorrect   cost amount on posted project transactions generated based on PO with vendor   retainage generates incorrect values in Project statements and Cost control   screens for fixed price projects |
| Project management and accounting | 521374 | Project   Sales Quotation Incorrectly updates unit price when change is made to header                                                                                                                    |
| Project management and accounting | 521807 | [ProjOps]   Retainers - Changing default project on contract after invoicing prepayments   messes up the incoming deductions later                                                                        |
| Project management and accounting | 521857 | Update   invoice date for vendor invoice, project sales price is changed                                                                                                                                  |
| Project management and accounting | 522897 | Issues   when adjusting intercompany transactions with different exchange rates   involved                                                                                                                |
| Project management and accounting | 522983 | Committed   costs with Item requirement and Purchase order are wrong in purchase order   invoice process with partly product receipt and partly invoicing                                                 |
| Project management and accounting | 523960 | Incorrect   values when reversing estimate with exchange rate                                                                                                                                             |
| Project management and accounting | 524242 | The   entered Effort in hours is automatically cleared on WBS template task level                                                                                                                         |
| Project management and accounting | 524911 | After   canceling a project quotation and clicking on Lost Quotation, Dynamics   changes the status of All quotations you invited with the status Created and   Sent to Lost incorrectly.                 |
| Project management and accounting | 525182 | Sales   invoice is not visible in invoice proposal if the Delivery date is future   date                                                                                                                  |
| Project management and accounting | 526180 | Change   on business logic for entity Project item journal lines                                                                                                                                          |
| Project management and accounting | 526522 | Intercompany   Customer Invoice Accrued Revenue Doesn't Matched with Timesheet & Foreign   Currency Revaluation Incorrect                                                                                 |
| Project management and accounting | 526650 | Committed   cost is calculated incorrectly after execute delivery reminder on the project   purchase order line which one created from project  purchase   requisition or from project                    |
| Project management and accounting | 526812 | Error   “No Financial data is being updated in the inventory unit” upon Project   adjustment                                                                                                              |
| Project management and accounting | 527319 | [ProjOps]   [Retainers] Removing a project from a contract should reset Default project   of the contract if needed                                                                                       |
| Project management and accounting | 527945 | Wrong   sales price on expense in project when use tax is applied                                                                                                                                         |
| Project management and accounting | 528020 | Wrong   quantity posted on project item requirement, when Project PO line is updated   with more invoices                                                                                                 |
| Project management and accounting | 528212 | [ProjOps]   Intercompany - Wrong expense lines show up in the list to "Add   line" in intercompany invoice                                                                                                |
| Project management and accounting | 529887 | Vendor   Account field is blank in project posted Transaction page if we post   transactions using Invoice register and Invoice approval                                                                  |
| Project management and accounting | 530008 | Original   Project date is not considered in Adjustment which caused error when the   "Use adjustment date as new project date" is No                                                                     |
| Project management and accounting | 530241 | The   Sales price on General journal and Expense journal related to project is   calculated wrongly when the Transaction currency differs from the Company   currency                                     |
| Project management and accounting | 530658 | Sales   transaction not showing up on voucher for partial invoice for project PO                                                                                                                          |
| Project management and accounting | 530883 | Project   accountant, project manager role cannot create hour journal with approval   group setup                                                                                                         |
| Project management and accounting | 531974 | Can't   post Excel imported Expense journal                                                                                                                                                               |
| Project management and accounting | 532106 | Unable   to create a timesheet policy due to message field being grayed out                                                                                                                               |
| Project management and accounting | 532548 | Issue   with Vendor transaction reversal from intercompany scenarios (vendor invoice   and expense reports) - is allowed                                                                                  |
| Project management and accounting | 532692 | Unable   to reset distributions on Approved timesheet                                                                                                                                                     |
| Project management and accounting | 532843 | Incorrect   values when reversing estimate with exchange rate for hour and item journals                                                                                                                  |
| Project management and accounting | 533426 | Project   Adjustment not updating Sales amount correctly with Indirect Costs                                                                                                                              |
| Project management and accounting | 534597 | "The   dimension value is not specified" error when posting hour journal                                                                                                                                  |
| Project management and accounting | 535428 | Project   contract with different currency does not calculate Accounting currency   correctly on the voucher                                                                                              |
| Project management and accounting | 535652 | Wrong   sales WIP account used for Intercompany Timesheet WIP posting                                                                                                                                     |
| Project management and accounting | 536536 | Project   quotation is miscalculating prices when a discount is applied and warehouse   is updated.                                                                                                       |
| Project management and accounting | 537905 | "Recalculation   is being paused because of an error" while running Recalculation after   item cost adjustment used by Project transaction                                                                |
| Project management and accounting | 540622 | No   GL entries get created when adjusting transaction from billable to   non-billable when accruing revenue                                                                                              |
| Project management and accounting | 540633 | ProjTrans   does not get created with pay when paid when feature key Enable cost amount   calculation feature for project vendor invoice retention term is ON                                             |
| Project management and accounting | 541421 | Multiple   issues with Create invoice proposal window                                                                                                                                                     |
| Project management and accounting | 543968 | [ProjOps]   Purchase Agreement form is not visible in F&O legal entities integrated   with Project operations                                                                                             |
| Project management and accounting | 544132 | Unable   to post advanced journal with accounting date in closed period even with   "Automatically set accounting date to next open period" is turned   on                                                |
| Project management and accounting | 545878 | [ProjOps]   Cannot convert quote to won due to DW integration error                                                                                                                                       |
| Project management and accounting | 546604 | [ProjOps]   Error message when trying to create contract line to ProjectId association   because of check for overlapping contract lines/transaction types                                                |
| Project management and accounting | 547440 | ProjCDSProjectContractEntity   can set funding source invoice address from different customer                                                                                                             |
| Project management and accounting | 547606 | Standard   lookup of the resource in standard forms is not coming after 10.0.15 update                                                                                                                    |
| Project management and accounting | 547831 | Ledger   account and posting type is incorrect on GL voucher and posting type wrong on   PO voucher for non-stock service item and with project group is set to   Balance                                 |
| Project management and accounting | 550030 | The   Activity number is not being shown for Pending vendor invoice, even though   the 'Block parent activity selection' is set to No.                                                                    |
| Project management and accounting | 557376 | [ProjOps]   No dimensions get picked up when creating posting invoice for a transaction                                                                                                                   |
| Project management and accounting | 442814 | Project   Management and Accounting, Transfer Price's priority is not accurately   reflected for Intercompany Timesheets                                                                                  |
| Project management and accounting | 533530 | Deprecate   legacy WBS class method   ProjWBSUpdateController::updateOutlineNumbersAndPublishInPreOrder                                                                                                   |

### Regulatory updates
For information about regulatory updates for Finance and Operations apps, see [Regulatory updates](https://docs.microsoft.com/dynamics365/finance/localizations/regulatory-updates). You can also sign in to LCS and view the planned regulatory updates using the Issue search tool. Issue search lets you search by country, type of feature, and release.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
