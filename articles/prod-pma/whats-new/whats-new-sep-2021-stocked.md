---
title: What's new or changed in Project Operations, September 2021 for manufacturing-based scenarios
description: This article provides information about the quality updates that are available in the September 2021 release of Project Operations for manufacturing-based scenarios.
author: andchoi
ms.custom:
  - evergreen
ms.date: 04/09/2024
ms.topic: whats-new
ms.reviewer: johnmichalak
ms.author: andchoi
---

# What's new or changed in Project Operations, September 2021 for manufacturing-based scenarios

_**Applies To:** Project Operations for manufacturing based-scenarios_

This article applies to the following components and versions of Microsoft Dynamics 365 Project Operations:

- Project management and accounting in a Dynamics 365 Finance environment version 10.0.21
 
## Quality updates

| Feature area | Reference number | Quality update |
|---|---|---|
| Project management and accounting | [412077](https://fix.lcs.dynamics.com/Issue/Details/?bugId=412077) | If the Purchase manager role is given access to one legal entity, it also gains access to all projects in all legal entities. |
| Project management and accounting | [537214](https://fix.lcs.dynamics.com/Issue/Details/?bugId=537214) | A value-added tax (VAT) rounding issue occurs while a credit note is settled against an original project invoice. |
| Project management and accounting | [538002](https://fix.lcs.dynamics.com/Issue/Details/?bugId=538002) | Use an alternate project budget for budget verification. |
| Project management and accounting | [546265](https://fix.lcs.dynamics.com/Issue/Details/?bugId=546265) | The **Sales price hour** price group isn't calculated on the work breakdown structure for project quotations. |
| Project management and accounting | [555604](https://fix.lcs.dynamics.com/Issue/Details/?bugId=555604) | Estimate elimination fails when the **Enable project contract currency for estimate calculation** feature is enabled. |
| Project management and accounting | [563523](https://fix.lcs.dynamics.com/Issue/Details/?bugId=563523) | Sales tax factorization by quantity is added to the sales price amount when use tax is used on the sales tax group of the Project expense journal. |
| Project management and accounting | [564701](https://fix.lcs.dynamics.com/Issue/Details/?bugId=564701) | Conditional tax isn't calculated correctly for the last payment when vendor retention and prepayment are applied to purchase order invoices. |
| Project management and accounting | [565642](https://fix.lcs.dynamics.com/Issue/Details/?bugId=565642) | Adjustment trace doesn't work for Beginning balance journals. |
| Project management and accounting | [568814](https://fix.lcs.dynamics.com/Issue/Details/?bugId=568814) | **Project budget revision allocation by period** is split across all budget periods. When the allocation is submitted, the record isn't cleared. |
| Project management and accounting | [569250](https://fix.lcs.dynamics.com/Issue/Details/?bugId=569250) | Work in process (WIP) postings to the general ledger have an incorrect amount. |
| Project management and accounting | [570731](https://fix.lcs.dynamics.com/Issue/Details/?bugId=570371) | Approval of the Project hour journal doesn't work. |
| Project management and accounting | [571391](https://fix.lcs.dynamics.com/Issue/Details/?bugId=571391) | The project adjustment sales price isn't updated with indirect costs when the funding limit is unmarked. |
| Project management and accounting | [575831](https://fix.lcs.dynamics.com/Issue/Details/?bugId=575831) | An item requirement can't be created when the Sales table header is invoiced and the backing purchase order for existing lines has been finalized. |
| Project management and accounting | [578036](https://fix.lcs.dynamics.com/Issue/Details/?bugId=578036) | The retention amount for a billing rule that has a milestone for a different project isn't posted in the corresponding project ID that was selected for the milestone. Instead, it's posted with the first project. |
| Project management and accounting | [578327](https://fix.lcs.dynamics.com/Issue/Details/?bugId=578327) | When you select **Financial dimension set** on an invoice proposal, the following error occurs: "Unable to cast object of type 'Dynamics.AX.Application.FormIntControl' to type 'Dynamics.AX.Application.FormStringControl'." |
| Project management and accounting | [581167](https://fix.lcs.dynamics.com/Issue/Details/?bugId=581167) | The **Project invoice** report skips lines. |
| Project management and accounting | [581489](https://fix.lcs.dynamics.com/Issue/Details/?bugId=581489) | An error occurs when you calculate the cost control for an investment project. |
| Project management and accounting | [590357](https://fix.lcs.dynamics.com/Issue/Details/?bugId=590357) | The **ProjTable::InitFromCustTable - canDeletePostalAddress** method causes a performance issue. |
| Project management and accounting | [592493](https://fix.lcs.dynamics.com/Issue/Details/?bugId=592493) | The error message should be clearer than "Unexpected error." |
| Project management and accounting | [598810](https://fix.lcs.dynamics.com/Issue/Details/?bugId=598810) | The Project invoice posting batch job processes and posts the invoice proposal even if the invoice lines haven't been generated. |
| Project management and accounting | [574282](https://fix.lcs.dynamics.com/Issue/Details/?bugId=574282) | A rounding issue occurs when the Public sector license configuration key is turned off. An incorrect cost or sales price is generated on the timesheet hours for contracts that have multiple founding sources. |
| Project management and accounting | [577598](https://fix.lcs.dynamics.com/Issue/Details/?bugId=577598) | The project sales price on an invoiced project purchase order is incorrectly calculated when the sales price model is **Contribution ratio**. |
| Project management and accounting | [580784](https://fix.lcs.dynamics.com/Issue/Details/?bugId=580784) | The system doesn't consider the active days in between when it calculates the effective labor rate for an employee. |
| Project management and accounting | [584054](https://fix.lcs.dynamics.com/Issue/Details/?bugId=584054) | A posting error occurs on the intercompany timesheet because of the following validation error: "No trading partner is configured for legal entity." |
| Project management and accounting | [586303](https://fix.lcs.dynamics.com/Issue/Details/?bugId=586303) | The description from a purchase order that has an expense category isn't retrieved in the posted project transaction list. |
| Project management and accounting | [590349](https://fix.lcs.dynamics.com/Issue/Details/?bugId=590349) | There is an incorrect conversion on Item journals that are posted to a project. |
| Project management and accounting | [557294](https://fix.lcs.dynamics.com/Issue/Details/?bugId=557294) | You can confirm a purchase order even if the funding limit has been exceeded. |
| Project management and accounting | [574162](https://fix.lcs.dynamics.com/Issue/Details/?bugId=574162) | The **Correction/Cancel invoice** section on a free text invoice disappears when a project ID is selected. |
| Project management and accounting | [575425](https://fix.lcs.dynamics.com/Issue/Details/?bugId=575425) | There are performance issues when a project invoice proposal is posted from a project sales order that includes a stocked item. |
| Project management and accounting | [575939](https://fix.lcs.dynamics.com/Issue/Details/?bugId=575939) | Project purchase invoices can't be posted because the following error occurs: "Function AccDistProcessorProjectExtension.createForProjectRevenueLine has been incorrectly called." |
| Project management and accounting | [578970](https://fix.lcs.dynamics.com/Issue/Details/?bugId=578970) | Update to the creation of project estimate batch jobs to support execution of multiple subtasks. |
| Project management and accounting | [584519](https://fix.lcs.dynamics.com/Issue/Details/?bugId=584519) | The status of a timesheet can't be updated to **Draft** when the workflow is stuck in a **Canceled** state. |
| Project management and accounting | [584757](https://fix.lcs.dynamics.com/Issue/Details/?bugId=584757) | Retention amounts aren't calculated in the credit note invoice proposal if multiple lines exist. |
| Project management and accounting | [586034](https://fix.lcs.dynamics.com/Issue/Details/?bugId=586034) | When you try to change the amount on a generated invoice from a purchase order, the following error occurs: "The transactions on voucher don't balance as per XX/XX/XXXX. (accounting currency: 0.00 - reporting currency: 0.01)." |
| Project management and accounting | [588714](https://fix.lcs.dynamics.com/Issue/Details/?bugId=588714) | There is a performance issue when a project invoice proposal is posted in batch mode, because of the join with **GeneralJournalAccountEntry**. |
| Project management and accounting | [588851](https://fix.lcs.dynamics.com/Issue/Details/?bugId=588851) | There are performance issues when a timesheet is posted. |
| Project management and accounting | [590535](https://fix.lcs.dynamics.com/Issue/Details/?bugId=590535) | The cost estimates hierarchy of the work breakdown structure isn't correctly aligned after all tasks are expanded or after a single task is manually expanded. |
| Project management and accounting | [593663](https://fix.lcs.dynamics.com/Issue/Details/?bugId=593663) | The project quotation Excel template can't be added to the **Open in Excel** menu. |
| Project management and accounting | [596669](https://fix.lcs.dynamics.com/Issue/Details/?bugId=596669) | The tax-exempt number for a legal entity isn't included on the printed project invoice. |
| Project management and accounting | [597563](https://fix.lcs.dynamics.com/Issue/Details/?bugId=597563) | No financial data is updated in the inventory unit error when a project is adjusted in relation to credit lines. |
| Project management and accounting | [598109](https://fix.lcs.dynamics.com/Issue/Details/?bugId=598109) | After you apply KB 461935, you can't post estimates if you switch to continuous number sequences. |
| Project management and accounting | [598688](https://fix.lcs.dynamics.com/Issue/Details/?bugId=598688) | **TimeEntryDataManager** causes the Project timesheet mobile app for Android to stop responding. |
| Project management and accounting | [602677](https://fix.lcs.dynamics.com/Issue/Details/?bugId=602677) | The WIP-reversed value from an invoice posting differs from the originally posted WIP value from the time entry. |
| Project management and accounting | [602728](https://fix.lcs.dynamics.com/Issue/Details/?bugId=602728) | In applied retainer cases, the transactions on a voucher don't balance when invoiced revenue for a project is posted. |
| Project management and accounting | [603320](https://fix.lcs.dynamics.com/Issue/Details/?bugId=603320) | When the **Project resource scheduling performance enhancement** feature is enabled, decimal values are incorrectly rounded for resource availability and capacity. |
| Project management and accounting | [607324](https://fix.lcs.dynamics.com/Issue/Details/?bugId=607324) | When the **Create project estimates using multiple batch tasks** feature is enabled, creation of estimates in a batch that has multiple subtasks works only for the current period. |
| Travel and Expense | [551911](https://fix.lcs.dynamics.com/Issue/Details/?bugId=551911) | A travel requisition policy is ignored, and the workflow is approved without errors. |
| Travel and Expense | [563752](https://fix.lcs.dynamics.com/Issue/Details/?bugId=563752) | <p>The Mobile Expense app doesn't save the following information on the expense line:</p><ul><li>The project ID</li><li>Whether the expense is billable</li><li>The activity number</li></ul> |
| Travel and Expense | [569458](https://fix.lcs.dynamics.com/Issue/Details/?bugId=569458) | The **Attached receipts** field is set to **Yes** even if no receipt is attached to the expense line. |
| Travel and Expense | [571334](https://fix.lcs.dynamics.com/Issue/Details/?bugId=571334) | An error occurs when you change the expense category to **Personal**. |
| Travel and Expense | [572783](https://fix.lcs.dynamics.com/Issue/Details/?bugId=572783) | You can't attach a receipt and edit the parent expense after a credit card transaction is split to a personal expense. |
| Travel and Expense | [574252](https://fix.lcs.dynamics.com/Issue/Details/?bugId=574252) | The expense policy for intercompany transactions that have a project ID doesn't work correctly. |
| Travel and Expense | [574489](https://fix.lcs.dynamics.com/Issue/Details/?bugId=574489) | The posted date information is missing for posted expense reports. |
| Travel and Expense | [574504](https://fix.lcs.dynamics.com/Issue/Details/?bugId=574504) | There are payment method issues in the Expense mobile app. |
| Travel and Expense | [584799](https://fix.lcs.dynamics.com/Issue/Details/?bugId=584799) | A travel requisition that is created for one worker can be used for another worker's expense report before the delegate date. |
| Travel and Expense | [586023](https://fix.lcs.dynamics.com/Issue/Details/?bugId=586023) | When you create an expense, changes to the financial dimension values aren't correctly updated at the accounting distribution level in the **Expense management** workspace. |
| Travel and Expense | [586081](https://fix.lcs.dynamics.com/Issue/Details/?bugId=586081) | The main expense line approval status isn't synced with the itemized line workflow approval status. |
| Travel and Expense | [590544](https://fix.lcs.dynamics.com/Issue/Details/?bugId=590544) | An error occurs if you post an expense report and tax recovery is enabled. |
| Travel and Expense | [564851](https://fix.lcs.dynamics.com/Issue/Details/?bugId=564851) | A delegate can't delete expense documents for a terminated employee. |
| Travel and Expense | [587306](https://fix.lcs.dynamics.com/Issue/Details/?bugId=587306) | Deletion of an expense line takes longer than expected and affects performance. |
| Travel and Expense | [600455](https://fix.lcs.dynamics.com/Issue/Details/?bugId=600455) | **TrvExpTrans** causes an orphaned **TaxUncommitted** record, because only **SourceDocumentLine** is deleted. |
| Travel and Expense | [609918](https://fix.lcs.dynamics.com/Issue/Details/?bugId=609918) | **ReleaseUpdateDB72_Expense.updateTrvExpTransProjTransId()** doesn't honor **trvExpTrans.ReferenceDataAreaId** to create the new number sequence. |

## Regulatory updates

For information about regulatory updates for finance and operations apps, see [Regulatory updates](/dynamics365/finance/localizations/regulatory-updates). You can also sign in to Microsoft Dynamics Lifecycle Services (LCS) and use the Issue search tool to view the planned regulatory updates. Issue search lets you search by country or region, type of feature, and release.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
