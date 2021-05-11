---
title: What's new May 2021 - Project Operations for resource/non-stocked based scenarios
description: This topic provides information about the quality updates available in the May 2021 release of Project Operations for resource/non-stocked based scenarios.
author: sigitac
ms.date: 04/22/2021
ms.topic: article
ms.prod:
ms.reviewer: kfend 
ms.author: sigitac
---

# What's new May 2021 - Project Operations for resource/non-stocked based scenarios

This topic applies to the following Dynamics 365 Project Operations components and versions:

| Project Operations on Dataverse | Project management and accounting on Dynamics 365 F&amp;O environment |
| --- | --- |
| 4.10.0.186 | 10.0.18 |

## Features included in this release

The following features are included in this release:

- [Scheduling modes](https://docs.microsoft.com/en-us/dynamics365/project-operations/project-management/scheduling-modes) – project managers now have ability to define if project should be managed using fixed duration, fixed work or fixed units scheduling mode.

## Project Operations dual-write maps updates

The following list shows the dual-write maps that have been modified or added in the Project Operations May ew2021 release.

| Entity map | Updated version | Comments |
| --- | --- | --- |
| Project funding source (msdyn\_projectcontractsplitbillingrules) | 1.0.0.2 | Syncing project contract customer terms of payment |
| Project invoice proposal V2 (invoices) | 1.0.0.3 | Syncing proforma invoice terms of payment |
| Project Operations integration project vendor invoice line export entity (msdyn\_projectvendorinvoicelines) | 1.0.0.1 | Quality updates |
| Projects V2 (msdyn\_projects) | 1.0.0.2 | Quality updates |

You should always run the latest version of the map in your environment and enable all related table maps as you update your Project Operations Dataverse solution and Finance and Operations solution version. Certain features and capabilities might not work correctly if the latest version of the map is not activated. You can see the active version of the map in the  **Version**  column on the  **Dual-write**  page. You can activate a new version of the map by selecting  **Table map versions** , selecting the latest version, and then saving the selected version. If you have customized an out-of-the-box table map, reapply the changes. For more information, see [Application lifecycle management](https://docs.microsoft.com/en-us/dynamics365/fin-ops-core/dev-itpro/data-entities/dual-write/app-lifecycle-management).

If you encounter an issue with starting the map, follow instructions in the [Missing table columns issue on maps](https://docs.microsoft.com/en-us/dynamics365/fin-ops-core/dev-itpro/data-entities/dual-write/dual-write-troubleshooting-finops-upgrades#missing-table-columns-issue-on-maps) section of the Dual Write troubleshooting guide.

## Quality updates

###

### Project Operations on Dataverse

| **Feature area** | **Reference number** | **Quality update** |
| --- | --- | --- |
| Billing and Pricing | 2227635 | Unit group and Unit are now defaulted from the product in material estimates grid. |
| Billing and Pricing | 2234127 | Task ID now correctly integrates to Dataverse Project actuals when posting vendor invoice |
| Billing and Pricing | 2235564 | Saving journal line ensures currency displayed in the journal line entry is matching currency defaulted to the line after saving it. |
| Billing and Pricing | 2246671 | Making transaction non-chargeable during invoicing must reverse original unbilled sales record and create a new unbilled sales record as non-chargeable. |
| Billing and Pricing | 2264042 | Valid Invoice correction must not be blocked if there is an invalid invoice correction detail in the environment |
| Billing and Pricing | 2146367 | Project invoice header Dual Write mapping extended to include payment terms |
| Opportunity management | 2086888 | Roles and categories that are deactivated before coping a quote must not be added to chargeable roles and categories of new copied quote |
| Opportunity management | 2234376 | Read-only fields are greyed out in material estimates grid |
| Opportunity management | 2238337 | Quote based on contact must be allowed to save when not associated with a project pricelist |
| Opportunity management | 2239810 | Closing Quote as Lost must close associated project and cancel the bookings |
| Project Planning and Tracking | 2099559 | Added additional validations on system health before launching Project tasks grid |
| Project Planning and Tracking | 2178987 | Fixed transient error on click of Next Stage in Project form |
| Resource Management | 2224817 | Extending bookings functionality fixed to default to the correct booking status |
| Time entry | 2202476 | Time entry form now uses react grid control and fixed UI issues such as grid mis-alignment |
| Time entry | 2223377 | Hidden time entry from Bookable resource form Related section to avoid confusion with usability |

### Project management and accounting on Dynamics 365 Finance

| Feature area | Reference number | Quality update |
| --- | --- | --- |
| Project management and accounting | [545878](https://nam06.safelinks.protection.outlook.com/?url=https://fix.lcs.dynamics.com/Issue/Details/?bugId%3D545878&amp;data=04%7C01%7CMadina.Kasimova%40microsoft.com%7C527a9de0529a497372ff08d8f4681c02%7C72f988bf86f141af91ab2d7cd011db47%7C1%7C0%7C637528075308199981%7CUnknown%7CTWFpbGZsb3d8eyJWIjoiMC4wLjAwMDAiLCJQIjoiV2luMzIiLCJBTiI6Ik1haWwiLCJXVCI6Mn0%3D%7C1000&amp;sdata=HJExfcDrBMthX70Idwv2bLtRT10o/eWUvOKDByk2oJ4%3D&amp;reserved=0) | Project Operations for Resource based scenarios: Cannot convert quote to won due to DW integration error |
| Project management and accounting | [546604](https://nam06.safelinks.protection.outlook.com/?url=https://fix.lcs.dynamics.com/Issue/Details/?bugId%3D546604&amp;data=04%7C01%7CMadina.Kasimova%40microsoft.com%7C527a9de0529a497372ff08d8f4681c02%7C72f988bf86f141af91ab2d7cd011db47%7C1%7C0%7C637528075308209971%7CUnknown%7CTWFpbGZsb3d8eyJWIjoiMC4wLjAwMDAiLCJQIjoiV2luMzIiLCJBTiI6Ik1haWwiLCJXVCI6Mn0%3D%7C1000&amp;sdata=ZDdWabLbklsptYeWArRI82o8lE9UKNU55q5XuHSCO4g%3D&amp;reserved=0) | [ProjOps] Error message when trying to create contract line to ProjectId association because of check for overlapping contract lines/transaction types |
| Project management and accounting | [547440](https://nam06.safelinks.protection.outlook.com/?url=https://fix.lcs.dynamics.com/Issue/Details/?bugId%3D547440&amp;data=04%7C01%7CMadina.Kasimova%40microsoft.com%7C527a9de0529a497372ff08d8f4681c02%7C72f988bf86f141af91ab2d7cd011db47%7C1%7C0%7C637528075308219966%7CUnknown%7CTWFpbGZsb3d8eyJWIjoiMC4wLjAwMDAiLCJQIjoiV2luMzIiLCJBTiI6Ik1haWwiLCJXVCI6Mn0%3D%7C1000&amp;sdata=tQkUOz%2BXzjxUduYRbamS7wu62t1CT3cLaNpNLBkesgc%3D&amp;reserved=0) | ProjCDSProjectContractEntity can set funding source invoice address from different customer |
| Travel and Expense | [480451](https://nam06.safelinks.protection.outlook.com/?url=https://fix.lcs.dynamics.com/Issue/Details/?bugId%3D480451&amp;data=04%7C01%7CMadina.Kasimova%40microsoft.com%7C527a9de0529a497372ff08d8f4681c02%7C72f988bf86f141af91ab2d7cd011db47%7C1%7C0%7C637528075306001243%7CUnknown%7CTWFpbGZsb3d8eyJWIjoiMC4wLjAwMDAiLCJQIjoiV2luMzIiLCJBTiI6Ik1haWwiLCJXVCI6Mn0%3D%7C1000&amp;sdata=PjvRsgAgOu7/KKGnEXP5vigpU3gWOmfGjMloivMsaVI%3D&amp;reserved=0) | Posting error related to mileage setup |
| Travel and Expense | [522084](https://nam06.safelinks.protection.outlook.com/?url=https://fix.lcs.dynamics.com/Issue/Details/?bugId%3D522084&amp;data=04%7C01%7CMadina.Kasimova%40microsoft.com%7C527a9de0529a497372ff08d8f4681c02%7C72f988bf86f141af91ab2d7cd011db47%7C1%7C0%7C637528075306061205%7CUnknown%7CTWFpbGZsb3d8eyJWIjoiMC4wLjAwMDAiLCJQIjoiV2luMzIiLCJBTiI6Ik1haWwiLCJXVCI6Mn0%3D%7C1000&amp;sdata=LDyMtQ7C6ABQk2k1EySBzqQuY39XNCAyfr/rAZFlLKM%3D&amp;reserved=0) | Split to personal for foreign currency expense transactions not working |
| Travel and Expense | [523938](https://nam06.safelinks.protection.outlook.com/?url=https://fix.lcs.dynamics.com/Issue/Details/?bugId%3D523938&amp;data=04%7C01%7CMadina.Kasimova%40microsoft.com%7C527a9de0529a497372ff08d8f4681c02%7C72f988bf86f141af91ab2d7cd011db47%7C1%7C0%7C637528075306071200%7CUnknown%7CTWFpbGZsb3d8eyJWIjoiMC4wLjAwMDAiLCJQIjoiV2luMzIiLCJBTiI6Ik1haWwiLCJXVCI6Mn0%3D%7C1000&amp;sdata=xzoP5pzxDw3pV1tesAtuAi9FCYkbysBdx1E/hlD3wvI%3D&amp;reserved=0) | Expense category dropdown values are displaying incorrect categories if delegates is a resource or even if delegate is NOT a resource |
| Travel and Expense | [539266](https://nam06.safelinks.protection.outlook.com/?url=https://fix.lcs.dynamics.com/Issue/Details/?bugId%3D539266&amp;data=04%7C01%7CMadina.Kasimova%40microsoft.com%7C527a9de0529a497372ff08d8f4681c02%7C72f988bf86f141af91ab2d7cd011db47%7C1%7C0%7C637528075306311069%7CUnknown%7CTWFpbGZsb3d8eyJWIjoiMC4wLjAwMDAiLCJQIjoiV2luMzIiLCJBTiI6Ik1haWwiLCJXVCI6Mn0%3D%7C1000&amp;sdata=L3H1cvqZGPaTEeVQ23AS6EADPQ6oOmeuhowmw%2B6rRoM%3D&amp;reserved=0) | Intercompany Expense Report cannot save due to Resource/Category validation error |
| Travel and Expense | [532610](https://nam06.safelinks.protection.outlook.com/?url=https://fix.lcs.dynamics.com/Issue/Details/?bugId%3D532610&amp;data=04%7C01%7CMadina.Kasimova%40microsoft.com%7C527a9de0529a497372ff08d8f4681c02%7C72f988bf86f141af91ab2d7cd011db47%7C1%7C0%7C637528075308020082%7CUnknown%7CTWFpbGZsb3d8eyJWIjoiMC4wLjAwMDAiLCJQIjoiV2luMzIiLCJBTiI6Ik1haWwiLCJXVCI6Mn0%3D%7C1000&amp;sdata=ik15V%2Bd7FxMVeQQxC4i4kllQWrYB1A9zT3Odmuvg50c%3D&amp;reserved=0) | Wrong Mileage rate calculation in expense report posting has split lines |
| Travel and Expense | [537404](https://nam06.safelinks.protection.outlook.com/?url=https://fix.lcs.dynamics.com/Issue/Details/?bugId%3D537404&amp;data=04%7C01%7CMadina.Kasimova%40microsoft.com%7C527a9de0529a497372ff08d8f4681c02%7C72f988bf86f141af91ab2d7cd011db47%7C1%7C0%7C637528075308060061%7CUnknown%7CTWFpbGZsb3d8eyJWIjoiMC4wLjAwMDAiLCJQIjoiV2luMzIiLCJBTiI6Ik1haWwiLCJXVCI6Mn0%3D%7C1000&amp;sdata=RjPiXgGPOovPxGl0qoCe%2B8c5TrDG6hZBAr1AkKu4oJ8%3D&amp;reserved=0) | Cannot post intercompany expense report when sales tax is included and offset account type on the payment method is Worker |
| Travel and Expense | [542927](https://nam06.safelinks.protection.outlook.com/?url=https://fix.lcs.dynamics.com/Issue/Details/?bugId%3D542927&amp;data=04%7C01%7CMadina.Kasimova%40microsoft.com%7C527a9de0529a497372ff08d8f4681c02%7C72f988bf86f141af91ab2d7cd011db47%7C1%7C0%7C637528075308140011%7CUnknown%7CTWFpbGZsb3d8eyJWIjoiMC4wLjAwMDAiLCJQIjoiV2luMzIiLCJBTiI6Ik1haWwiLCJXVCI6Mn0%3D%7C1000&amp;sdata=gEH2zqq4LtqN2o99DU378SjDEJqxy7DyxnJmAtfK5qU%3D&amp;reserved=0) | Rollback TrvRequisitionLine Data Entity and unique index associated to the entity. |
| Travel and Expense | [543239](https://nam06.safelinks.protection.outlook.com/?url=https://fix.lcs.dynamics.com/Issue/Details/?bugId%3D543239&amp;data=04%7C01%7CMadina.Kasimova%40microsoft.com%7C527a9de0529a497372ff08d8f4681c02%7C72f988bf86f141af91ab2d7cd011db47%7C1%7C0%7C637528075308150005%7CUnknown%7CTWFpbGZsb3d8eyJWIjoiMC4wLjAwMDAiLCJQIjoiV2luMzIiLCJBTiI6Ik1haWwiLCJXVCI6Mn0%3D%7C1000&amp;sdata=TraL%2BmYzYw9pfE2KT0dD7RizN0aRfEk6bUO72ScpDto%3D&amp;reserved=0) | Instrumentation for expense report to support source document line creation/upating |
| Travel and Expense | [544323](https://nam06.safelinks.protection.outlook.com/?url=https://fix.lcs.dynamics.com/Issue/Details/?bugId%3D544323&amp;data=04%7C01%7CMadina.Kasimova%40microsoft.com%7C527a9de0529a497372ff08d8f4681c02%7C72f988bf86f141af91ab2d7cd011db47%7C1%7C0%7C637528075308179988%7CUnknown%7CTWFpbGZsb3d8eyJWIjoiMC4wLjAwMDAiLCJQIjoiV2luMzIiLCJBTiI6Ik1haWwiLCJXVCI6Mn0%3D%7C1000&amp;sdata=x22ui8bmVmoZZX64OeAOmSbGaQ4KPlox9R8Gaq0pqL8%3D&amp;reserved=0) | Incorrect subledger journal is presented to end user in Intercompany scenario if Sales tax is posted to Destination legal entity |
| Travel and Expense | [546877](https://nam06.safelinks.protection.outlook.com/?url=https://fix.lcs.dynamics.com/Issue/Details/?bugId%3D546877&amp;data=04%7C01%7CMadina.Kasimova%40microsoft.com%7C527a9de0529a497372ff08d8f4681c02%7C72f988bf86f141af91ab2d7cd011db47%7C1%7C0%7C637528075308209971%7CUnknown%7CTWFpbGZsb3d8eyJWIjoiMC4wLjAwMDAiLCJQIjoiV2luMzIiLCJBTiI6Ik1haWwiLCJXVCI6Mn0%3D%7C1000&amp;sdata=tmsXOw8MS0R1KDaqlEgsEZbk3krtYyfRM6HZWwXkxd4%3D&amp;reserved=0) | [ProjOps] Expense Estimate is not getting deleted from FnO when deleted from CE side. |
| Travel and Expense | [550575](https://nam06.safelinks.protection.outlook.com/?url=https://fix.lcs.dynamics.com/Issue/Details/?bugId%3D550575&amp;data=04%7C01%7CMadina.Kasimova%40microsoft.com%7C527a9de0529a497372ff08d8f4681c02%7C72f988bf86f141af91ab2d7cd011db47%7C1%7C0%7C637528075308269940%7CUnknown%7CTWFpbGZsb3d8eyJWIjoiMC4wLjAwMDAiLCJQIjoiV2luMzIiLCJBTiI6Ik1haWwiLCJXVCI6Mn0%3D%7C1000&amp;sdata=FUMqUK5JAvLPguJ/RkgxYDyHra15pqk5LFAJEFtz6bM%3D&amp;reserved=0) | When Expense category is Non-Project category, financial dimensions selected on Expenses page does not get copied to Expense Report. |
