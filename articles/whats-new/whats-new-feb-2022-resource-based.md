---
title: What's new February 2022 - Project Operations for resource/non-stocked based scenarios
description: This topic provides information about the quality updates that are available in the February 2022 release of Project Operations for resource/non-stocked based scenarios.
author: sigitac
ms.date: 01/24/2021
ms.topic: article
ms.prod:
ms.reviewer: kfend 
ms.author: sigitac
---

# What's new February 2022 - Project Operations for resource/non-stocked based scenarios

*Applies To: Project Operations for resource/non-stocked based scenarios*

This topic applies to the following components and versions of Microsoft Dynamics 365 Project Operations:

- Project Operations in a Dataverse environment version 4.28.0.120
- Project management and accounting in a Dynamics 365 Finance environment version 10.0.24


## Features included in this release

- With this release it is possible to add up to 300 team members to a single project (previously it was possible to add 150 team members). For more details see [Project limits](https://docs.microsoft.com/en-us/dynamics365/project-operations/project-management/create-wbs#project-limitations).


## Project Operations dual-write maps updates

The following list shows the dual-write maps that have been modified or added in the Project Operations February 2022 release.

| Entity map | Updated version | Comments |
| --- | --- | --- |
| Project Operations integration project expenses export entity (msdyn\_expenses) | 1.0.0.3 | Extended for project activity sync to Dataverse |

Please refer to [Project Operations dual-write map versions | Microsoft Docs](https://docs.microsoft.com/en-us/dynamics365/project-operations/environment/resource-dual-write-maps) for the latest list and versions of Project Operations Dual Write maps.

You should always run the latest version of the map in your environment and enable all related table maps as you update your Project Operations Dataverse solution and Finance and Operations solution version. Certain features and capabilities might not work correctly if the latest version of the map is not activated. You can see the active version of the map in the  **Version**  column on the  **Dual-write**  page. You can activate a new version of the map by selecting  **Table map versions** , selecting the latest version, and then saving the selected version. If you have customized an out-of-the-box table map, reapply the changes. For more information, see [Application lifecycle management](https://docs.microsoft.com/en-us/dynamics365/fin-ops-core/dev-itpro/data-entities/dual-write/app-lifecycle-management).

If you encounter an issue with starting the map, follow instructions in the [Missing table columns issue on maps](https://docs.microsoft.com/en-us/dynamics365/fin-ops-core/dev-itpro/data-entities/dual-write/dual-write-troubleshooting-finops-upgrades#missing-table-columns-issue-on-maps) section of the Dual Write troubleshooting guide.

##

## Quality updates

###

### Project Operations on Dataverse

| **Feature area** | **Reference number** | **Quality update** |
| --- | --- | --- |
| Billing and pricing | 2415109 | Operations payment terms field must default to Project contract customer record and to Proforma invoice record |
| Billing and pricing | 2497369 | Material correction must follow the date value on the Correction parameters |
| Billing and pricing | 2498697 | Improved security configuration for time entry recall function |
| Billing and pricing | 2513824 | Transaction category ID must not exceed 28 characters in Project Operations for resource based scenarios |
| Billing and pricing | 2517455 | Refresh invoice line transactions action must not be allowed to trigger multiple times for the same invoice simultaneously |
| Billing and pricing | 2517465 | Deactivate Invoice line details action is blocked as it is not supported. |
| Billing and pricing | 2556660 | Fixed data effectivity check on the pricelist attached to Project parameters record |
| Opportunity management | 2369202 | Corrected business logic checking no pricelists with overlap effectivity date can be attached to the same Project contract |
| Opportunity management | 2385965 | Corrected &quot;Save and close&quot; button behavior in Project contract Customers tab. |
| Time and expense | 2538503 | Project task must be available in Project actuals entity after posting Expense report in the Expense management. |

### Project management and accounting on Dynamics 365 Finance

| Feature area | Reference number | Quality update |
| --- | --- | --- |
| Project management and accounting | [615496](https://nam06.safelinks.protection.outlook.com/?url=https:%2F%2Ffix.lcs.dynamics.com%2FIssue%2FDetails%2F?bugId%3D615496&amp;data=04%7C01%7Cjespers%40microsoft.com%7Ccde64220313744574dff08d9cf624d02%7C72f988bf86f141af91ab2d7cd011db47%7C1%7C0%7C637768843396140874%7CUnknown%7CTWFpbGZsb3d8eyJWIjoiMC4wLjAwMDAiLCJQIjoiV2luMzIiLCJBTiI6Ik1haWwiLCJXVCI6Mn0%3D%7C3000&amp;sdata=m1K5WtUYIA7s4iA3uSARABIMj6FmMQ2lk1l4r%2BV1D04%3D&amp;reserved=0) | Error on importing for vendor credit notes: &quot;Retainage amount can&#39;t be more than remaining net amount&quot; |
| Project management and accounting | [619391](https://nam06.safelinks.protection.outlook.com/?url=https:%2F%2Ffix.lcs.dynamics.com%2FIssue%2FDetails%2F?bugId%3D619391&amp;data=04%7C01%7Cjespers%40microsoft.com%7Ccde64220313744574dff08d9cf624d02%7C72f988bf86f141af91ab2d7cd011db47%7C1%7C0%7C637768843396240210%7CUnknown%7CTWFpbGZsb3d8eyJWIjoiMC4wLjAwMDAiLCJQIjoiV2luMzIiLCJBTiI6Ik1haWwiLCJXVCI6Mn0%3D%7C3000&amp;sdata=C%2F1%2F8KorFa6DpHfSLlS2cLQwft5L%2BbzqcYgTFi%2BMAaU%3D&amp;reserved=0) | User can&#39;t invoice if the invoice proposal includes any 0 amount fee transaction unbilled sales actual |
| Project management and accounting | [624423](https://nam06.safelinks.protection.outlook.com/?url=https:%2F%2Ffix.lcs.dynamics.com%2FIssue%2FDetails%2F?bugId%3D624423&amp;data=04%7C01%7Cjespers%40microsoft.com%7Ccde64220313744574dff08d9cf624d02%7C72f988bf86f141af91ab2d7cd011db47%7C1%7C0%7C637768843396340202%7CUnknown%7CTWFpbGZsb3d8eyJWIjoiMC4wLjAwMDAiLCJQIjoiV2luMzIiLCJBTiI6Ik1haWwiLCJXVCI6Mn0%3D%7C3000&amp;sdata=WrI4s82plAt8pz%2FqJYbU2ktMDnEWR%2B%2FtbwWqexCDB%2FE%3D&amp;reserved=0) | The Posted cost not correct after the purchase price updated and Enable the Activate change management |
| Project management and accounting | [628386](https://nam06.safelinks.protection.outlook.com/?url=https:%2F%2Ffix.lcs.dynamics.com%2FIssue%2FDetails%2F?bugId%3D628386&amp;data=04%7C01%7Cjespers%40microsoft.com%7Ccde64220313744574dff08d9cf624d02%7C72f988bf86f141af91ab2d7cd011db47%7C1%7C0%7C637768843396440176%7CUnknown%7CTWFpbGZsb3d8eyJWIjoiMC4wLjAwMDAiLCJQIjoiV2luMzIiLCJBTiI6Ik1haWwiLCJXVCI6Mn0%3D%7C3000&amp;sdata=pQ%2FU%2FwFbTvUh3S1qwW0HjrBps%2F6Eb9n0jPY1j0OB9%2BQ%3D&amp;reserved=0) | Posting Estimate for Fixed-price project use wrong currency and amount in the Estimate voucher even with feature &#39;Enable project contract currency for estimate calculation&#39; |
| Project management and accounting | [629239](https://nam06.safelinks.protection.outlook.com/?url=https:%2F%2Ffix.lcs.dynamics.com%2FIssue%2FDetails%2F?bugId%3D629239&amp;data=04%7C01%7Cjespers%40microsoft.com%7Ccde64220313744574dff08d9cf624d02%7C72f988bf86f141af91ab2d7cd011db47%7C1%7C0%7C637768843396490159%7CUnknown%7CTWFpbGZsb3d8eyJWIjoiMC4wLjAwMDAiLCJQIjoiV2luMzIiLCJBTiI6Ik1haWwiLCJXVCI6Mn0%3D%7C3000&amp;sdata=hI51ruLaCaxJMukZmp80xVDKyef4y0G7bL0oVVM2ukg%3D&amp;reserved=0) | ProjDMFDataPopulation\_Extension should not call enable change tracking for entities with disabled config keys without catching exceptions |
| Project management and accounting | [623818](https://nam06.safelinks.protection.outlook.com/?url=https:%2F%2Ffix.lcs.dynamics.com%2FIssue%2FDetails%2F?bugId%3D623818&amp;data=04%7C01%7Cjespers%40microsoft.com%7Ccde64220313744574dff08d9cf624d02%7C72f988bf86f141af91ab2d7cd011db47%7C1%7C0%7C637768843397089977%7CUnknown%7CTWFpbGZsb3d8eyJWIjoiMC4wLjAwMDAiLCJQIjoiV2luMzIiLCJBTiI6Ik1haWwiLCJXVCI6Mn0%3D%7C3000&amp;sdata=RwnA4k%2Bd0ywlyO%2BiXYZENP%2BF%2FewSkEk8d17CPOmCMXY%3D&amp;reserved=0) | Batch job fixed when posting multiple advanced journals and error occurs. |
| Travel and Expense | [616805](https://nam06.safelinks.protection.outlook.com/?url=https:%2F%2Ffix.lcs.dynamics.com%2FIssue%2FDetails%2F?bugId%3D616805&amp;data=04%7C01%7Cjespers%40microsoft.com%7Ccde64220313744574dff08d9cf624d02%7C72f988bf86f141af91ab2d7cd011db47%7C1%7C0%7C637768843396190243%7CUnknown%7CTWFpbGZsb3d8eyJWIjoiMC4wLjAwMDAiLCJQIjoiV2luMzIiLCJBTiI6Ik1haWwiLCJXVCI6Mn0%3D%7C3000&amp;sdata=iupyrs7kagbFpPzxWLqbTrwzmDxeH%2BidY35sOx61hwI%3D&amp;reserved=0) | Settlement Issue of Expense report with Cash Advance. Tax amount is not covered part of the cash advance |
| Travel and Expense | [616959](https://nam06.safelinks.protection.outlook.com/?url=https:%2F%2Ffix.lcs.dynamics.com%2FIssue%2FDetails%2F?bugId%3D616959&amp;data=04%7C01%7Cjespers%40microsoft.com%7Ccde64220313744574dff08d9cf624d02%7C72f988bf86f141af91ab2d7cd011db47%7C1%7C0%7C637768843396190243%7CUnknown%7CTWFpbGZsb3d8eyJWIjoiMC4wLjAwMDAiLCJQIjoiV2luMzIiLCJBTiI6Ik1haWwiLCJXVCI6Mn0%3D%7C3000&amp;sdata=R2%2FLb4iuD6jWTUlyjjWPuh%2FkMK5MZ6useYvZE2itBxA%3D&amp;reserved=0) | Sales tax information not displayed in Expense - Posted transactions report |
| Travel and Expense | [618943](https://nam06.safelinks.protection.outlook.com/?url=https:%2F%2Ffix.lcs.dynamics.com%2FIssue%2FDetails%2F?bugId%3D618943&amp;data=04%7C01%7Cjespers%40microsoft.com%7Ccde64220313744574dff08d9cf624d02%7C72f988bf86f141af91ab2d7cd011db47%7C1%7C0%7C637768843396190243%7CUnknown%7CTWFpbGZsb3d8eyJWIjoiMC4wLjAwMDAiLCJQIjoiV2luMzIiLCJBTiI6Ik1haWwiLCJXVCI6Mn0%3D%7C3000&amp;sdata=X9aSlQ24OWpUSe87Q9IwRgBf23CRsz2OitpS1PNzqMg%3D&amp;reserved=0) | Receipts Required Expense Policy violation incorrectly throws warning on expense reports |
| Travel and Expense | [633470](https://nam06.safelinks.protection.outlook.com/?url=https:%2F%2Ffix.lcs.dynamics.com%2FIssue%2FDetails%2F?bugId%3D633470&amp;data=04%7C01%7Cjespers%40microsoft.com%7Ccde64220313744574dff08d9cf624d02%7C72f988bf86f141af91ab2d7cd011db47%7C1%7C0%7C637768843397189952%7CUnknown%7CTWFpbGZsb3d8eyJWIjoiMC4wLjAwMDAiLCJQIjoiV2luMzIiLCJBTiI6Ik1haWwiLCJXVCI6Mn0%3D%7C3000&amp;sdata=MeeRbpbvTmUJaqKCcQAl35ELr1x0SXlHqiyXCGhIFg8%3D&amp;reserved=0) | project transaction does not include non-recoverable sales tax in total sales amount when coming from mileage expense |
| Travel and Expense | [642979](https://nam06.safelinks.protection.outlook.com/?url=https:%2F%2Ffix.lcs.dynamics.com%2FIssue%2FDetails%2F?bugId%3D642979&amp;data=04%7C01%7Cjespers%40microsoft.com%7Ccde64220313744574dff08d9cf624d02%7C72f988bf86f141af91ab2d7cd011db47%7C1%7C0%7C637768843397289944%7CUnknown%7CTWFpbGZsb3d8eyJWIjoiMC4wLjAwMDAiLCJQIjoiV2luMzIiLCJBTiI6Ik1haWwiLCJXVCI6Mn0%3D%7C3000&amp;sdata=nhCn86ZztFp%2Ba68Ni%2FkaUDTVOgsJwCfwU82u%2F1BzCsU%3D&amp;reserved=0) | Unable to change itemization line date when itemized line has tax - Source document state error |
