---
title: What's new or changed in Project Operations, July 2021 for Project Operations for manufacturing
description: This article provides information about the quality updates available in the July 2021 release of Project Operations for manufacturing.
author: andchoi
ms.custom:
  - evergreen
ms.date: 07/07/2025
ms.topic: whats-new
ms.reviewer: johnmichalak
ms.author: andchoi
---

# What's new or changed in Project Operations, July 2021 for Project Operations for manufacturing

_**Applies To:** Project Operations for manufacturing based-scenarios_

This article applies to the following Dynamics 365 Project Operations components and versions:

- Project management and accounting in Dynamics 365 Finance environment version 10.0.20
 
### Quality updates
                                                                                                                                                                                  
| Feature area                      | Reference number| Quality update                                                                                                                                                                          |
|-----------------------------------|--------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Project management and accounting | [485394](https://fix.lcs.dynamics.com/Issue/Details/?bugId=485394) | Cost commitment records from a purchase requisition are cleared as soon as the purchase order is released from the purchase requisition issue.                                                                           |
| Project management and accounting | [529602](https://fix.lcs.dynamics.com/Issue/Details/?bugId=529602) | Budget validation occurs twice on a purchase requisition. This duplication means that the requisition can't be closed and the corresponding purchase order isn't created.                                                                                                                        |
| Project management and accounting | [539439](https://fix.lcs.dynamics.com/Issue/Details/?bugId=539439) | The **Percent to bill on** billing rule couldn't be completed because of a rounding issue.                                                                              |
| Project management and accounting | [540023](https://fix.lcs.dynamics.com/Issue/Details/?bugId=540023) | When you adjust the transaction and the percentage has decimals, the cost and sales price isn't adjusted correctly.                                      |
| Project management and accounting | [540927](https://fix.lcs.dynamics.com/Issue/Details/?bugId=540927) | The accounting source explorer shows hours for a single timesheet line for multiple timesheet lines with different activities.                                      |
| Project management and accounting | [541471](https://fix.lcs.dynamics.com/Issue/Details/?bugId=541471) | Saved views and timesheet line detail personalization cause the system to always open the details for the first timesheet in the list when trying to open a timesheet.  |
| Project management and accounting | [548677](https://fix.lcs.dynamics.com/Issue/Details/?bugId=548677) | The project root node disappears and work breakdown structure records are deleted after import.                                                                                             |
| Project management and accounting | [548999](https://fix.lcs.dynamics.com/Issue/Details/?bugId=548999) | When items are received and issued partially from the item   requirement, the system updates the wrong budget consumption balance. |
| Project management and accounting | [550959](https://fix.lcs.dynamics.com/Issue/Details/?bugId=550959) | Project retainage purchase orders aren't showing totals correctly in the **Totals** pane or the **Pending invoice** grid.                                                                  |
| Project management and accounting | [554593](https://fix.lcs.dynamics.com/Issue/Details/?bugId=554593) | When closing inventory, project item cost adjustments are posted to the balance account instead of the profit and loss account.                                                            |
| Project management and accounting | [557394](https://fix.lcs.dynamics.com/Issue/Details/?bugId=557394) | A project posted transaction voucher and an estimate voucher use USD as the accounting currency but the amount is showing what the CAD equivalent would be.              |
| Project management and accounting | [560140](https://fix.lcs.dynamics.com/Issue/Details/?bugId=560140) | Committed costs with an item requirement and purchase order are   wrong in the purchase order invoice process with part product receipt and part invoicing.       |
| Project management and accounting | [560567](https://fix.lcs.dynamics.com/Issue/Details/?bugId=560567) | Project adjustment isn't updating the sales amount correctly with   indirect costs.                                                                                    |
| Project management and accounting | [561137](https://fix.lcs.dynamics.com/Issue/Details/?bugId=561137) | The **Timesheet** table is missing a defined relationship with the **Worker/Resource** view.                                                                                   |
| Project management and accounting | [563330](https://fix.lcs.dynamics.com/Issue/Details/?bugId=563330) | Unable to populate the **Activity number** field when you select it from the drop-down menu for an intercompany timesheet.                                                                 |
| Project management and accounting | [563840](https://fix.lcs.dynamics.com/Issue/Details/?bugId=563840) | You can't add a personalized **Purpose** or **Activity description** field to the following pages: **Project posted transaction**, **Invoice proposal creation**, or **Invoice proposal**.  |
| Project management and accounting | [566348](https://fix.lcs.dynamics.com/Issue/Details/?bugId=566348) | The wrong delivery date control is provided when you create item requirements by using data management (**ProjSalesItemRequirementEntity**).                                              |
| Project management and accounting | [566544](https://fix.lcs.dynamics.com/Issue/Details/?bugId=566544) | When you select a project contract ID in Finance, the Project Operations integrated environment opens the page to create a new record instead of opening the existing project contract.                                                                                                                 |
| Project management and   accounting | [567300](https://fix.lcs.dynamics.com/Issue/Details/?bugId=567300) |  The label, ”@SYS4083080” (”Unable to find a unique Worker record   corresponding to the entered values”) isn't translated to Danish.                                |
| Project management and accounting | [569901](https://fix.lcs.dynamics.com/Issue/Details/?bugId=569901) | The **Item sales tax group** field isn't editable on an invoice proposal.                                                                               |
| Project management and accounting | [557049](https://fix.lcs.dynamics.com/Issue/Details/?bugId=557049) | Committed cost is overstated with non-deductible tax amounts.                                                                                                    |
| Project management and accounting | [565080](https://fix.lcs.dynamics.com/Issue/Details/?bugId=565080) | Posting an intercompany timesheet with multiple projects and   different financial dimensions generates unexpected values in the general ledger.                             |
| Project management and accounting | [567962](https://fix.lcs.dynamics.com/Issue/Details/?bugId=567962) | Invoice proposal lines are duplicated because of multiple instances of the periodic process, **Import from staging** running at the same time.                                      |
| Project management and accounting | [571339](https://fix.lcs.dynamics.com/Issue/Details/?bugId=571339) | There is an error in the credit note invoice proposal posting, so the   transactions on the voucher don't balance.    |
| Project management and accounting | [573567](https://fix.lcs.dynamics.com/Issue/Details/?bugId=573567) | Project committed costs become incorrect after on-hold pending invoices are released.                                                                             |
| Project management and   accounting | [573886](https://fix.lcs.dynamics.com/Issue/Details/?bugId=573886) | You can't create a credit note for a project sales order when the tax is in a different currency than the company currency.                                      |
| Project management and accounting | [582329](https://fix.lcs.dynamics.com/Issue/Details/?bugId=582329) | Deleting a contract also deletes the address associated with the customer.                                                                                     |
| Project management and accounting | [585811](https://fix.lcs.dynamics.com/Issue/Details/?bugId=585811) | An invoice proposal that results from a negative time transaction correction can't be posted.                                                                    |
| Travel and Expense                  | [532075](https://fix.lcs.dynamics.com/Issue/Details/?bugId=532075) | Tax is calculated differently in expense reports.                                                                                                                  |
| Travel and Expense                  | [546450](https://fix.lcs.dynamics.com/Issue/Details/?bugId=546450) | Release update **DB72_Expense.updateTrvExpTransProjTransId()**   doesn't allow **trvExpTrans.ReferenceDataAreaId** to create the new number sequence.                    |
| Travel and Expense                  | [568805](https://fix.lcs.dynamics.com/Issue/Details/?bugId=568805) | The amount filed isn't showing with the mandatory field.                                                                                                             |
| Travel and Expense                  | [568831](https://fix.lcs.dynamics.com/Issue/Details/?bugId=568831) | Improvements in the performance of attaching an expense to the expense report using the Expense Reimagined user interface.                                                            |
| Travel and Expense                  | [570790](https://fix.lcs.dynamics.com/Issue/Details/?bugId=570790) | You can delete posted expense reports.                                                                                           |
| Travel and Expense                  | [571317](https://fix.lcs.dynamics.com/Issue/Details/?bugId=571317) | The Expense policy message is displayed multiple times.                                                                                                       |
| Travel and Expense                  | [573969](https://fix.lcs.dynamics.com/Issue/Details/?bugId=573969) | The **Payment method** field is included on the **New expense** pane.                                                                                                      |
| Travel and Expense                  | [523557](https://fix.lcs.dynamics.com/Issue/Details/?bugId=523557) | The **Reset Expense document status** tool should reset the expense report status to **Draft** if the workflow wasn't found. 

### Regulatory updates
For information about regulatory updates for finance and operations apps, see [Regulatory updates](/dynamics365/finance/localizations/regulatory-updates). You can also sign in to Lifecycle Services (LCS) and view the planned regulatory updates using the Issue search tool. Issue search lets you search by country/region, type of feature, and release.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
