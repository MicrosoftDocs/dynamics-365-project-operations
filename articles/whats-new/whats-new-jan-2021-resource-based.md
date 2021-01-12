---
title: What's new January 2021 - Project Operations for resource/non-stocked based scenarios
description: This topic provides information about the quality updates available in the January 2021 release of Project Operations for resource/non-stocked based scenarios.
author: sigitac
manager: tfehr
ms.date: 12/04/2020
ms.topic: article
ms.prod:
ms.service: project-operations
ms.reviewer: kfend 
ms.author: sigitac
---
# What&#39;s new or changed in Project Operations, January 2021

Note!

This article applies to Project Operations components with version listed below.

| Project Operations on CDS environment | Project management and accounting on Dynamics 365 F&amp;O environment |
| --- | --- |
| 4.6.0.154 | 10.0.16 |

## Quality updates

### Project Operations on CDS

­­­­

| **Feature Area** | **Reference number** | **Quality update** |
| --- | --- | --- |
| **Deployment and configuration** | 2106818 | Fixed webresource rename issue causing issues for customers with customization to the specific form |
| **Billing and Pricing** | 2091908 | Fixed &#39;Lock pricing&#39; and &#39;Use Current Pricing&#39; options visibility in invoice form when Project Operations installed together with Field Service solution |
| **Billing and Pricing** | 2103058 | Refresh Project Totals to handle null values for Actual Cost on Task |
| **Billing and Pricing** | 2116100 | Improved error messages used with function Correct Entries on Actuals |
| **Billing and Pricing** | 2116129 | Improved Expense Estimates visibility in Estimates tab in Projects page |
| **Billing and Pricing** | 2119112 | Fixed aggregation of Actual Sales and Actual Cost when different Exchange Rates are used |
| **Billing and Pricing** | 2134705 | Fixed error &quot;Cannot read property &#39;getResourceString&#39; of undefined&quot; on loading the Invoice form when Field Service solution is installed |
| **Opportunity Management** | 2022195 | The task based billing grid on the project page to show an icon indicating that there a contract/quote line linked to that task. |
| **Opportunity Management** | 2029135 | Fixed &quot;Business process error&quot; when user tries to open Invoice line on invoice having &quot;Advance&quot; amount invoiced on it and is in confirmed state |
| **Opportunity Management** | 2040713 | Fixed script error while creating invoice from contract when Field Service solution is installed |
| **Project Planning and Tracking** | 2090202 | Marked not-used Business Rules as Deprecated |
| **Time and Expense** | 2091249 | Tighten controls, so users are prevented from changing the task on an time entry that has been approved/submitted |

### Project management and accounting on Dynamics 365 F&amp;O

| **Feature Area** | **Reference number** | **Quality update** |
| --- | --- | --- |
| **Travel and Expense** | [515334](https://fix.lcs.dynamics.com/Issue/Details/?bugId=515334) | Unable to post expense lines due to missing hour setup in contract line |
| **Travel and Expense** | [437673](https://fix.lcs.dynamics.com/Issue/Details/?bugId=437673) | Expense category cannot be list in expense report when assign project/category group and left the category in remain area and specify category to a project in category assignments. |
| **Travel and Expense** | [441256](https://fix.lcs.dynamics.com/Issue/Details/?bugId=441256) | Cash advances balance is not updated for Expense report posted by line |
| **Travel and Expense** | [465396](https://fix.lcs.dynamics.com/Issue/Details/?bugId=465396) | Update payment information job fails after reversing settlements where Invoice was settled with 2 or more payment transactions |
| **Travel and Expense** | [472892](https://fix.lcs.dynamics.com/Issue/Details/?bugId=472892) | Last day meal reduction calculation for the per diem expense category issue |
| **Travel and Expense** | [477714](https://fix.lcs.dynamics.com/Issue/Details/?bugId=477714) | Expense Management - Report Expense Type per employee do not show itemized expenses when user first connection was in language es-MX |
| **Travel and Expense** | [487516](https://fix.lcs.dynamics.com/Issue/Details/?bugId=487516) | Vendor payment for Expense report invoice is using wrong summary account for settlement posting |
| **Travel and Expense** | [487531](https://fix.lcs.dynamics.com/Issue/Details/?bugId=487531) | Expense report posted with &quot;Allow grouping of transactions based on offset payment account&quot; and &quot;Correcting Accounting Date at posting&quot; turned on. shows Accounting Dates are not grouped in Accounting Distribution table and impacts sales tax records |
| **Travel and Expense** | [488292](https://fix.lcs.dynamics.com/Issue/Details/?bugId=488292) | Expense subcategory mapping is removed when &quot;use in expense&quot; is unchecked and then checked again. |
| **Travel and Expense** | [506175](https://fix.lcs.dynamics.com/Issue/Details/?bugId=506175) | Intercompany expense report cannot be created if the Project ID is added on the header level. |
| **Travel and Expense** | [509491](https://fix.lcs.dynamics.com/Issue/Details/?bugId=509491) | Expense payment issue when the expense amount is more than the cash advance amount. |
| **Travel and Expense** | [509556](https://fix.lcs.dynamics.com/Issue/Details/?bugId=509556) | Project ID info under intercompany expense report is empty if the user role is assigned to a specific organization |
| **Travel and Expense** | [518186](https://fix.lcs.dynamics.com/Issue/Details/?bugId=518186) | Expense category locked when adding a New expense line |
| **Travel and Expense** | [520914](https://fix.lcs.dynamics.com/Issue/Details/?bugId=520914) | Itemizing already split Expense report lines posts incomplete AP\GL voucher and also breaks the Accounting Source Explorer for due to TRVEXPTRANS.SOURCEDOCUMENTLINE duplication |
| **Travel and Expense** | [521768](https://fix.lcs.dynamics.com/Issue/Details/?bugId=521768) | Index added on TRVREQUISITIONLINE table for which customer has duplicates throws error during upgrade |
| **Travel and Expense** | [525106](https://fix.lcs.dynamics.com/Issue/Details/?bugId=525106) | ProjOps - Cannot create/approve time with intercompany tasks in CE |

## Regulatory updates

For information about regulatory updates for Dynamics 365 Finance and Operations apps, see [Regulatory updates](https://docs.microsoft.com/en-us/dynamics365/finance/localizations/regulatory-updates). Another way to learn about regulatory updates is to sign in to LCS and view the planned regulatory updates using the issue search tool. Issue search lets you search by country, type of feature, and release.
