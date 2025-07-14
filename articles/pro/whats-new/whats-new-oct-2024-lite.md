---
title: What's new October 2024 - Project Operations Core deployment
description: This article provides information about quality updates that are available in the October 2024 release of Microsoft Dynamics 365 Project Operations Core deployment.
author: mohitmenon
ms.author: mohitmenon
ms.topic: whats-new
ms.custom:
  - evergreen
  - bap-template
ms.date: 11/06/2024
ms.reviewer: johnmichalak
---

# What's new October 2024 - Project Operations Core deployment

[!INCLUDE[banner](../../includes/banner.md)]

_**Applies To:** Project Operations Core_

This article applies to the following components and versions of Microsoft Dynamics 365 Project Operations:

- Project Operations in a Microsoft Dataverse environment version 4.121.0.50.

## Features included in this release

| **Feature area** | **Feature name** | **More information** |
| --- | --- | --- |
| Project Budgeting |**Project budget time-phasing by Month, Quarter & Year** <br><br> This feature enhances project budget time-phasing capabilities. Previously, budget lines could only be time-phased in a weekly manner. With this release, project budget lines can time-phase by month, quarter, or year. The time-phasing method can be changed at the project level from weekly to monthly, quarterly, or yearly, but only when the budget version is in a draft or editable state to ensure data consistency.|[Set up budget period](../budget/budget-period-setup.md) |

## Quality updates

### Project Operations on Dataverse

| **Feature Area** | **Reference No.** | **Quality Update** |
| --- | --- | --- |
|Sales|	3443372|	Revising the quote resets the split billing percentage on the contract lines for the listed customers.|
|Subcontracting|	3667173|	Casting of SubcontractLine entity collections to entities fails intermittently. |
|Billing and Pricing|	3733811|	Import QLD from estimates: missing price and amount fields when aggregating over multiple tasks/roles.|
|Billing and Pricing|	3958570|	Fixing issue that prevented deletion of confirmed customer invoices in certain scenarios (advanced retainer or milestone).|
|Billing and Pricing|	4093604|	Product Business Logic should prevent the creation of more than one Estimate of type "Activitybasedestimate."|
|Billing and Pricing|	4113808|	Sequence number calculated incorrectly when using xMultiple for invoicing.|
|Sales|	4149073|	Importing estimates to QLDs/CLDs doesn't correctly set billing type for task-based billing.|
|Billing and Pricing|	4158165|	Making Update Prices a long running job to improve user experience.|
|Sales|	4212767|	Eliminating memory delays that occur post update or confirmation of Project Contract.|
|Time Entry|	4249478|	Project Operations license doesn't grant access to Team Member App.|
|Sales|	4318898|	Able to deactivate primary customer on quote.|
|Billing and Pricing|	4319341|	Limit the application of retainers against chargeable transactions only (and not nonchargeable transactions).|
|Billing and Pricing|	4324688|	Correct misaligned privileges for msdyn_actual and msdyn_transactionconnection entities within ProjOps OOB default user roles.|
|Billing and Pricing|	4326097|	Not able to create estimates with the future dates when Modern Estimates Feature is enabled.|
|Subcontracting|	4326960|	Null Reference Exception (NRE) thrown when confirming a vendor invoice.|
|Billing and Pricing|	4344145|	Transaction date (Time zone Independent) field on Invoice Detail is changed when user who creates Invoice is different time zone than user that created order.|
|Project Budgeting|	4374938|	Not able to Create Budget Period where Project Doesn't have end date.|
|Project Budgeting|	4375822|	Time phasing Budget lines not working.|
|Billing and Pricing|	4377398|	During Project copy, estimates aren't getting copied completely in Lite org.|
|Project Planning|	4384132|	Online: Not possible to change a plan calendar template in the purple experience.|
|Sales|	4394136|	Project Contract is Missing' Error Thrown When Closing Quote as Won.|
|Resource Management|	4413953|	"An unexpected error occurred" or "Object reference not set to an instance of an object." when trying to book a project resource from the schedule board without using team member generated requirement.|


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
