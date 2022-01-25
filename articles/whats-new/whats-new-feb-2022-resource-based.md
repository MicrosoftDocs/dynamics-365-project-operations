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

- With this release, you can add up to 300 team members to a single project. Previously, the maximum team member limit was 150. For more information, see [Project limits](../project-management/create-wbs.md#project-limitations).


## Project Operations dual-write maps updates

The following list shows the dual-write maps that have been modified or added in the Project Operations February 2022 release.

| Entity map | Updated version | Comments |
| --- | --- | --- |
| Project Operations integration project expenses export entity (msdyn\_expenses) | 1.0.0.3 | Extended for project activity sync to Dataverse. |

For a current list and versions of Project Operations dual-write maps, see [Project Operations dual-write map versions](../environment/resource-dual-write-maps.md).

Always run the latest version of the map in your environment, and enable all related table maps as you update your Project Operations Dataverse solution and Finance solution version. Some features and capabilities might not work correctly if the latest version of the map isn't activated. You can view the active version of the map in the **Version** column on the **Dual-write** page. To activate a new version of the map, select **Table map versions**, select the latest version, and then save the selected version. If you've customized an out-of-box table map, reapply the changes. For more information, see [Application lifecycle management](/dynamics365/fin-ops-core/dev-itpro/data-entities/dual-write/app-lifecycle-management).

If you encounter an issue when you start the map, follow the instructions in the [Missing table columns issue on maps](/dynamics365/fin-ops-core/dev-itpro/data-entities/dual-write/dual-write-troubleshooting-finops-upgrades#missing-table-columns-issue-on-maps) section of the Dual Write troubleshooting guide.

## Quality updates

### Project Operations on Dataverse

| **Feature area** | **Reference number** | **Quality update** |
| --- | --- | --- |
| Billing and pricing | 2415109 | The **Operations payment terms** field must default to the project contract customer record and to the proforma invoice record. |
| Billing and pricing | 2497369 | Material correction must follow the date value on the **Correction** parameters. |
| Billing and pricing | 2498697 | Improved security configuration for **Time entry recall**.  |
| Billing and pricing | 2513824 | The transaction category ID must not exceed 28 characters in Project Operations for resource-based scenarios. |
| Billing and pricing | 2517455 | The **Refresh invoice line transactions** action must not be allowed to trigger multiple times for the same invoice simultaneously. |
| Billing and pricing | 2517465 | The **Deactivate invoice line details** action is blocked because it isn't supported. |
| Billing and pricing | 2556660 | Fixed data effectivity check on the pricelist that' attached to project parameters record. |
| Opportunity management | 2369202 | Corrected the business logic that verifes pricelists with overlapping effectivity dates can be attached to the same project contract. |
| Opportunity management | 2385965 | Corrected the behavior on the **Project contract** page, on the **Customers** tab, when you select **Save and close**. |
| Time and expense | 2538503 | A project task must be available in the **Project actuals** entity after an expense report is posted. |

### Project management and accounting on Dynamics 365 Finance

| Feature area | Reference number | Quality update |
| --- | --- | --- |
| Project management and accounting | [615496](https://nam06.safelinks.protection.outlook.com/?url=https:%2F%2Ffix.lcs.dynamics.com%2FIssue%2FDetails%2F?bugId%3D615496&amp;data=04%7C01%7Cjespers%40microsoft.com%7Ccde64220313744574dff08d9cf624d02%7C72f988bf86f141af91ab2d7cd011db47%7C1%7C0%7C637768843396140874%7CUnknown%7CTWFpbGZsb3d8eyJWIjoiMC4wLjAwMDAiLCJQIjoiV2luMzIiLCJBTiI6Ik1haWwiLCJXVCI6Mn0%3D%7C3000&amp;sdata=m1K5WtUYIA7s4iA3uSARABIMj6FmMQ2lk1l4r%2BV1D04%3D&amp;reserved=0) | An error occurs during import of vendor credit notes that says, "Retainage amount can't be more than remaining net amount." |
| Project management and accounting | [619391](https://nam06.safelinks.protection.outlook.com/?url=https:%2F%2Ffix.lcs.dynamics.com%2FIssue%2FDetails%2F?bugId%3D619391&amp;data=04%7C01%7Cjespers%40microsoft.com%7Ccde64220313744574dff08d9cf624d02%7C72f988bf86f141af91ab2d7cd011db47%7C1%7C0%7C637768843396240210%7CUnknown%7CTWFpbGZsb3d8eyJWIjoiMC4wLjAwMDAiLCJQIjoiV2luMzIiLCJBTiI6Ik1haWwiLCJXVCI6Mn0%3D%7C3000&amp;sdata=C%2F1%2F8KorFa6DpHfSLlS2cLQwft5L%2BbzqcYgTFi%2BMAaU%3D&amp;reserved=0) | If an invoice proposal includes any zero amount fee transactions that are unbilled sales actuals, invoicing can’t occur. |
| Project management and accounting | [624423](https://nam06.safelinks.protection.outlook.com/?url=https:%2F%2Ffix.lcs.dynamics.com%2FIssue%2FDetails%2F?bugId%3D624423&amp;data=04%7C01%7Cjespers%40microsoft.com%7Ccde64220313744574dff08d9cf624d02%7C72f988bf86f141af91ab2d7cd011db47%7C1%7C0%7C637768843396340202%7CUnknown%7CTWFpbGZsb3d8eyJWIjoiMC4wLjAwMDAiLCJQIjoiV2luMzIiLCJBTiI6Ik1haWwiLCJXVCI6Mn0%3D%7C3000&amp;sdata=WrI4s82plAt8pz%2FqJYbU2ktMDnEWR%2B%2FtbwWqexCDB%2FE%3D&amp;reserved=0) | The posted cost isn't correct after the purchase price updated and **Activate change management** is enabled.|
| Project management and accounting | [628386](https://nam06.safelinks.protection.outlook.com/?url=https:%2F%2Ffix.lcs.dynamics.com%2FIssue%2FDetails%2F?bugId%3D628386&amp;data=04%7C01%7Cjespers%40microsoft.com%7Ccde64220313744574dff08d9cf624d02%7C72f988bf86f141af91ab2d7cd011db47%7C1%7C0%7C637768843396440176%7CUnknown%7CTWFpbGZsb3d8eyJWIjoiMC4wLjAwMDAiLCJQIjoiV2luMzIiLCJBTiI6Ik1haWwiLCJXVCI6Mn0%3D%7C3000&amp;sdata=pQ%2FU%2FwFbTvUh3S1qwW0HjrBps%2F6Eb9n0jPY1j0OB9%2BQ%3D&amp;reserved=0) | The posting estimate for a fixed -price project uses the wrong currency and amount in the estimate voucher even with the feature **Enable project contract currency for estimate calculation** enabled. |
| Project management and accounting | [629239](https://nam06.safelinks.protection.outlook.com/?url=https:%2F%2Ffix.lcs.dynamics.com%2FIssue%2FDetails%2F?bugId%3D629239&amp;data=04%7C01%7Cjespers%40microsoft.com%7Ccde64220313744574dff08d9cf624d02%7C72f988bf86f141af91ab2d7cd011db47%7C1%7C0%7C637768843396490159%7CUnknown%7CTWFpbGZsb3d8eyJWIjoiMC4wLjAwMDAiLCJQIjoiV2luMzIiLCJBTiI6Ik1haWwiLCJXVCI6Mn0%3D%7C3000&amp;sdata=hI51ruLaCaxJMukZmp80xVDKyef4y0G7bL0oVVM2ukg%3D&amp;reserved=0) | **ProjDMFDataPopulation\_Extension** shouldn't call to enable change tracking wtihout catching exceptions for entities that have configuration keys that aren't enabled. |
| Project management and accounting | [623818](https://nam06.safelinks.protection.outlook.com/?url=https:%2F%2Ffix.lcs.dynamics.com%2FIssue%2FDetails%2F?bugId%3D623818&amp;data=04%7C01%7Cjespers%40microsoft.com%7Ccde64220313744574dff08d9cf624d02%7C72f988bf86f141af91ab2d7cd011db47%7C1%7C0%7C637768843397089977%7CUnknown%7CTWFpbGZsb3d8eyJWIjoiMC4wLjAwMDAiLCJQIjoiV2luMzIiLCJBTiI6Ik1haWwiLCJXVCI6Mn0%3D%7C3000&amp;sdata=RwnA4k%2Bd0ywlyO%2BiXYZENP%2BF%2FewSkEk8d17CPOmCMXY%3D&amp;reserved=0) | The batch job is  fixed when multiple advanced journals are posted and an error occurs. |
| Travel and Expense | [616805](https://nam06.safelinks.protection.outlook.com/?url=https:%2F%2Ffix.lcs.dynamics.com%2FIssue%2FDetails%2F?bugId%3D616805&amp;data=04%7C01%7Cjespers%40microsoft.com%7Ccde64220313744574dff08d9cf624d02%7C72f988bf86f141af91ab2d7cd011db47%7C1%7C0%7C637768843396190243%7CUnknown%7CTWFpbGZsb3d8eyJWIjoiMC4wLjAwMDAiLCJQIjoiV2luMzIiLCJBTiI6Ik1haWwiLCJXVCI6Mn0%3D%7C3000&amp;sdata=iupyrs7kagbFpPzxWLqbTrwzmDxeH%2BidY35sOx61hwI%3D&amp;reserved=0) | There is a settlement issue related to cash advance on expense reports because the tax amount isn't covered as part of the cash advance. |
| Travel and Expense | [616959](https://nam06.safelinks.protection.outlook.com/?url=https:%2F%2Ffix.lcs.dynamics.com%2FIssue%2FDetails%2F?bugId%3D616959&amp;data=04%7C01%7Cjespers%40microsoft.com%7Ccde64220313744574dff08d9cf624d02%7C72f988bf86f141af91ab2d7cd011db47%7C1%7C0%7C637768843396190243%7CUnknown%7CTWFpbGZsb3d8eyJWIjoiMC4wLjAwMDAiLCJQIjoiV2luMzIiLCJBTiI6Ik1haWwiLCJXVCI6Mn0%3D%7C3000&amp;sdata=R2%2FLb4iuD6jWTUlyjjWPuh%2FkMK5MZ6useYvZE2itBxA%3D&amp;reserved=0) | Sales tax information isn't included on the **Expense - Posted transactions** report. |
| Travel and Expense | [618943](https://nam06.safelinks.protection.outlook.com/?url=https:%2F%2Ffix.lcs.dynamics.com%2FIssue%2FDetails%2F?bugId%3D618943&amp;data=04%7C01%7Cjespers%40microsoft.com%7Ccde64220313744574dff08d9cf624d02%7C72f988bf86f141af91ab2d7cd011db47%7C1%7C0%7C637768843396190243%7CUnknown%7CTWFpbGZsb3d8eyJWIjoiMC4wLjAwMDAiLCJQIjoiV2luMzIiLCJBTiI6Ik1haWwiLCJXVCI6Mn0%3D%7C3000&amp;sdata=X9aSlQ24OWpUSe87Q9IwRgBf23CRsz2OitpS1PNzqMg%3D&amp;reserved=0) | The **Receipts Required** expense policy violation incorrectly shows a warning on expense reports. |
| Travel and Expense | [633470](https://nam06.safelinks.protection.outlook.com/?url=https:%2F%2Ffix.lcs.dynamics.com%2FIssue%2FDetails%2F?bugId%3D633470&amp;data=04%7C01%7Cjespers%40microsoft.com%7Ccde64220313744574dff08d9cf624d02%7C72f988bf86f141af91ab2d7cd011db47%7C1%7C0%7C637768843397189952%7CUnknown%7CTWFpbGZsb3d8eyJWIjoiMC4wLjAwMDAiLCJQIjoiV2luMzIiLCJBTiI6Ik1haWwiLCJXVCI6Mn0%3D%7C3000&amp;sdata=MeeRbpbvTmUJaqKCcQAl35ELr1x0SXlHqiyXCGhIFg8%3D&amp;reserved=0) | A project transaction doesn't include non-recoverable sales tax in the total sales amount when the transaction is a result of a mileage expense. |
| Travel and Expense | [642979](https://nam06.safelinks.protection.outlook.com/?url=https:%2F%2Ffix.lcs.dynamics.com%2FIssue%2FDetails%2F?bugId%3D642979&amp;data=04%7C01%7Cjespers%40microsoft.com%7Ccde64220313744574dff08d9cf624d02%7C72f988bf86f141af91ab2d7cd011db47%7C1%7C0%7C637768843397289944%7CUnknown%7CTWFpbGZsb3d8eyJWIjoiMC4wLjAwMDAiLCJQIjoiV2luMzIiLCJBTiI6Ik1haWwiLCJXVCI6Mn0%3D%7C3000&amp;sdata=nhCn86ZztFp%2Ba68Ni%2FkaUDTVOgsJwCfwU82u%2F1BzCsU%3D&amp;reserved=0) | When an itemized line has tax, you can’t change the itemization line date and a source document state error occurs.  |
