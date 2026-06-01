---
title: What's new September 2024 - Project Operations Core
description: This article provides information about quality updates that are available in the Sept 2024 release of Microsoft Dynamics 365 Project Operations Core.
author: mohitmenon
ms.custom:
  - evergreen
ms.date: 02/26/2026
ms.update-cycle: 1095-days
ms.topic: whats-new
ms.reviewer: johnmichalak
ms.author: mohitmenon
---

# What's new September 2024 - Project Operations Core

[!INCLUDE[banner](../../includes/banner.md)]

_**Applies To:** Project Operations Core_

This article applies to the following components and versions of Microsoft Dynamics 365 Project Operations:

- Project Operations in a Microsoft Dataverse environment version 4.120.0.164.

## Features included in this release

| **Feature area** | **Feature name** | **More information** |
| --- | --- | --- |
| Billing & Pricing |**Discounts and Fee** <br><br> Define discount and fee percentages at the project quote or contract line level. When a transaction is generated and approved, the system applies the appropriate discount or fee based on the contract line setup and updates the actuals accordingly. This feature is applicable to Time and Material business processes.| [Manage Discounts and Fee](../../pricing-costing/manage-discount-fee-calculations.md)|
| Billing & Pricing |**Role price override within Quote Line Detail form** <br><br> The Price Override button is integrated into the Quote Line form and facilitates the modification of price overrides for quote line details. This functionality significantly reduces the number of clicks and streamlines the process of adjusting prices while maintaining focus within the context of each specific quote line detail.| [New Quote Form Experience](../../sales/quotes-new-form.md)|
| Billing & Pricing |**Journal line improvements** <br><br> This feature prevents creation of incorrect journal line entries by enforcing business rules. It introduces new validations and fills in dependent values automatically, based on the transaction class and transaction type. This feature aims to enhance the **Quick create** form for journal lines by adding validations and defaulting logic for fields, and improves the display of fields.| [Journal line improvements](../../actuals/journal-line-improvements.md)|
| Time Entry |**Copilot in time entry (Generally Available)** <br><br> Copilot in time entry, which was originally released in USA only, is now enabled by default in all regions from this release onwards. Use Copilot to create time entries from assignments and generate external comments.|[Copilot in time entry](../../time/copilot-in-time-entry.md) |


## Quality updates

### Project Operations on Dataverse

| **Feature Area** | **Reference No.** | **Quality Update** |
| --- | --- | --- |
|Billing & Pricing|	4377398|	During project copy, estimates aren't getting copied completely in Project Operations Core org.|
|Resource Management|	4343128|	Fix invalid XML and null reference errors when booking from the Schedule Board.|
|Project Planning & Tracking|	4337938|	PSA Upgrade: Dynamics365ProjectOperationsDualWrite and Dynamics365ProjectOperationsDualWriteEntityMaps shouldn't be imported during upgrade from PSA to PO.|
|Project Estimates|	4326097|	Unable to create estimates with the future dates when the **Modern Estimates** feature is enabled.|
|Resource Management|	4323126|	Update to use correct version of UnifiedResourceScheduling in PSCore.|
|Billing & Pricing|	4320628|	Can't open the **Add to Invoice** dialog.|
|Project Estimates|	4318730|	Legacy estimates grid doesn't load.|
|Sales|	4316856|	Should allow relinking project/task to contract line and block other changes to contract line during reevaluation.|
|Approvals|	4314519|	Unable to delete an ILD on a draft invoice.|
|Subcontracting|	4305864|	On creation of subcontracting line resource, restriction on msdyn_name char count>100 throwing error.|
|Sales|	4294310|	Price override through QLD shows incorrect currency in quick create form.|
|Approvals|	4260445|	Editing project approval billing type alters journal line transaction date.|
|Billing & Pricing|	4259028|	Fallback when user settings are unavailable in ProjectOperationsDualWrite.|
|Billing & Pricing|	4232463|	Product-based lines are included on invoices for all customers in multiple customer scenarios, resulting in multiple billings of the same product.|
|Sales|	4221302|	Allow multiple executions for contract confirmation.|
|Time Entry|	4220455|	Time entries split incorrectly when the days overlap while importing resource bookings.|
|Approvals|	4132742|	Project approver administrator role doesn't work when assigned through a team role.|
|Project Estimates|	4097344|	SQL timeout displaying on **Estimates** tab.|
|Project Planning & Tracking|	4086054|	Prevent update to a project's locked fields if the project has tasks from the backend.|
|Project Planning & Tracking|	3859423|	Copy project: Telemetry and error improvements to make troubleshooting easier customers.|
|Deployment & Configuration|	3842801|	Improve error messaging for post import during upgrades or installations.|
|Project Planning & Tracking|	3831591|	Recalled time entry doesn't update in WBS with on-demand update.|
|Approvals|	3801469|	Project approval billing type is only set with linked contract line.|
|Project Estimates|	3770326|	Estimated expense cost (msdyn_plannedexpensecost) goes negative when changing task duration.|
|Project Planning & Tracking|	3736776|	Updating project start shouldn't open project session if there isn't an open session.|
|Sales|	3679212|	Contract line details can be added or updated on a confirmed contract.|
|Approvals|	3521008|	Correction journals ignore new expense category on integrated orgs.|
|Project Planning & Tracking|	3506993|	Schedule variance not being recalculated after task effort is adjusted using the task grid.|
|Subcontracting|	3491867|	Subcontract line resource creation leads to script error.|
|Subcontracting|	3338245|	Posting vendor invoice fails when lines include the **Procurement** category with category type **Item**. |

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
