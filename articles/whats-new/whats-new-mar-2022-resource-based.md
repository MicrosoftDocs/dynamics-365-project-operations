---
title: What's new March 2022 - Project Operations for resource/non-stocked based scenarios
description: This topic provides information about the quality updates that are available in the March 2022 release of Project Operations for resource/non-stocked based scenarios.
author: sigitac
ms.date: 03/15/2022
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

## Features included in this release

Per diems are now supported in the new and reimagined modern expense workspace. Companies that use per diems can enable this feature to provide users with an easy way to submit and be reimbursed for their per diem expenses. For more information, see [Per diem expenses](../expense/per-diem-expenses.md)


## Project Operations dual-write maps updates

There are no updates for Project Operations dual-write maps in this release. Please refer to [Project Operations dual-write map versions](../environment/resource-dual-write-maps.md) for the latest list and versions of Project Operations dual-write maps.

Always run the latest version of the map in your environment, and enable all related table maps as you update your Project Operations Dataverse solution and Finance solution version. Some features and capabilities might not work correctly if the latest version of the map isn't activated. You can view the active version of the map in the **Version**  column on the **Dual-write** page. To activate a new version of the map, select **Table map versions**, select the latest version, and then save the selected version. If you've customized an out-of-the-box table map, reapply the changes. For more information, see [Application lifecycle management](/dynamics365/fin-ops-core/dev-itpro/data-entities/dual-write/app-lifecycle-management).

If you encounter an issue when you start the map, follow the instructions in the [Missing table columns issue on maps](/dynamics365/fin-ops-core/dev-itpro/data-entities/dual-write/dual-write-troubleshooting-finops-upgrades#missing-table-columns-issue-on-maps) section of the Dual-write troubleshooting guide.

## Quality updates

### Project Operations on Dataverse

| **Feature area** | **Reference number** | **Quality update** |
| --- | --- | --- |
| Time and expense | 2388011| Show reject comments to time entry submitters during bulk approval. |
| Project planning and tracking | 2495294 | Project details must not be editable on the **Task details** pae. |
| Billing and pricing | 2499605 | Contract milestones that are created from quote milestones are incorrectly marked as read-only. |
| Project planning and tracking | 2506050 | Operation set stays pending for one hour if there is no change to save and then falsely marks the set as **Failed**, when it should be completed immediately. |
| Billing and pricing | 2507401 | Contracting unit defaults incorrectly on projects because of incorrect caching. |
| Billing and pricing | 2541660 | **Sales Order Creation Validation** in dual-write should be for project-based orders only. |
| Billing and pricing | 2552745 | Tax isn't being split between customers who have split billing rules set up. |
| Billing and pricing | 2558859 | Improved error messages when setting up pricing dimensions. |
| Billing and pricing | 2558933 | **Import from Project Estimates** fails when **msdyn\_project** is added as a pricing dimension. |
| Billing and pricing | 2559101 | Project parameter deletion isn't blocked and causes issues. |
| Opportunity management | 2570390 | Dual-write plug-in enforces the account type on quotes, orders, and opportunities to be **Customer** even when that isn't correct. |
| Billing and pricing | 2586097 | Split billed cost actuals aren't reversed when a project is removed from project contract line. |
| Billing and pricing | 2589619 | Tax on write-in material is propagating to unbilled sales actuals and the invoice. |
| Opportunity management | 2594015 | Unable to close a quote as won for customer's with a **Net60** payment term. |
| Project planning and tracking | 2595841 | In Project for the Web, users are shown an error about missing **msdyn\_actualstart** when they create a new resource request. |
| Time and Expense | 2602511 | The **Rejected by** field for time entries is listing **System** as the rejector instead of the named user. |
| Time and Expense | 2602528 | A project approver can approve time on projects where they aren't listed as an approver. |
| Billing and pricing | 2608550 | A correction invoice can be confirmed even if there are no changes from the original. |

### Project management and accounting on Dynamics 365 Finance

| Feature area | Reference number | Quality update |
| --- | --- | --- |
| Project management and accounting | [606759](https://nam06.safelinks.protection.outlook.com/?url=https:%2F%2Ffix.lcs.dynamics.com%2FIssue%2FDetails%2F?bugId%3D606759&amp;data=04%7C01%7Chmahl%40microsoft.com%7Ce0aa497efe5d44aacb8d08d9f3492410%7C72f988bf86f141af91ab2d7cd011db47%7C1%7C0%7C637808317817553152%7CUnknown%7CTWFpbGZsb3d8eyJWIjoiMC4wLjAwMDAiLCJQIjoiV2luMzIiLCJBTiI6Ik1haWwiLCJXVCI6Mn0%3D%7C3000&amp;sdata=efabk%2BHTxmOjOqDcjxkyz9Uva3UfZaCg3Doc975%2F9HY%3D&amp;reserved=0) | There is a mismatch between Finance and Project Operations in the allowed length of the **Category ID** field. |
 | Project management and accounting | [617806](https://nam06.safelinks.protection.outlook.com/?url=https:%2F%2Ffix.lcs.dynamics.com%2FIssue%2FDetails%2F?bugId%3D617806&amp;data=04%7C01%7Chmahl%40microsoft.com%7Ce0aa497efe5d44aacb8d08d9f3492410%7C72f988bf86f141af91ab2d7cd011db47%7C1%7C0%7C637808317817603136%7CUnknown%7CTWFpbGZsb3d8eyJWIjoiMC4wLjAwMDAiLCJQIjoiV2luMzIiLCJBTiI6Ik1haWwiLCJXVCI6Mn0%3D%7C3000&amp;sdata=g6UzaNLVZz5rBEEkDBM1oceShalml1AYqYEdOr17JyY%3D&amp;reserved=0) | Fixed Price projects with On account invoicing = Profit and Loss and Completed percentage principle can't be eliminated. |
 | Project management and accounting | [620979](https://nam06.safelinks.protection.outlook.com/?url=https:%2F%2Ffix.lcs.dynamics.com%2FIssue%2FDetails%2F?bugId%3D620979&amp;data=04%7C01%7Chmahl%40microsoft.com%7Ce0aa497efe5d44aacb8d08d9f3492410%7C72f988bf86f141af91ab2d7cd011db47%7C1%7C0%7C637808317817603136%7CUnknown%7CTWFpbGZsb3d8eyJWIjoiMC4wLjAwMDAiLCJQIjoiV2luMzIiLCJBTiI6Ik1haWwiLCJXVCI6Mn0%3D%7C3000&amp;sdata=sI5NvvGoMbzCeQRbOQkCYG8vApJSeQh6MvFZrNzrCFw%3D&amp;reserved=0) | The wrong sales tax group defaults from the project setup on expense lines in the Project Operations integration journal. |
 | Project management and accounting | [623014](https://nam06.safelinks.protection.outlook.com/?url=https:%2F%2Ffix.lcs.dynamics.com%2FIssue%2FDetails%2F?bugId%3D623014&amp;data=04%7C01%7Chmahl%40microsoft.com%7Ce0aa497efe5d44aacb8d08d9f3492410%7C72f988bf86f141af91ab2d7cd011db47%7C1%7C0%7C637808317817653119%7CUnknown%7CTWFpbGZsb3d8eyJWIjoiMC4wLjAwMDAiLCJQIjoiV2luMzIiLCJBTiI6Ik1haWwiLCJXVCI6Mn0%3D%7C3000&amp;sdata=9FsE7BZwBwXsLlUx%2BAEJDlciT3i8U90iBooo8yavhIw%3D&amp;reserved=0) | You can't amend the project invoice proposal header dimensions in an integrated deployment with Project Operations. |
 | Project management and accounting | [624283](https://nam06.safelinks.protection.outlook.com/?url=https:%2F%2Ffix.lcs.dynamics.com%2FIssue%2FDetails%2F?bugId%3D624283&amp;data=04%7C01%7Chmahl%40microsoft.com%7Ce0aa497efe5d44aacb8d08d9f3492410%7C72f988bf86f141af91ab2d7cd011db47%7C1%7C0%7C637808317817653119%7CUnknown%7CTWFpbGZsb3d8eyJWIjoiMC4wLjAwMDAiLCJQIjoiV2luMzIiLCJBTiI6Ik1haWwiLCJXVCI6Mn0%3D%7C3000&amp;sdata=L3wB659DDa5UAkDF3bhNnzjhZaMfcnri%2Fs9IYp39E%2Fc%3D&amp;reserved=0) | Intercompany vendor invoices must not be integrated to Dataverse. |
 | Project management and accounting | [634156](https://nam06.safelinks.protection.outlook.com/?url=https:%2F%2Ffix.lcs.dynamics.com%2FIssue%2FDetails%2F?bugId%3D634156&amp;data=04%7C01%7Chmahl%40microsoft.com%7Ce0aa497efe5d44aacb8d08d9f3492410%7C72f988bf86f141af91ab2d7cd011db47%7C1%7C0%7C637808317817853086%7CUnknown%7CTWFpbGZsb3d8eyJWIjoiMC4wLjAwMDAiLCJQIjoiV2luMzIiLCJBTiI6Ik1haWwiLCJXVCI6Mn0%3D%7C3000&amp;sdata=1v5ZafckozDnVKsg4pcLFDmL9Gd7pU2vMHQ1pgDvzgo%3D&amp;reserved=0) | There is a mismatch in the Customer Balances Currency and the Reporting Currency. |
 | Project management and accounting | [641612](https://nam06.safelinks.protection.outlook.com/?url=https:%2F%2Ffix.lcs.dynamics.com%2FIssue%2FDetails%2F?bugId%3D641612&amp;data=04%7C01%7Chmahl%40microsoft.com%7Ce0aa497efe5d44aacb8d08d9f3492410%7C72f988bf86f141af91ab2d7cd011db47%7C1%7C0%7C637808317817953066%7CUnknown%7CTWFpbGZsb3d8eyJWIjoiMC4wLjAwMDAiLCJQIjoiV2luMzIiLCJBTiI6Ik1haWwiLCJXVCI6Mn0%3D%7C3000&amp;sdata=NWRerwV4HhddY8bxSReAi2ax1VDK42UqXIyLvM9J9xU%3D&amp;reserved=0) | You can post a project invoice even if customer is on-hold for all invoices. |
 | Project management and accounting | [642945](https://nam06.safelinks.protection.outlook.com/?url=https:%2F%2Ffix.lcs.dynamics.com%2FIssue%2FDetails%2F?bugId%3D642945&amp;data=04%7C01%7Chmahl%40microsoft.com%7Ce0aa497efe5d44aacb8d08d9f3492410%7C72f988bf86f141af91ab2d7cd011db47%7C1%7C0%7C637808317817953066%7CUnknown%7CTWFpbGZsb3d8eyJWIjoiMC4wLjAwMDAiLCJQIjoiV2luMzIiLCJBTiI6Ik1haWwiLCJXVCI6Mn0%3D%7C3000&amp;sdata=%2FrQjz1BncOwgzz03nS8soqb90m3G7axqhREJU87Nhb8%3D&amp;reserved=0) | Oroject invoice proposals with the **Header** and **Lines** view is missing the **Delete all lines** button. |
 | Project management and accounting | [637760](https://nam06.safelinks.protection.outlook.com/?url=https:%2F%2Ffix.lcs.dynamics.com%2FIssue%2FDetails%2F?bugId%3D637760&amp;data=04%7C01%7Chmahl%40microsoft.com%7Ce0aa497efe5d44aacb8d08d9f3492410%7C72f988bf86f141af91ab2d7cd011db47%7C1%7C0%7C637808317818452927%7CUnknown%7CTWFpbGZsb3d8eyJWIjoiMC4wLjAwMDAiLCJQIjoiV2luMzIiLCJBTiI6Ik1haWwiLCJXVCI6Mn0%3D%7C3000&amp;sdata=oxB6h2Tok5Iba4FN%2B6tlnMW3xE9wphvJi3vPpC6jOQ8%3D&amp;reserved=0) | When you post a vendor invoice, the following error occurs: **The accounting date for the invoice must be in the same accounting year as the related purchased order. Run the purchase order year-end process or change the date to the current accounting year.** |
 | Travel and Expense | [604128](https://nam06.safelinks.protection.outlook.com/?url=https:%2F%2Ffix.lcs.dynamics.com%2FIssue%2FDetails%2F?bugId%3D604128&amp;data=04%7C01%7Chmahl%40microsoft.com%7Ce0aa497efe5d44aacb8d08d9f3492410%7C72f988bf86f141af91ab2d7cd011db47%7C1%7C0%7C637808317817553152%7CUnknown%7CTWFpbGZsb3d8eyJWIjoiMC4wLjAwMDAiLCJQIjoiV2luMzIiLCJBTiI6Ik1haWwiLCJXVCI6Mn0%3D%7C3000&amp;sdata=J%2F7M4x%2BCVkFfxxHm8LOn0npS6QfSGpDe6xJKZ1L910M%3D&amp;reserved=0) | The committed cost for a project isn't released after closing the travel requisition's committed cost. |
 | Travel and Expense | [620803](https://nam06.safelinks.protection.outlook.com/?url=https:%2F%2Ffix.lcs.dynamics.com%2FIssue%2FDetails%2F?bugId%3D620803&amp;data=04%7C01%7Chmahl%40microsoft.com%7Ce0aa497efe5d44aacb8d08d9f3492410%7C72f988bf86f141af91ab2d7cd011db47%7C1%7C0%7C637808317817603136%7CUnknown%7CTWFpbGZsb3d8eyJWIjoiMC4wLjAwMDAiLCJQIjoiV2luMzIiLCJBTiI6Ik1haWwiLCJXVCI6Mn0%3D%7C3000&amp;sdata=S8Bpa5l%2FJhr4ySOjLIJdP9Cep53Zoa9D8fgacAU%2FTng%3D&amp;reserved=0) | The following error occurs when you submit an expense report: **Stack Trace: The company does not exist**. |
 | Travel and Expense | [622465](https://nam06.safelinks.protection.outlook.com/?url=https:%2F%2Ffix.lcs.dynamics.com%2FIssue%2FDetails%2F?bugId%3D622465&amp;data=04%7C01%7Chmahl%40microsoft.com%7Ce0aa497efe5d44aacb8d08d9f3492410%7C72f988bf86f141af91ab2d7cd011db47%7C1%7C0%7C637808317817653119%7CUnknown%7CTWFpbGZsb3d8eyJWIjoiMC4wLjAwMDAiLCJQIjoiV2luMzIiLCJBTiI6Ik1haWwiLCJXVCI6Mn0%3D%7C3000&amp;sdata=Yz211grpXqdnCT2jT26698GiPF%2F484fQbWPiBi806zA%3D&amp;reserved=0) | The **Project ID** doesn't default on expense reports when the **Require activity for journal** parameter is selected on the project. |
 | Travel and Expense | [626781](https://nam06.safelinks.protection.outlook.com/?url=https:%2F%2Ffix.lcs.dynamics.com%2FIssue%2FDetails%2F?bugId%3D626781&amp;data=04%7C01%7Chmahl%40microsoft.com%7Ce0aa497efe5d44aacb8d08d9f3492410%7C72f988bf86f141af91ab2d7cd011db47%7C1%7C0%7C637808317817702721%7CUnknown%7CTWFpbGZsb3d8eyJWIjoiMC4wLjAwMDAiLCJQIjoiV2luMzIiLCJBTiI6Ik1haWwiLCJXVCI6Mn0%3D%7C3000&amp;sdata=d8Hy%2B6OjPHMhLNnutceh3nuiTau6VeG%2BfYTCkp9jNVg%3D&amp;reserved=0) | The **Post Expenses** button doesn't work correctly om Project Operations for Resource/non-stocked scenarios. |
 | Travel and Expense | [635348](https://nam06.safelinks.protection.outlook.com/?url=https:%2F%2Ffix.lcs.dynamics.com%2FIssue%2FDetails%2F?bugId%3D635348&amp;data=04%7C01%7Chmahl%40microsoft.com%7Ce0aa497efe5d44aacb8d08d9f3492410%7C72f988bf86f141af91ab2d7cd011db47%7C1%7C0%7C637808317817853086%7CUnknown%7CTWFpbGZsb3d8eyJWIjoiMC4wLjAwMDAiLCJQIjoiV2luMzIiLCJBTiI6Ik1haWwiLCJXVCI6Mn0%3D%7C3000&amp;sdata=p1QdfgFO9Hiat9DVYsAEM%2BEwMRo2PjIJO7%2BfXA038CA%3D&amp;reserved=0) | There is an issue with **Rate per mile** for a mileage expense report that includes passengers. |
 | Travel and Expense | [638019](https://nam06.safelinks.protection.outlook.com/?url=https:%2F%2Ffix.lcs.dynamics.com%2FIssue%2FDetails%2F?bugId%3D638019&amp;data=04%7C01%7Chmahl%40microsoft.com%7Ce0aa497efe5d44aacb8d08d9f3492410%7C72f988bf86f141af91ab2d7cd011db47%7C1%7C0%7C637808317817903075%7CUnknown%7CTWFpbGZsb3d8eyJWIjoiMC4wLjAwMDAiLCJQIjoiV2luMzIiLCJBTiI6Ik1haWwiLCJXVCI6Mn0%3D%7C3000&amp;sdata=o5XqzhPUD2PmAzHlyDKzDfAomOpmeexeHA7WxGP0D6Y%3D&amp;reserved=0) | Expense mileage rates for employees aren't totaling correctly when two different vehicle types are used in the expense category, **Mileage rate tiers**. |
 | Travel and Expense | [641272](https://nam06.safelinks.protection.outlook.com/?url=https:%2F%2Ffix.lcs.dynamics.com%2FIssue%2FDetails%2F?bugId%3D641272&amp;data=04%7C01%7Chmahl%40microsoft.com%7Ce0aa497efe5d44aacb8d08d9f3492410%7C72f988bf86f141af91ab2d7cd011db47%7C1%7C0%7C637808317817953066%7CUnknown%7CTWFpbGZsb3d8eyJWIjoiMC4wLjAwMDAiLCJQIjoiV2luMzIiLCJBTiI6Ik1haWwiLCJXVCI6Mn0%3D%7C3000&amp;sdata=rxlrHAsNf5QyU0fjCwmInvGKBvWR991YE5EmB0KimYo%3D&amp;reserved=0) | The **Project** field look-up on a travel requisition line isn't returning the correct list of projects. |
 | Travel and Expense | [645905](https://nam06.safelinks.protection.outlook.com/?url=https:%2F%2Ffix.lcs.dynamics.com%2FIssue%2FDetails%2F?bugId%3D645905&amp;data=04%7C01%7Chmahl%40microsoft.com%7Ce0aa497efe5d44aacb8d08d9f3492410%7C72f988bf86f141af91ab2d7cd011db47%7C1%7C0%7C637808317818003025%7CUnknown%7CTWFpbGZsb3d8eyJWIjoiMC4wLjAwMDAiLCJQIjoiV2luMzIiLCJBTiI6Ik1haWwiLCJXVCI6Mn0%3D%7C3000&amp;sdata=X%2FqcJod3HdTQ8zdJJUQn5AiB2CPLR83BwVL36rUgNso%3D&amp;reserved=0) | The **Mileage in review** shows a warning in expense reports. |
 | Travel and Expense | [647819](https://nam06.safelinks.protection.outlook.com/?url=https:%2F%2Ffix.lcs.dynamics.com%2FIssue%2FDetails%2F?bugId%3D647819&amp;data=04%7C01%7Chmahl%40microsoft.com%7Ce0aa497efe5d44aacb8d08d9f3492410%7C72f988bf86f141af91ab2d7cd011db47%7C1%7C0%7C637808317818003025%7CUnknown%7CTWFpbGZsb3d8eyJWIjoiMC4wLjAwMDAiLCJQIjoiV2luMzIiLCJBTiI6Ik1haWwiLCJXVCI6Mn0%3D%7C3000&amp;sdata=JMHUsT%2BNu2uWPfw1QQ0F%2BrQvJbTWBRUp9MnSN3yVJqo%3D&amp;reserved=0) | The receipt OCR service is not working because of an issue with the expense OCR service URL. |
 | Travel and Expense | [648684](https://nam06.safelinks.protection.outlook.com/?url=https:%2F%2Ffix.lcs.dynamics.com%2FIssue%2FDetails%2F?bugId%3D648684&amp;data=04%7C01%7Chmahl%40microsoft.com%7Ce0aa497efe5d44aacb8d08d9f3492410%7C72f988bf86f141af91ab2d7cd011db47%7C1%7C0%7C637808317818552494%7CUnknown%7CTWFpbGZsb3d8eyJWIjoiMC4wLjAwMDAiLCJQIjoiV2luMzIiLCJBTiI6Ik1haWwiLCJXVCI6Mn0%3D%7C3000&amp;sdata=9sf6y4AydLEN%2F8s%2B2qc5T4vMhBsT4Fh0r8N8l%2BgT3AM%3D&amp;reserved=0) | With the feature, **Ability to itemize recurring expenses quickly** enabled, itemization lines in Expense reports are getting changed amounts every time the **Itemize** page is opened. |
 | Travel and Expense | [651899](https://nam06.safelinks.protection.outlook.com/?url=https:%2F%2Ffix.lcs.dynamics.com%2FIssue%2FDetails%2F?bugId%3D651899&amp;data=04%7C01%7Chmahl%40microsoft.com%7Ce0aa497efe5d44aacb8d08d9f3492410%7C72f988bf86f141af91ab2d7cd011db47%7C1%7C0%7C637808317818552494%7CUnknown%7CTWFpbGZsb3d8eyJWIjoiMC4wLjAwMDAiLCJQIjoiV2luMzIiLCJBTiI6Ik1haWwiLCJXVCI6Mn0%3D%7C3000&amp;sdata=PosFhqudYQgYQnQrHfhYOmFhrKaREvi%2FNwkdtxcTLpQ%3D&amp;reserved=0) | Can't delete an expense report when the **Interim list** has more than one approver. |
 
## Removed and depreciated features
The [Removed or deprecated features in Project Operations](removed-depreciated-features-project.md) topic describes features that have been removed or deprecated for Dynamics 365 Project Operations.

- A removed feature is no longer available in the product.
- A deprecated feature is not in active development and may be removed in a future update.

Before any feature is removed from the product, the deprecation notice will be announced in the [Removed or deprecated features in Project Operations](removed-depreciated-features-project.md) topic 12 months prior to the removal.

For breaking changes that only affect compilation time, but are binary compatible with sandbox and production environments, the deprecation time will be less than 12 months. Typically, these are functional updates that need to be made to the compiler.
