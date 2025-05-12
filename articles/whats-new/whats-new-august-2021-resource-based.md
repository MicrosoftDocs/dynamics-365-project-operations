---
title: What's new August 2021 - Project Operations for resource/non-stocked based scenarios
description: This article provides information about the quality updates available in the August 2021 release of Project Operations for resource/non-stocked based scenarios.
author: sigitac
ms.custom:
  - evergreen
ms.date: 04/09/2024
ms.topic: whats-new
ms.reviewer: johnmichalak
ms.author: sigitac
---

# What's new August 2021 - Project Operations for resource/non-stocked based scenarios

*Applies To: Project Operations for resource/non-stocked based scenarios*

This article applies to the following Dynamics 365 Project Operations components and versions:

   - Project Operations in Microsoft Dataverse environment version 4.13.0.152.
   - Project management and accounting in Dynamics 365 Finance environment version 10.0.20.

## Features included in this release

The following features are included in this release:

- **Approval sets**: Approval sets group time, expense, or material usage approval requests together into smaller subsets of operations. This grouping allows approvals to be processed in a specific order by project and allows for retrying and sequencing. Grouping the requests improves the reliability and traceability of approval processing for large volumes of approvals. For more information, see [Approval sets](../approvals/approval-sets.md).

## Project Operations dual-write maps updates

There are no updates for Project Operations dual-write maps in this release.

For a current list and versions of Project Operations dual-write maps, see [Project Operations dual-write map versions](../environment/resource-dual-write-maps.md).

Always run the latest version of the map in your environment and enable all related table maps as you update your Project Operations Dataverse solution and Finance solution version. Certain features and capabilities might not work correctly if the latest version of the map isn't activated. You can see the active version of the map on the **Dual-write** page in the **Version** column. Activate a new version of the map by selecting **Table map versions**, selecting the latest version, and then saving the selected version. If you have customized an out-of-the-box table map, reapply the changes. For more information, see [Application lifecycle management](/dynamics365/fin-ops-core/dev-itpro/data-entities/dual-write/app-lifecycle-management).

If you encounter an issue starting the map, follow the instructions in the [Missing table columns issue on maps](/dynamics365/fin-ops-core/dev-itpro/data-entities/dual-write/dual-write-troubleshooting-finops-upgrades#missing-table-columns-issue-on-maps) section in the Dual-write troubleshooting guide.

## Quality updates

### Project Operations on Dataverse

| **Feature area** | **Reference number** | **Quality update** |
| --- | --- | --- |
| Billing and pricing | 2295625 | The milestone name must be copied from the invoice schedule to the invoice line detail. |
| Billing and pricing | 2316323 | The discount shouldn't be editable on a proforma invoice in Project Operations for resource-based scenarios. |
| Opportunity management | 2338619 | **Opportunity** and **Quote** business rules must be invoked only on pages. |
| Resource management | 2316523 | Using **Send Request** from a resource requirement that has a role attached should not display an error. |
| Resource management | 2326885 | Creating a resource requirement through a project should not display an error. |
| Time and expense | 2335584 | Deprecated task flows in the time entry. |
| Time and expense | 2336884 | The **Copy Week** time entry button must work for more than just the current user. |


### Project management and accounting on Dynamics 365 Finance

| Feature area | Reference number | Quality update |
| --- | --- | --- |
| Travel and expense | [4618082](https://fix.lcs.dynamics.com/Issue/Details?kb=4618082&amp;bugId=583101&amp;dbType=3&amp;qc=9c85ac8ca1e5e9cd07fac9e9aa2cb0914724e28b86ad3339dacf7741f554c605) | Incorrect vendor transaction and sales tax transaction amounts are posted when an expense is created from a credit card transaction. |
| Travel and expense | [4620366](https://fix.lcs.dynamics.com/Issue/Details?kb=4620366&amp;bugId=579485&amp;dbType=3&amp;qc=e864789bd95505ea624c537d585bf113c2de60b97c88439d44693dbd85aa8e92) | The wrong settlement are lines created when the payment journal is generated. |
| Travel and expense | [4618082](https://fix.lcs.dynamics.com/Issue/Details?kb=4618082&amp;bugId=583101&amp;dbType=3&amp;qc=9c85ac8ca1e5e9cd07fac9e9aa2cb0914724e28b86ad3339dacf7741f554c605) | Incorrect sales tax transaction amounts are posted when an expense is created from a credit card transaction. |
| Travel and expense | [4621765](https://fix.lcs.dynamics.com/Issue/Details?kb=4621765&amp;bugId=587306&amp;dbType=3&amp;qc=6fbfad0123d4e95eaf8d5a5a2f6c354577c991b7905c852ab02d1f94e728a876) | Deleting an expense line might take a long time. |
| Project accounting | [4623737](https://fix.lcs.dynamics.com/Issue/Details?kb=4623737&amp;bugId=598109&amp;dbType=3&amp;qc=4101fc5865201e21815299f2ff11ae46d5d5370510868df86c25ee09a8ca1a0c) | The system doesn't support the setup of continuous number sequencing when you post an estimate after applying KB 4619395. |
| Project accounting | [4623332](https://fix.lcs.dynamics.com/Issue/Details?kb=4623332&amp;bugId=586034&amp;dbType=3&amp;qc=2f64bb1977c4a9c9dd2ce9de7e72230b86eca14b6295c5bbfb614ea97ad81caf) | Vendor invoice posting might fail with the error message, "The transactions on voucher do not balance as per 5/17/2021. (accounting currency: 0.00 - reporting currency: 0.01)" |
