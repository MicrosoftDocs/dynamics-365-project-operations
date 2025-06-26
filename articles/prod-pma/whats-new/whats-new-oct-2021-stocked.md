---
title: What's new or changed in Project Operations, October 2021 for manufacturing
description: This article provides information about the quality updates that are available in the October 2021 release of Project Operations for manufacturing.
author: andchoi
ms.custom:
  - evergreen
ms.date: 04/09/2024
ms.topic: whats-new
ms.reviewer: johnmichalak
ms.author: andchoi
---

# What's new or changed in Project Operations, October 2021 for manufacturing

_**Applies To:** Project Operations for manufacturing based-scenarios_

This article applies to the following components and versions of Microsoft Dynamics 365 Project Operations:

- Project management and accounting in a Dynamics 365 Finance environment version 10.0.22
 
## Quality updates

| Feature area | Reference number | Quality update |
|--------------|------------------|----------------|
| Project management and accounting | [557017](https://fix.lcs.dynamics.com/Issue/Details/?bugId=557017) | Project work in process (WIP) and accrued revenue amounts aren't correctly reversed when an intercompany customer invoice is posted. |
| Project management and accounting | [558232](https://fix.lcs.dynamics.com/Issue/Details/?bugId=558232) | The **Prevent project closure if open transactions exist** functionality doesn't work. |
| Project management and accounting | [559271](https://fix.lcs.dynamics.com/Issue/Details/?bugId=559271) | The billing classification on a free text invoice doesn't automatically fill in dimensions from projects when that functionality is enabled. |
| Project management and accounting | [574013](https://fix.lcs.dynamics.com/Issue/Details/?bugId=574013) | In non-intercompany scenarios, WIP and accrued revenue amounts aren't correctly reversed when the project invoice is posted. |
| Project management and accounting | [577857](https://fix.lcs.dynamics.com/Issue/Details/?bugId=577857) | Debit and credit values are switched when the Microsoft Excel add-in is used with the Project expense journal and the **Offset account type** field is set to **Project**. |
| Project management and accounting | [577972](https://fix.lcs.dynamics.com/Issue/Details/?bugId=577972) | The amount that is posted in project transactions is overstated on a project purchase order that includes stocked items and that has non-deductible tax amounts when **UseTax** is marked. |
| Project management and accounting | [581216](https://fix.lcs.dynamics.com/Issue/Details/?bugId=581216) | The system splits the amount between the project profit and loss reports and the project WIP reports. |
| Project management and accounting | [582065](https://fix.lcs.dynamics.com/Issue/Details/?bugId=582065) | On-hand inventory is incorrect after a partially returned item requirement is adjusted. |
| Project management and accounting | [582682](https://fix.lcs.dynamics.com/Issue/Details/?bugId=582682) | Resource names are duplicated in Project Operations when they are edited in Microsoft Project. |
| Project management and accounting | [583873](https://fix.lcs.dynamics.com/Issue/Details/?bugId=583873) | Intercompany expense reports that have Accounts payable intercompany pending vendor invoice costs are first posted to the **Project WIP cost** posting type. However, during processing, the estimate-related costs are posted to the **Project cost** posting type instead of the expected **Intercompany cost** posting type. |
| Project management and accounting | [584732](https://fix.lcs.dynamics.com/Issue/Details/?bugId=584732) | Vendor retainage results in project expense transactions aren't shown. |
| Project management and accounting | [587453](https://fix.lcs.dynamics.com/Issue/Details/?bugId=587453) | The timesheet must round the transaction amount in the transaction currency to a specified number of decimal places on all accounting distributions and general journal allocation entries. |
| Project management and accounting | [589409](https://fix.lcs.dynamics.com/Issue/Details/?bugId=589409) | Quantities of project item requirements are automatically updated when the planned orders are firmed. |
| Project management and accounting | [590206](https://fix.lcs.dynamics.com/Issue/Details/?bugId=590206) | The voucher number, transaction type vendor balance, and account number can't be reversed on the prepayment invoice of a purchase order. |
| Project management and accounting | [593068](https://fix.lcs.dynamics.com/Issue/Details/?bugId=593068) | The intercompany vendor invoice is broken when vendor invoice integration is turned on. |
| Project management and accounting | [593335](https://fix.lcs.dynamics.com/Issue/Details/?bugId=593335) | When you create a Project expense journal, the cost amount is shown in the **Credit** field. |
| Project management and accounting | [593382](https://fix.lcs.dynamics.com/Issue/Details/?bugId=593382) | The terms of payment on project invoices doesn't work as expected. |
| Project management and accounting | [593565](https://fix.lcs.dynamics.com/Issue/Details/?bugId=593565) | Timesheet vouchers might be reused when the number sequence is set up as continuous. |
| Project management and accounting | [593652](https://fix.lcs.dynamics.com/Issue/Details/?bugId=593652) | FRANCE: The **Manual retention amount** logic doesn't match the **Automatic retention amount** logic in the Project contract invoice proposal. |
| Project management and accounting | [596263](https://fix.lcs.dynamics.com/Issue/Details/?bugId=596263) | When the vendor retention is released, the voucher posting has incorrect additional lines. |
| Project management and accounting | [596650](https://fix.lcs.dynamics.com/Issue/Details/?bugId=596650) | When the **Invoice date** field on the **Create invoice proposal** page is changed, the following error might occur: "Object reference not set to an instance of an object." |
| Project management and accounting | [597679](https://fix.lcs.dynamics.com/Issue/Details/?bugId=597679) | An error occurs when you try to approve a timesheet from the **TSLine** workflow, and there is a timesheet policy for Saturday and Sunday. |
| Project management and accounting | [597801](https://fix.lcs.dynamics.com/Issue/Details/?bugId=597801) | The beginning balance project item type is excluded from **Invoice proposal transaction summaries** when the invoice total of the invoice proposal is calculated. |
| Project management and accounting | [597886](https://fix.lcs.dynamics.com/Issue/Details/?bugId=597886) | If the consumption cost on a project production order is 0 (zero), the following error occurs when you try to estimate: "Attempted to divide by zero." |
| Project management and accounting | [598706](https://fix.lcs.dynamics.com/Issue/Details/?bugId=598706) | The Project Timesheet Mobile app for Android stops responding. The issue is related to **TimeEntryDataManager ArgumentNullException**. |
| Project management and accounting | [598758](https://fix.lcs.dynamics.com/Issue/Details/?bugId=598758) | The Project Operations integration journal fails when you post it, because an account is missing dimensions. However, the account that is missing the dimensions isn't the account that you're posting to. |
| Project management and accounting | [598929](https://fix.lcs.dynamics.com/Issue/Details/?bugId=598929) | The **ToDate** filter in searches isn't cleared when it's removed from the **Select** dialog box on the **Post cost** page. |
| Project management and accounting | [599757](https://fix.lcs.dynamics.com/Issue/Details/?bugId=599757) | **Reset all distribution** fails and shows an error for the timesheets that are created for a project of the **Time only** type. |
| Project management and accounting | [602650](https://fix.lcs.dynamics.com/Issue/Details/?bugId=602650) | The **Project** tab isn't editable on a pending vendor invoice when the procurement category is assigned to the item. |
| Project management and accounting | [605121](https://fix.lcs.dynamics.com/Issue/Details/?bugId=605121) | The navigation pane is missing if you aren't signed in to Project Operations Dataverse. |
| Project management and accounting | [546467](https://fix.lcs.dynamics.com/Issue/Details/?bugId=546467) | For intercompany project adjustment transactions, there are issues in the destination company. |
| Project management and accounting | [563579](https://fix.lcs.dynamics.com/Issue/Details/?bugId=563579) | Committed costs for a project calculate the wrong quantity and cost price if the purchase order was processed by **Purchase order year-end process** in General ledger. |
| Project management and accounting | [581454](https://fix.lcs.dynamics.com/Issue/Details/?bugId=581454) | When a project production order that has quality orders is reported as finished, the following error occurs: "No virtual transaction marked with inventory transaction." |
| Project management and accounting | [596408](https://fix.lcs.dynamics.com/Issue/Details/?bugId=596408) | When a project-related Accounts payable invoice is posted, the following error occurs: "Enumerated text Project - cost - item does not exist." |
| Project management and accounting | [597237](https://fix.lcs.dynamics.com/Issue/Details/?bugId=597237) | Indirect costs are doubled when you manually accrue revenue. |
| Project management and accounting | [601198](https://fix.lcs.dynamics.com/Issue/Details/?bugId=601198) | Accrue revenue and WIP posting doesn't produce transactions. |
| Project management and accounting | [602095](https://fix.lcs.dynamics.com/Issue/Details/?bugId=602095) | Activation of the pending price fails for a standard cost item when a received project purchase order exists. |
| Project management and accounting | [602677](https://fix.lcs.dynamics.com/Issue/Details/?bugId=602677) | The WIP-reversed value from an invoice posting differs from the original posted WIP value from a time entry. |
| Project management and accounting | [602728](https://fix.lcs.dynamics.com/Issue/Details/?bugId=602728) | There is a posting issue for project invoiced revenue in applied retainer cases where the transactions on voucher don't balance. |
| Project management and accounting | [603624](https://fix.lcs.dynamics.com/Issue/Details/?bugId=603624) | Creation of an estimate after an invoice proposal is posted blocks the import of correction lines in Project Operations. |
| Project management and accounting | [606083](https://fix.lcs.dynamics.com/Issue/Details/?bugId=606083) | Modification of a fully invoiced milestone record should not be possible. |
| Project management and accounting | [611389](https://fix.lcs.dynamics.com/Issue/Details/?bugId=611389) | When automatic charges are used, the intercompany customer invoice for a timesheet can't be posted, and an error message is shown. |
| Project management and accounting | [612991](https://fix.lcs.dynamics.com/Issue/Details/?bugId=612991) | The address on a subproject isn't correctly updated. |
| Project management and accounting | [613418](https://fix.lcs.dynamics.com/Issue/Details/?bugId=613418) | The cost price on item requirements is updated with the purchase price for consolidated purchase orders. |
| Project management and accounting | [614145](https://fix.lcs.dynamics.com/Issue/Details/?bugId=614145) | The posted cost isn't correct after the purchase price is updated and the parameter **Activate change management** is enabled. |
| Travel and Expense | [575305](https://fix.lcs.dynamics.com/Issue/Details/?bugId=575305) | All user expenses can be seen when you search for a category in the Expense mobile app. |
| Travel and Expense | [583101](https://fix.lcs.dynamics.com/Issue/Details/?bugId=583101) | Incorrect amounts on vendor transactions and sales tax transactions are posted from an expense that was created from a credit card transaction. |
| Travel and Expense | [583760](https://fix.lcs.dynamics.com/Issue/Details/?bugId=583760) | An irrelevant warning message is shown when you refresh the expense report pages. |
| Travel and Expense | [598656](https://fix.lcs.dynamics.com/Issue/Details/?bugId=598656) | The wrong interim approver is used when you delete an interim approver and then resubmit through workflow. |
| Travel and Expense | [612742](https://fix.lcs.dynamics.com/Issue/Details/?bugId=612742) | A posting error occurs that is related to the mileage setup. |
| Travel and Expense | [620773](https://fix.lcs.dynamics.com/Issue/Details/?bugId=620773) | Distribution doesn't update the legal entity when an unattached transaction is re-added to the expense report on an intercompany expense. |

### Regulatory updates

For information about regulatory updates for finance and operations apps, see [Regulatory updates](/dynamics365/finance/localizations/regulatory-updates). You can also sign in to Microsoft Dynamics Lifecycle Services (LCS) and use the Issue search tool to view the planned regulatory updates. Issue search lets you search by country or region, type of feature, and release.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
