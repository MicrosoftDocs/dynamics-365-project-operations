---
title: What's new September 2021 - Project Operations Integrated with ERP
description: This article provides information about the quality updates available in the September 2021 release of Project Operations Integrated with ERP.
author: sigitac
ms.custom:
  - evergreen
ms.date: 04/09/2024
ms.topic: whats-new
ms.reviewer: johnmichalak
ms.author: sigitac
---

# What's new September 2021 - Project Operations Integrated with ERP

*Applies To: Project Operations Integrated with ERP*

This article applies to the following Dynamics 365 Project Operations components and versions:

   - Project Operations in Microsoft Dataverse environment version 4.14.0.99.
   - Project management and accounting in Dynamics 365 Finance environment version 10.0.20.

## Project Operations dual-write maps updates

There are no updates for Project Operations dual-write maps in this release. For a current list and versions of Project Operations dual-write maps, see [Project Operations dual-write map versions](../environment/resource-dual-write-maps.md).

Always run the latest version of the map in your environment and enable all related table maps as you update your Project Operations Dataverse solution and Finance solution version. Certain features and capabilities might not work correctly if the latest version of the map isn't activated. You can see the active version of the map on the **Dual-write** page in the **Version** column. To activate a new version of the map, select  **Table map versions**, select the latest version, and then save the selected version. If you have customized an out-of-the-box table map, reapply the changes. For more information, see [Application lifecycle management](/dynamics365/fin-ops-core/dev-itpro/data-entities/dual-write/app-lifecycle-management).

If you encounter an issue starting the map, follow instructions in the [Missing table columns issue on maps](/dynamics365/fin-ops-core/dev-itpro/data-entities/dual-write/dual-write-troubleshooting-finops-upgrades#missing-table-columns-issue-on-maps) section of the Dual Write troubleshooting guide.

## Quality updates

### Project Operations on Dataverse

| **Feature area** | **Reference number** | **Quality update** |
| --- | --- | --- |
| Time and expense | 1811407 | Adjusted the Project Approver security role for expense entry approvals. |
| Time and expense | 1811438 | Adjusted the Project Approver security role for time entry approval cancellation. |
| Time and expense | 2370126 | Updated the **Project Task** and **Role** icons in **Time Entry** entity. |
| Time and expense | 2379879 | Corrected the **Copy Week** function in time entry when using Dynamics 365 for phone. |
| Billing and Pricing | 2371906 | Proforma invoice total amount must not be adjustable in Project Operations for resource-based deployments. |
| Billing and Pricing | 2385802 | Fixed the error that occurs with negative actual hours when project totals are refreshed. |
| Billing and Pricing | 2389675 | Improved proforma invoice confirmation behavior. Long running jobs entity must take into account the activity required to write confirmation results for accounting. |

### Project management and accounting in Dynamics 365 Finance

| Feature area | Reference number | Quality update |
| --- | --- | --- |
| Travel and expense | [4618082](https://fix.lcs.dynamics.com/Issue/Details?kb=4618082&amp;bugId=583101&amp;dbType=3&amp;qc=9c85ac8ca1e5e9cd07fac9e9aa2cb0914724e28b86ad3339dacf7741f554c605) | The amounts on vendor and sales tax transactions that are posted from an expense that was created from a credit card transaction are incorrect. |
| Travel and expense | [4620366](https://fix.lcs.dynamics.com/Issue/Details?kb=4620366&amp;bugId=579485&amp;dbType=3&amp;qc=e864789bd95505ea624c537d585bf113c2de60b97c88439d44693dbd85aa8e92) | The wrong settlement lines are created when the payment journal is generated. |
| Travel and expense | [4618082](https://fix.lcs.dynamics.com/Issue/Details?kb=4618082&amp;bugId=583101&amp;dbType=3&amp;qc=9c85ac8ca1e5e9cd07fac9e9aa2cb0914724e28b86ad3339dacf7741f554c605) | The amounts on sales tax transactions that are posted from an expense that was created from a credit card transaction are incorrect. |
| Travel and expense | [4621765](https://fix.lcs.dynamics.com/Issue/Details?kb=4621765&amp;bugId=587306&amp;dbType=3&amp;qc=6fbfad0123d4e95eaf8d5a5a2f6c354577c991b7905c852ab02d1f94e728a876) | Deleting an expense line might take a long time. |
| Project accounting | [4623737](https://fix.lcs.dynamics.com/Issue/Details?kb=4623737&amp;bugId=598109&amp;dbType=3&amp;qc=4101fc5865201e21815299f2ff11ae46d5d5370510868df86c25ee09a8ca1a0c) | After you apply KB 4619395, changing the number sequence to **Continuous** isn't supported and when you post an estimate, the following error occurs, "System does not support setup 'continuous' of number sequence Proj_X." |
| Project accounting | [4623332](https://fix.lcs.dynamics.com/Issue/Details?kb=4623332&amp;bugId=586034&amp;dbType=3&amp;qc=2f64bb1977c4a9c9dd2ce9de7e72230b86eca14b6295c5bbfb614ea97ad81caf) | Posting a vendor invoice might fail with the following error message, "The transactions on voucher do not balance as per 5/17/2021. (accounting currency: 0.00 - reporting currency: 0.01)." |
