---
title: What's new March 2022 - Project Operations for resource/non-stocked based scenarios
description: This topic provides information about the quality updates that are available in the March 2022 release of Project Operations for resource/non-stocked based scenarios.
author: sigitac
ms.date: 02/14/2021
ms.topic: article
ms.prod:
ms.reviewer: kfend 
ms.author: sigitac
---

# What's new March 2022 - Project Operations for resource/non-stocked based scenarios

*Applies To: Project Operations for resource/non-stocked based scenarios*

This topic applies to the following components and versions of Microsoft Dynamics 365 Project Operations:

- Project Operations in a Dataverse environment version 4.30.0.99
- Project management and accounting in a Dynamics 365 Finance environment version 10.0.25

##

## Features included in this release

- Per diems are now supported in the new and reimagined modern expense workspace. Companies that use per diems can enable the feature to provide users with an easy way to submit their per diem expenses and get reimbursed. For more information , see [https://docs.microsoft.com/en-us/dynamics365/project-operations/expense/per-diem-expenses](https://docs.microsoft.com/en-us/dynamics365/project-operations/expense/per-diem-expenses)

##

## Project Operations dual-write maps updates

There are no updates for Project Operations dual-write maps in this release. Please refer to [Project Operations dual-write map versions | Microsoft Docs](https://docs.microsoft.com/en-us/dynamics365/project-operations/environment/resource-dual-write-maps) for the latest list and versions of Project Operations Dual Write maps.

You should always run the latest version of the map in your environment and enable all related table maps as you update your Project Operations Dataverse solution and Finance and Operations solution version. Certain features and capabilities might not work correctly if the latest version of the map is not activated. You can see the active version of the map in the  **Version**  column on the  **Dual-write**  page. You can activate a new version of the map by selecting  **Table map versions** , selecting the latest version, and then saving the selected version. If you have customized an out-of-the-box table map, reapply the changes. For more information, see [Application lifecycle management](https://docs.microsoft.com/en-us/dynamics365/fin-ops-core/dev-itpro/data-entities/dual-write/app-lifecycle-management).

If you encounter an issue with starting the map, follow instructions in the [Missing table columns issue on maps](https://docs.microsoft.com/en-us/dynamics365/fin-ops-core/dev-itpro/data-entities/dual-write/dual-write-troubleshooting-finops-upgrades#missing-table-columns-issue-on-maps) section of the Dual Write troubleshooting guide.

##

## Quality updates

### Project Operations on Dataverse

| **Feature area** | **Reference number** | **Quality update** |
| --- | --- | --- |
| Time and expense | 2388011| Show reject comments to time entry submitters at bulk approval |
| Project planning and tracking | 2495294 | Project details must not be editable in Task details form |
| Billing and pricing | 2499605 | Contract Milestones created via Quote Milestones are incorrectly marked as read-only in the UI |
| Project planning and tracking | 2506050 | [Schedule APIs] Operation set stay pending for 1 hour if no change to save and falsely marked as Failed after, should be complete right away |
| Billing and pricing | 2507401 | Contracting unit is defaulted incorrectly on Project due to incorrect caching |
| Billing and pricing | 2541660 | Sales Order Creation Validation in Dual Write should be for Project-Based Orders only |
| Billing and pricing | 2552745 | Tax not split between customers with split billing rules |
| Billing and pricing | 2558859 | Improved error messages when setting up Pricing Dimensions |
| Billing and pricing | 2558933 | Import from Project Estimates fails when customer adds msdyn\_project as a Pricing Dimension |
| Billing and pricing | 2559101 | Project Parameter deletion is not blocked and causes issues |
| Opportunity management | 2570390 | DualWrite Plugin enforces the account type on Quote/Order/Opportunity to be &quot;Customer&quot; even though they are not work-based (ie, PSA quote) |
| Billing and pricing | 2586097 | Split billed cost actuals not reversed when project removed from project contract line |
| Billing and pricing | 2589619 | Tax on write in material is propagating to unbilled sales actuals and hence to invoice |
| Opportunity management | 2594015 | Unable to close quote as won for customer&#39;s with Net60 payment term |
| Project planning and tracking | 2595841 | Project for the Web: Users are shown an error about missing msdyn\_actualstart when trying to create a new resource request |
| Time and Expense | 2602511 | Time Entries &quot;Rejected by&quot; showing as System instead of the named user. |
| Time and Expense | 2602528 | A project approver is able to approve time on projects where they are not flagged as an approver |
| Billing and pricing | 2608550 | It is possible to confirm a correction invoice that does not have changes from the original |

### Project management and accounting on Dynamics 365 Finance

| Feature area | Reference number | Quality update |
| --- | --- | --- |
| Project management and accounting | [606759](https://nam06.safelinks.protection.outlook.com/?url=https:%2F%2Ffix.lcs.dynamics.com%2FIssue%2FDetails%2F?bugId%3D606759&amp;data=04%7C01%7Chmahl%40microsoft.com%7Ce0aa497efe5d44aacb8d08d9f3492410%7C72f988bf86f141af91ab2d7cd011db47%7C1%7C0%7C637808317817553152%7CUnknown%7CTWFpbGZsb3d8eyJWIjoiMC4wLjAwMDAiLCJQIjoiV2luMzIiLCJBTiI6Ik1haWwiLCJXVCI6Mn0%3D%7C3000&amp;sdata=efabk%2BHTxmOjOqDcjxkyz9Uva3UfZaCg3Doc975%2F9HY%3D&amp;reserved=0) | Allowed Transaction Category ID field length mismatch between F&amp;O and PO |
 | Project management and accounting | [617806](https://nam06.safelinks.protection.outlook.com/?url=https:%2F%2Ffix.lcs.dynamics.com%2FIssue%2FDetails%2F?bugId%3D617806&amp;data=04%7C01%7Chmahl%40microsoft.com%7Ce0aa497efe5d44aacb8d08d9f3492410%7C72f988bf86f141af91ab2d7cd011db47%7C1%7C0%7C637808317817603136%7CUnknown%7CTWFpbGZsb3d8eyJWIjoiMC4wLjAwMDAiLCJQIjoiV2luMzIiLCJBTiI6Ik1haWwiLCJXVCI6Mn0%3D%7C3000&amp;sdata=g6UzaNLVZz5rBEEkDBM1oceShalml1AYqYEdOr17JyY%3D&amp;reserved=0) | [PROJECT OPERATIONS[ Unable to Eliminate Fixed Price projects with On account invoicing = Profit and Loss and Completed percentage principle |
 | Project management and accounting | [620979](https://nam06.safelinks.protection.outlook.com/?url=https:%2F%2Ffix.lcs.dynamics.com%2FIssue%2FDetails%2F?bugId%3D620979&amp;data=04%7C01%7Chmahl%40microsoft.com%7Ce0aa497efe5d44aacb8d08d9f3492410%7C72f988bf86f141af91ab2d7cd011db47%7C1%7C0%7C637808317817603136%7CUnknown%7CTWFpbGZsb3d8eyJWIjoiMC4wLjAwMDAiLCJQIjoiV2luMzIiLCJBTiI6Ik1haWwiLCJXVCI6Mn0%3D%7C3000&amp;sdata=sI5NvvGoMbzCeQRbOQkCYG8vApJSeQh6MvFZrNzrCFw%3D&amp;reserved=0) | Sales tax group is incorrectly defaulted from Project setup on Expense line in the Project Operations integration journal |
 | Project management and accounting | [623014](https://nam06.safelinks.protection.outlook.com/?url=https:%2F%2Ffix.lcs.dynamics.com%2FIssue%2FDetails%2F?bugId%3D623014&amp;data=04%7C01%7Chmahl%40microsoft.com%7Ce0aa497efe5d44aacb8d08d9f3492410%7C72f988bf86f141af91ab2d7cd011db47%7C1%7C0%7C637808317817653119%7CUnknown%7CTWFpbGZsb3d8eyJWIjoiMC4wLjAwMDAiLCJQIjoiV2luMzIiLCJBTiI6Ik1haWwiLCJXVCI6Mn0%3D%7C3000&amp;sdata=9FsE7BZwBwXsLlUx%2BAEJDlciT3i8U90iBooo8yavhIw%3D&amp;reserved=0) | No way of amending project invoice proposal header dimensions in an integrated deployment with Project Operations. |
 | Project management and accounting | [624283](https://nam06.safelinks.protection.outlook.com/?url=https:%2F%2Ffix.lcs.dynamics.com%2FIssue%2FDetails%2F?bugId%3D624283&amp;data=04%7C01%7Chmahl%40microsoft.com%7Ce0aa497efe5d44aacb8d08d9f3492410%7C72f988bf86f141af91ab2d7cd011db47%7C1%7C0%7C637808317817653119%7CUnknown%7CTWFpbGZsb3d8eyJWIjoiMC4wLjAwMDAiLCJQIjoiV2luMzIiLCJBTiI6Ik1haWwiLCJXVCI6Mn0%3D%7C3000&amp;sdata=L3wB659DDa5UAkDF3bhNnzjhZaMfcnri%2Fs9IYp39E%2Fc%3D&amp;reserved=0) | Intercompany vendor invoice must not be integrated to Dataverse |
 | Project management and accounting | [634156](https://nam06.safelinks.protection.outlook.com/?url=https:%2F%2Ffix.lcs.dynamics.com%2FIssue%2FDetails%2F?bugId%3D634156&amp;data=04%7C01%7Chmahl%40microsoft.com%7Ce0aa497efe5d44aacb8d08d9f3492410%7C72f988bf86f141af91ab2d7cd011db47%7C1%7C0%7C637808317817853086%7CUnknown%7CTWFpbGZsb3d8eyJWIjoiMC4wLjAwMDAiLCJQIjoiV2luMzIiLCJBTiI6Ik1haWwiLCJXVCI6Mn0%3D%7C3000&amp;sdata=1v5ZafckozDnVKsg4pcLFDmL9Gd7pU2vMHQ1pgDvzgo%3D&amp;reserved=0) | [ProjOps]Mismatch in Customer Balances Currency &amp; Reporting Currency. |
 | Project management and accounting | [641612](https://nam06.safelinks.protection.outlook.com/?url=https:%2F%2Ffix.lcs.dynamics.com%2FIssue%2FDetails%2F?bugId%3D641612&amp;data=04%7C01%7Chmahl%40microsoft.com%7Ce0aa497efe5d44aacb8d08d9f3492410%7C72f988bf86f141af91ab2d7cd011db47%7C1%7C0%7C637808317817953066%7CUnknown%7CTWFpbGZsb3d8eyJWIjoiMC4wLjAwMDAiLCJQIjoiV2luMzIiLCJBTiI6Ik1haWwiLCJXVCI6Mn0%3D%7C3000&amp;sdata=NWRerwV4HhddY8bxSReAi2ax1VDK42UqXIyLvM9J9xU%3D&amp;reserved=0) | Project invoice can be posted even if customer is on-hold for all invoices |
 | Project management and accounting | [642945](https://nam06.safelinks.protection.outlook.com/?url=https:%2F%2Ffix.lcs.dynamics.com%2FIssue%2FDetails%2F?bugId%3D642945&amp;data=04%7C01%7Chmahl%40microsoft.com%7Ce0aa497efe5d44aacb8d08d9f3492410%7C72f988bf86f141af91ab2d7cd011db47%7C1%7C0%7C637808317817953066%7CUnknown%7CTWFpbGZsb3d8eyJWIjoiMC4wLjAwMDAiLCJQIjoiV2luMzIiLCJBTiI6Ik1haWwiLCJXVCI6Mn0%3D%7C3000&amp;sdata=%2FrQjz1BncOwgzz03nS8soqb90m3G7axqhREJU87Nhb8%3D&amp;reserved=0) | [ProjOps] Project invoice proposal with the Header and Lines view missing Delete all lines button |
 | Project management and accounting | [637760](https://nam06.safelinks.protection.outlook.com/?url=https:%2F%2Ffix.lcs.dynamics.com%2FIssue%2FDetails%2F?bugId%3D637760&amp;data=04%7C01%7Chmahl%40microsoft.com%7Ce0aa497efe5d44aacb8d08d9f3492410%7C72f988bf86f141af91ab2d7cd011db47%7C1%7C0%7C637808317818452927%7CUnknown%7CTWFpbGZsb3d8eyJWIjoiMC4wLjAwMDAiLCJQIjoiV2luMzIiLCJBTiI6Ik1haWwiLCJXVCI6Mn0%3D%7C3000&amp;sdata=oxB6h2Tok5Iba4FN%2B6tlnMW3xE9wphvJi3vPpC6jOQ8%3D&amp;reserved=0) | posting the vendor invoice gives error as follows: &quot;The accounting date for the invoice must be in the same accounting year as the related purchased order. Run the purchase order year-end process or change the date to the current accounting year&quot; |
 | Travel and Expense | [604128](https://nam06.safelinks.protection.outlook.com/?url=https:%2F%2Ffix.lcs.dynamics.com%2FIssue%2FDetails%2F?bugId%3D604128&amp;data=04%7C01%7Chmahl%40microsoft.com%7Ce0aa497efe5d44aacb8d08d9f3492410%7C72f988bf86f141af91ab2d7cd011db47%7C1%7C0%7C637808317817553152%7CUnknown%7CTWFpbGZsb3d8eyJWIjoiMC4wLjAwMDAiLCJQIjoiV2luMzIiLCJBTiI6Ik1haWwiLCJXVCI6Mn0%3D%7C3000&amp;sdata=J%2F7M4x%2BCVkFfxxHm8LOn0npS6QfSGpDe6xJKZ1L910M%3D&amp;reserved=0) | Project committed cost not getting released after closing the travel requisition committed cost |
 | Travel and Expense | [620803](https://nam06.safelinks.protection.outlook.com/?url=https:%2F%2Ffix.lcs.dynamics.com%2FIssue%2FDetails%2F?bugId%3D620803&amp;data=04%7C01%7Chmahl%40microsoft.com%7Ce0aa497efe5d44aacb8d08d9f3492410%7C72f988bf86f141af91ab2d7cd011db47%7C1%7C0%7C637808317817603136%7CUnknown%7CTWFpbGZsb3d8eyJWIjoiMC4wLjAwMDAiLCJQIjoiV2luMzIiLCJBTiI6Ik1haWwiLCJXVCI6Mn0%3D%7C3000&amp;sdata=S8Bpa5l%2FJhr4ySOjLIJdP9Cep53Zoa9D8fgacAU%2FTng%3D&amp;reserved=0) | &quot;Stack Trace: The company does not exist&quot; error when submitting an expense report |
 | Travel and Expense | [622465](https://nam06.safelinks.protection.outlook.com/?url=https:%2F%2Ffix.lcs.dynamics.com%2FIssue%2FDetails%2F?bugId%3D622465&amp;data=04%7C01%7Chmahl%40microsoft.com%7Ce0aa497efe5d44aacb8d08d9f3492410%7C72f988bf86f141af91ab2d7cd011db47%7C1%7C0%7C637808317817653119%7CUnknown%7CTWFpbGZsb3d8eyJWIjoiMC4wLjAwMDAiLCJQIjoiV2luMzIiLCJBTiI6Ik1haWwiLCJXVCI6Mn0%3D%7C3000&amp;sdata=Yz211grpXqdnCT2jT26698GiPF%2F484fQbWPiBi806zA%3D&amp;reserved=0) | ProjID not defaulting on Expense report when &#39;require activity for journal&#39; parameter selected on project |
 | Travel and Expense | [626781](https://nam06.safelinks.protection.outlook.com/?url=https:%2F%2Ffix.lcs.dynamics.com%2FIssue%2FDetails%2F?bugId%3D626781&amp;data=04%7C01%7Chmahl%40microsoft.com%7Ce0aa497efe5d44aacb8d08d9f3492410%7C72f988bf86f141af91ab2d7cd011db47%7C1%7C0%7C637808317817702721%7CUnknown%7CTWFpbGZsb3d8eyJWIjoiMC4wLjAwMDAiLCJQIjoiV2luMzIiLCJBTiI6Ik1haWwiLCJXVCI6Mn0%3D%7C3000&amp;sdata=d8Hy%2B6OjPHMhLNnutceh3nuiTau6VeG%2BfYTCkp9jNVg%3D&amp;reserved=0) | Post Expenses button does not work correctly Project Operations for Resource/ non-stocked scenarios |
 | Travel and Expense | [635348](https://nam06.safelinks.protection.outlook.com/?url=https:%2F%2Ffix.lcs.dynamics.com%2FIssue%2FDetails%2F?bugId%3D635348&amp;data=04%7C01%7Chmahl%40microsoft.com%7Ce0aa497efe5d44aacb8d08d9f3492410%7C72f988bf86f141af91ab2d7cd011db47%7C1%7C0%7C637808317817853086%7CUnknown%7CTWFpbGZsb3d8eyJWIjoiMC4wLjAwMDAiLCJQIjoiV2luMzIiLCJBTiI6Ik1haWwiLCJXVCI6Mn0%3D%7C3000&amp;sdata=p1QdfgFO9Hiat9DVYsAEM%2BEwMRo2PjIJO7%2BfXA038CA%3D&amp;reserved=0) | Rate per mile issue for Mileage expense report with passengers |
 | Travel and Expense | [638019](https://nam06.safelinks.protection.outlook.com/?url=https:%2F%2Ffix.lcs.dynamics.com%2FIssue%2FDetails%2F?bugId%3D638019&amp;data=04%7C01%7Chmahl%40microsoft.com%7Ce0aa497efe5d44aacb8d08d9f3492410%7C72f988bf86f141af91ab2d7cd011db47%7C1%7C0%7C637808317817903075%7CUnknown%7CTWFpbGZsb3d8eyJWIjoiMC4wLjAwMDAiLCJQIjoiV2luMzIiLCJBTiI6Ik1haWwiLCJXVCI6Mn0%3D%7C3000&amp;sdata=o5XqzhPUD2PmAzHlyDKzDfAomOpmeexeHA7WxGP0D6Y%3D&amp;reserved=0) | Employee \&gt; Expense \&gt; Mileage rates not totalling correctly when using two different Vehicle types in the Expense category \&gt; Mileage rate tiers |
 | Travel and Expense | [641272](https://nam06.safelinks.protection.outlook.com/?url=https:%2F%2Ffix.lcs.dynamics.com%2FIssue%2FDetails%2F?bugId%3D641272&amp;data=04%7C01%7Chmahl%40microsoft.com%7Ce0aa497efe5d44aacb8d08d9f3492410%7C72f988bf86f141af91ab2d7cd011db47%7C1%7C0%7C637808317817953066%7CUnknown%7CTWFpbGZsb3d8eyJWIjoiMC4wLjAwMDAiLCJQIjoiV2luMzIiLCJBTiI6Ik1haWwiLCJXVCI6Mn0%3D%7C3000&amp;sdata=rxlrHAsNf5QyU0fjCwmInvGKBvWR991YE5EmB0KimYo%3D&amp;reserved=0) | Project field look up on travel requisition line is not returning correctly list of Projects |
 | Travel and Expense | [645905](https://nam06.safelinks.protection.outlook.com/?url=https:%2F%2Ffix.lcs.dynamics.com%2FIssue%2FDetails%2F?bugId%3D645905&amp;data=04%7C01%7Chmahl%40microsoft.com%7Ce0aa497efe5d44aacb8d08d9f3492410%7C72f988bf86f141af91ab2d7cd011db47%7C1%7C0%7C637808317818003025%7CUnknown%7CTWFpbGZsb3d8eyJWIjoiMC4wLjAwMDAiLCJQIjoiV2luMzIiLCJBTiI6Ik1haWwiLCJXVCI6Mn0%3D%7C3000&amp;sdata=X%2FqcJod3HdTQ8zdJJUQn5AiB2CPLR83BwVL36rUgNso%3D&amp;reserved=0) | Expense report - Mileage in review shoes warning |
 | Travel and Expense | [647819](https://nam06.safelinks.protection.outlook.com/?url=https:%2F%2Ffix.lcs.dynamics.com%2FIssue%2FDetails%2F?bugId%3D647819&amp;data=04%7C01%7Chmahl%40microsoft.com%7Ce0aa497efe5d44aacb8d08d9f3492410%7C72f988bf86f141af91ab2d7cd011db47%7C1%7C0%7C637808317818003025%7CUnknown%7CTWFpbGZsb3d8eyJWIjoiMC4wLjAwMDAiLCJQIjoiV2luMzIiLCJBTiI6Ik1haWwiLCJXVCI6Mn0%3D%7C3000&amp;sdata=JMHUsT%2BNu2uWPfw1QQ0F%2BrQvJbTWBRUp9MnSN3yVJqo%3D&amp;reserved=0) | The receipt OCR service is not working due to issue with expense OCR service URL. |
 | Travel and Expense | [648684](https://nam06.safelinks.protection.outlook.com/?url=https:%2F%2Ffix.lcs.dynamics.com%2FIssue%2FDetails%2F?bugId%3D648684&amp;data=04%7C01%7Chmahl%40microsoft.com%7Ce0aa497efe5d44aacb8d08d9f3492410%7C72f988bf86f141af91ab2d7cd011db47%7C1%7C0%7C637808317818552494%7CUnknown%7CTWFpbGZsb3d8eyJWIjoiMC4wLjAwMDAiLCJQIjoiV2luMzIiLCJBTiI6Ik1haWwiLCJXVCI6Mn0%3D%7C3000&amp;sdata=9sf6y4AydLEN%2F8s%2B2qc5T4vMhBsT4Fh0r8N8l%2BgT3AM%3D&amp;reserved=0) | Ability to itemize recurring expenses quickly feature - Itemization lines in Expense report are getting changed amounts every time Itemize form is opened |
 | Travel and Expense | [651899](https://nam06.safelinks.protection.outlook.com/?url=https:%2F%2Ffix.lcs.dynamics.com%2FIssue%2FDetails%2F?bugId%3D651899&amp;data=04%7C01%7Chmahl%40microsoft.com%7Ce0aa497efe5d44aacb8d08d9f3492410%7C72f988bf86f141af91ab2d7cd011db47%7C1%7C0%7C637808317818552494%7CUnknown%7CTWFpbGZsb3d8eyJWIjoiMC4wLjAwMDAiLCJQIjoiV2luMzIiLCJBTiI6Ik1haWwiLCJXVCI6Mn0%3D%7C3000&amp;sdata=PosFhqudYQgYQnQrHfhYOmFhrKaREvi%2FNwkdtxcTLpQ%3D&amp;reserved=0) | Can not delete a expense report when the Interim list has more than one approver |
 
 ##
## Removed and depreciated features
The [Removed or deprecated features in Project Operations](https://docs.microsoft.com/en-us/dynamics365/project-operations/whats-new/removed-depreciated-features-project) topic describes features that have been removed or deprecated for Dynamics 365 Project Operations.

- A removed feature is no longer available in the product.
- A deprecated feature is not in active development and may be removed in a future update.

Before any feature is removed from the product, the deprecation notice will be announced in the [Removed or deprecated features in Project Operations](https://docs.microsoft.com/en-us/dynamics365/project-operations/whats-new/removed-depreciated-features-project) topic 12 months prior to the removal.

For breaking changes that only affect compilation time, but are binary compatible with sandbox and production environments, the deprecation time will be less than 12 months. Typically, these are functional updates that need to be made to the compiler.
