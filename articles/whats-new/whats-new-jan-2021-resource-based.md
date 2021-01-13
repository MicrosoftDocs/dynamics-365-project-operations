---
title: What's new January 2021 - Project Operations for resource/non-stocked based scenarios
description: This topic provides information about the quality updates available in the January 2021 release of Project Operations for resource/non-stocked based scenarios.
author: sigitac
manager: tfehr
ms.date: 01/12/2021
ms.topic: article
ms.prod:
ms.service: project-operations
ms.reviewer: kfend 
ms.author: sigitac
---

# What's new January 2021 - Project Operations for resource/non-stocked based scenarios

_**Applies To:** Project Operations for resource/non-stocked based scenarios_


This topic applies to the following Dynamics 365 Project Operations components and versions:

  - Project Operations on Dataverse environment version 4.6.0.154
  - Project management and accounting in Dynamics 365 Finance environment version 10.0.16

## Quality updates

### Project Operations on Dataverse

| **Feature Area** | **Reference number** | **Quality update** |
| --- | --- | --- |
| **Deployment and configuration** | 2106818 | Fixed the webresource rename that was causing issues related to customizing a page. |
| **Billing and Pricing** | 2091908 | Fixed the visibility of the **Lock pricing** and **Use Current Pricing** options on the **Invoice** page when Project Operations is installed together with Dynamics 365 Field Service. |
| **Billing and Pricing** | 2103058 | Refreshed **Project Totals** to handle null values for the actual cost on a task. |
| **Billing and Pricing** | 2116100 | Improved error messages used with the functionality, **Correct Entries on Actuals**. |
| **Billing and Pricing** | 2116129 | Improved expense estimates visibility on the **Estimates** tab on the **Projects** page. |
| **Billing and Pricing** | 2119112 | Fixed aggregation of actual sales and actual cost when different exchange rates are used. |
| **Billing and Pricing** | 2134705 | Fixed the error, "Cannot read property **getResourceString** of undefined" when the **Invoice** page is opened and Field Service is installed. |
| **Opportunity Management** | 2022195 | The task-based billing grid on the **Project** page includes an icon indicating that there is a contract or quote line linked to that task. |
| **Opportunity Management** | 2029135 | Fixed the business process error that occurs when a user tries to open an invoice line on a confirmed invoice that has an advance amount invoiced. |
| **Opportunity Management** | 2040713 | Fixed the script error that occurs when creating an invoice from a contract and Field Service is installed. |
| **Project Planning and Tracking** | 2090202 | Marked business rules that are no longer used as **Deprecated**. |
| **Time and Expense** | 2091249 | Tightened controls so that users can't change the task on a submitted or approved time entry. |

### Project management and accounting in Dynamics 365 Finance

| **Feature Area** | **Reference number** | **Quality update** |
| --- | --- | --- |
| **Project management and accounting** | [478667](https://fix.lcs.dynamics.com/Issue/Details/?bugId=478667) | Incorrect contract amount in On-account form for a fixed-price project with multiple funding sources |
| **Project management and accounting** | [480260](https://fix.lcs.dynamics.com/Issue/Details/?bugId=480260) | %Invoice proposal.PSAnfRefProjId% placeholder is not displaying Project ID for Review project invoice proposals workflow |
| **Project management and accounting** | [481227](https://fix.lcs.dynamics.com/Issue/Details/?bugId=481227) | Wrong cash discount date when posting project Invoice proposals |
| **Project management and accounting** | [482558](https://fix.lcs.dynamics.com/Issue/Details/?bugId=482558) | [ProjOps] Removing and readding resource assignment doubles Project Forecast entries in FO |
| **Project management and accounting** | [484468](https://fix.lcs.dynamics.com/Issue/Details/?bugId=484468) | ProjOps - Unable to create project estimates in CE without having contract line on the project |
| **Project management and accounting** | [485871](https://fix.lcs.dynamics.com/Issue/Details/?bugId=485871) | Financial dimension in project expense transaction is not in sync with the related voucher and the accounting distribution of the expense report, when costs are posted to Balance |
| **Project management and accounting** | [488382](https://fix.lcs.dynamics.com/Issue/Details/?bugId=488382) | The filter for Invoice status in Posted project transactions for Fixed-price projects does not work |
| **Project management and accounting** | [491941](https://fix.lcs.dynamics.com/Issue/Details/?bugId=491941) | Reverse estimate elimination is not working in Periodic |
| **Project management and accounting** | [509989](https://fix.lcs.dynamics.com/Issue/Details/?bugId=509989) | Can delete invoice proposal lines in Project Operations integrated scenario |
| **Project management and accounting** | [510041](https://fix.lcs.dynamics.com/Issue/Details/?bugId=510041) | Prevent enabling Multiple contract lines feature without CE Integration |
| **Project management and accounting** | [510527](https://fix.lcs.dynamics.com/Issue/Details/?bugId=510527) | Estimate screen Invoiced revenue is ZERO when On account invoicing = Profit and loss |
| **Project management and accounting** | [514167](https://fix.lcs.dynamics.com/Issue/Details/?bugId=514167) | Invoice corrections not working in integrated environment |
| **Project management and accounting** | [514364](https://fix.lcs.dynamics.com/Issue/Details/?bugId=514364) | WIP - sales value posting in Intercompany project invoicing picks unexpected account |
| **Project management and accounting** | [514385](https://fix.lcs.dynamics.com/Issue/Details/?bugId=514385) | ProjOps integration: Unable to update dependencies on estimate tasks in CE |
| **Project management and accounting** | [515258](https://fix.lcs.dynamics.com/Issue/Details/?bugId=515258) | Repeated deletion of Project Operations integration journals on F&amp;O side leads to loss of data |
| **Project management and accounting** | [519716](https://fix.lcs.dynamics.com/Issue/Details/?bugId=519716) | Project Invoice proposal posting error: Transaction does not balance on reporting currency when advance invoice deducted is added |
| **Project management and accounting** | [521807](https://fix.lcs.dynamics.com/Issue/Details/?bugId=521807) | Wrong project id on deductions after updating default project on contract in Project Operations |
| **Project management and accounting** | [522799](https://fix.lcs.dynamics.com/Issue/Details/?bugId=522799) | Unable to perform estimate/revenue recognition with project operations feature enabled |
| **Project management and accounting** | [527319](https://fix.lcs.dynamics.com/Issue/Details/?bugId=527319) | ProjOps - Removing a project from a contract does not reset default project on the contract |
| **Project management and accounting** | [528212](https://fix.lcs.dynamics.com/Issue/Details/?bugId=528212) | ProjOps - Intercompany - Wrong expense lines show up in the list to &quot;Add line&quot; in intercompany invoice |
| **Travel and Expense** | [515334](https://fix.lcs.dynamics.com/Issue/Details/?bugId=515334) | Expense lines can't be posted because hour setup is missing on the contract line. |
| **Travel and Expense** | [437673](https://fix.lcs.dynamics.com/Issue/Details/?bugId=437673) | When project/category validation is mandatory, expense categories associated with the project are not visible in the expense report. |
| **Travel and Expense** | [441256](https://fix.lcs.dynamics.com/Issue/Details/?bugId=441256) | The cash advance balance isn't updated when an expense report is posted by line. |
| **Travel and Expense** | [465396](https://fix.lcs.dynamics.com/Issue/Details/?bugId=465396) | The **Update payment information** job fails after reversing settlements where an invoice was settled with two or more payment transactions. |
| **Travel and Expense** | [472892](https://fix.lcs.dynamics.com/Issue/Details/?bugId=472892) | There is an issue with the calculation of the last day meal reduction for the per diem expense category. |
| **Travel and Expense** | [477714](https://fix.lcs.dynamics.com/Issue/Details/?bugId=477714) | The **Expense type per employee** report doesn't show itemized expenses if a user's first connection was in the es-MX language. |
| **Travel and Expense** | [487516](https://fix.lcs.dynamics.com/Issue/Details/?bugId=487516) | The vendor payment for an expense report invoice is using the wrong summary account for settlement posting. |
| **Travel and Expense** | [487531](https://fix.lcs.dynamics.com/Issue/Details/?bugId=487531) | When an expense report is posted with **Allow grouping of transactions based on offset payment account** and **Correcting Accounting Date at posting** enabled, the accounting dates aren't grouped in the **Accounting distribution** table which impacts the sales tax records. |
| **Travel and Expense** | [488292](https://fix.lcs.dynamics.com/Issue/Details/?bugId=488292) | Expense subcategory mapping is removed when the Use in expense check box is cleared and then selected again. |
| **Travel and Expense** | [506175](https://fix.lcs.dynamics.com/Issue/Details/?bugId=506175) | An intercompany expense report can't be created if the Project ID is added at the header level. |
| **Travel and Expense** | [509491](https://fix.lcs.dynamics.com/Issue/Details/?bugId=509491) | There is an issue with expense payments when the expense amount is more than the cash advance amount. |
| **Travel and Expense** | [509556](https://fix.lcs.dynamics.com/Issue/Details/?bugId=509556) | The **Project ID** field on an intercompany expense report is empty if the user role is assigned to a specific organization. |
| **Travel and Expense** | [518186](https://fix.lcs.dynamics.com/Issue/Details/?bugId=518186) | The expense category is locked when adding a new expense line. |
| **Travel and Expense** | [520914](https://fix.lcs.dynamics.com/Issue/Details/?bugId=520914) | Itemizing expense report lines that are already split results in an incomplete posted Accounts payable\General ledger voucher. Because of the duplication of **TRVEXPTRANS.SOURCEDOCUMENTLINE**, the Accounting Source Explorer is also broken. |
| **Travel and Expense** | [521768](https://fix.lcs.dynamics.com/Issue/Details/?bugId=521768) | The index added on the **TRVREQUISITIONLINE** table for which the customer has duplicates, results in an error during upgrade. |
| **Travel and Expense** | [525106](https://fix.lcs.dynamics.com/Issue/Details/?bugId=525106) | In Project Operations, time with intercompany tasks in Dataverse can't be created or approved. |

## Regulatory updates

For information about regulatory updates for Finance and Operations apps, see [Regulatory updates](https://docs.microsoft.com/en-us/dynamics365/finance/localizations/regulatory-updates). You can also sign in to LCS and view the planned regulatory updates using the Issue search tool. Issue search lets you search by country, type of feature, and release.
