---
title: What's new September 2024 - Project Operations Integrated with ERP
description: This article provides information about the quality updates that are available in the Sep 2024 release of Microsoft Dynamics 365 Project Operations Integrated with ERP.
author: mohitmenon
ms.topic: whats-new
ms.custom: 
  - bap-template
  - ms.custom:
  - evergreen
ms.date: 07/07/2025
ms.reviewer: johnmichalak
ms.author: mohitmenon
---

# What's new September 2024 - Project Operations Integrated with ERP

[!INCLUDE[banner](../includes/banner.md)]

**Applies To:**  Project Operations Integrated with ERP.

This article applies to the following components and versions of Microsoft Dynamics 365 Project Operations:

- Project Operations in a Microsoft Dataverse environment version 4.120.0.19.
- Project management and accounting in a Microsoft Dynamics 365 Finance environment version 10.0.40.

## Project Operations dual-write maps updates

There are no modifications to Dual-write maps in the Project Operations September 2024 release.

For a current list and versions of Project Operations dual-write maps, see [Project Operations dual-write map versions](../environment/resource-dual-write-maps.md).

Always run the latest version of the map in your environment and enable all related table maps as you update your Project Operations Dataverse solution and Finance solution version. Some features and capabilities might not work correctly if the latest version of the map isn't activated. You can view the active version of the map in the **Version** column on the **Dual-write** page. To activate a new version of the map, select **Table map versions**, select the latest version, and then save the selected version. If you customized an out-of-box table map, reapply the changes. For more information, see [Application lifecycle management](/dynamics365/fin-ops-core/dev-itpro/data-entities/dual-write/app-lifecycle-management).

If you encounter an issue when you start the map, follow the instructions in the [Missing table columns issue on maps](/dynamics365/fin-ops-core/dev-itpro/data-entities/dual-write/dual-write-troubleshooting-finops-upgrades#missing-table-columns-issue-on-maps) section of the Dual-write troubleshooting guide.


## Features included in this release

| **Feature area** | **Feature name** | **More information** |
| --- | --- | --- |
| Billing & Pricing |**Role price override within Quote Line Detail form** <br><br> The Price Override button is integrated into the Quote Line form and facilitates the modification of price overrides for quote line details. This functionality significantly reduces the number of clicks and streamlines the process of adjusting prices while maintaining focus within the context of each specific quote line detail.| [New Quote Form Experience](../sales/quotes-new-form.md)|
| Time Entry |**Copilot in time entry (Generally Available)** <br><br> Copilot in time entry, which was originally released in USA only, is now enabled by default in all regions from this release onwards. Use Copilot to create time entries from assignments and generate external comments.|[Copilot in time entry](../time/copilot-in-time-entry.md) |

## Quality updates

### Project Operations on Dataverse

| **Feature Area** | **Reference No.** | **Quality Update** |
| --- | --- | --- |
|Billing & Pricing|	4377398|	During Project copy, estimates aren't getting copied completely in Lite org.|
|Resource Management|	4343128|	Fix Invalid XML and Null Reference errors when booking from the Schedule Board.|
|Project Planning & Tracking|	4337938|	PSA Upgrade: Dynamics365ProjectOperationsDualWrite and Dynamics365ProjectOperationsDualWriteEntityMaps shouldn't be imported during upgrade from PSA to PO.|
|Project Estimates|	4326097|	Not able to create estimates with the future dates when Modern Estimates Feature is enabled.|
|Resource Management|	4323126|	Update to use right version of UnifiedResourceScheduling in PSCore.|
|Billing & Pricing|	4320628|	Can't open Add to Invoice dialog.|
|Project Estimates|	4318730|	Legacy estimates grid doesn't load.|
|Sales|	4316856|	Should allow relinking project/task to contract line and block other changes to contract line during reevaluation.|
|Approvals|	4314519|	Unable to delete an ILD on a draft invoice.|
|Subcontracting|	4305864|	On creation of subcontracting line resource, restriction on msdyn_name char count>100 throwing error.|
|Sales|	4294310|	Price override through QLD shows incorrect currency in quick create form.|
|Approvals|	4260445|	Editing Project approval billing type alters journal line transaction date.|
|Billing & Pricing|	4259028|	Fallback when User Settings are unavailable in ProjectOperationsDualWrite.|
|Billing & Pricing|	4232463|	Product-based lines are included on invoices for ALL customers in multiple customer scenario and resulting in multiple billings of the same product, etc.|
|Sales|	4221302|	Allow Multiple Executions for Contract Confirmation.|
|Time Entry|	4220455|	Time Entries split incorrectly when the days overlap while importing Resource bookings.|
|Approvals|	4132742|	Project Approver Admin Role doesn't work when assigned through a team role.|
|Project Estimates|	4097344|	SQL timeout displaying in Estimates Tab.|
|Project Planning & Tracking|	4086054|	Prevent Update to Project Locked Fields if Project has Tasks from backend.|
|Project Planning & Tracking|	3859423|	Copy Project: Telemetry and error improvements to make troubleshooting easier customers.|
|Deployment & Configuration|	3842801|	Improve error messaging for post import during Upgrades or Installations.|
|Project Planning & Tracking|	3831591|	Recalled time entry doesn't update in WBS with on-demand update.|
|Approvals|	3801469|	Project approval billing type is only set with linked contract line.|
|Project Estimates|	3770326|	Estimated Expense Cost (msdyn_plannedexpensecost) goes negative when changing task duration.|
|Project Planning & Tracking|	3736776|	Updating project start shouldn't open project session if there isn't an open session.|
|Sales|	3679212|	Contract line details can be added or updated on a confirmed contract.|
|Approvals|	3521008|	Correction Journals ignore new expense category on integrated orgs.|
|Project Planning & Tracking|	3506993|	Schedule Variance not being recalculated after task Effort is adjusted using Task Grid.|
|Subcontracting|	3491867|	Subcontract Line Resource creation leads to script error.|
|Subcontracting|	3338245|	Posting vendor invoice fails when lines include Procurement category with category type Item. |

### Project management and accounting in Finance

For information about the bug fixes that are included in this update, sign in to Microsoft Dynamics 365 Lifecycle Services, and view the [KB article](https://fix.lcs.dynamics.com/Issue/Details?kb=0&bugId=952752&dbType=3&qc=3b907b83fa0fe10ada99211e89737ca71d07b749a67c0a42302cca6fa39b1a5a).

[!INCLUDE[footer-include](../includes/footer-banner.md)]


