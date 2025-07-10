---
title: What's new October 2024 - Project Operations Integrated with ERP
description: This article provides information about the quality updates that are available in the October 2024 release of Microsoft Dynamics 365 Project Operations Integrated with ERP.
author: mohitmenon
ms.author: mohitmenon
ms.topic: whats-new
ms.custom: 
  - bap-template
  - evergreen
ms.date: 07/07/2025
ms.update-cycle: 1095-days
ms.reviewer: johnmichalak

---

# What's new October 2024 - Project Operations Integrated with ERP

[!INCLUDE[banner](../includes/banner.md)]

**Applies To:**  Project Operations Integrated with ERP.

This article applies to the following components and versions of Microsoft Dynamics 365 Project Operations:

- Project Operations in a Microsoft Dataverse environment version 4.121.0.50.
- Project management and accounting in a Microsoft Dynamics 365 Finance environment version 10.0.41.

## Project Operations dual-write maps updates

There are no modifications to Dual-write maps in the Project Operations October 2024 release.

For a current list and versions of Project Operations dual-write maps, see [Project Operations dual-write map versions](../environment/resource-dual-write-maps.md).

Always run the latest version of the map in your environment and enable all related table maps as you update your Project Operations Dataverse solution and Finance solution version. Some features and capabilities might not work correctly if the latest version of the map isn't activated. You can view the active version of the map in the **Version** column on the **Dual-write** page. To activate a new version of the map, select **Table map versions**, select the latest version, and then save the selected version. If you customized an out-of-box table map, reapply the changes. For more information, see [Application lifecycle management](/dynamics365/fin-ops-core/dev-itpro/data-entities/dual-write/app-lifecycle-management).

If you encounter an issue when you start the map, follow the instructions in the [Missing table columns issue on maps](/dynamics365/fin-ops-core/dev-itpro/data-entities/dual-write/dual-write-troubleshooting-finops-upgrades#missing-table-columns-issue-on-maps) section of the Dual-write troubleshooting guide.


## Features included in this release

| **Feature area** | **Feature name** | **More information** |
| --- | --- | --- |
| Financials |**Enable the use of Project fixed exchange rate agreements for Project Operations Integrated with ERP deployments** <br><br> This feature lets you optionally enter a fixed exchange rate on the project contract in Microsoft Dynamics 365 Finance. This exchange rate is used to converte the sales currency amounts into the legal entity's accounting currency.|[Use of fixed exchange rates](../invoicing/format-update-project-invoice-proposals.md) |
| Financials |**Enable project categories for on-account transactions** <br><br> This feature adds the ability to specify a project category for on-account transactions for Project Operations Integrated with ERP deployment type. The use of project category allows for more flexibility in recording revenue for different activities all recorded as milestones or other on-account transactions.|[Configure Project Categories](../project-accounting/configure-project-categories.md) |
| Project Budgeting |**Project budget time-phasing by Month, Quarter & Year** <br><br> This feature enhances project budget time-phasing capabilities. Previously, budget lines could only be time-phased in a weekly manner. With this release, project budget lines can time-phase by month, quarter, or year. The time-phasing method can be changed at the project level from weekly to monthly, quarterly, or yearly, but only when the budget version is in a draft or editable state to ensure data consistency.|[Set up budget period](../pro/budget/budget-period-setup.md) |

## Quality updates

### Project Operations on Dataverse

| **Feature Area** | **Reference No.** | **Quality Update** |
| --- | --- | --- |
|Sales|	3443372|	Revising the quote resets the split billing percentage on the contract lines for the listed customers.|
|Subcontracting|	3667173|	Casting of SubcontractLine entity collections to entities fails intermittently. |
|Billing and Pricing|	3733811|	Import QLD from estimates--missing price and amount fields when aggregating over multiple tasks/roles.|
|Sales|	3853801|	Quote Line Detail and Contract Line Detail Dual-write precreate validation should default Owning Company instead of throwing an error.|
|Billing and Pricing|	3958570|	Fixing issue that prevented deletion of confirmed customer invoices in certain scenarios (advanced retainer or milestone).|
|Billing and Pricing|	4093604|	Product Business Logic should prevent the creation of more than one Estimate of type "Activitybasedestimate."|
|Billing and Pricing|	4113808|	Sequence number calculated incorrectly when using xMultiple for invoicing.|
|Sales|	4149073|	Importing estimates to QLDs/CLDs doesn't correctly set billing type for task-based billing.|
|Billing and Pricing|	4158165|	Making Update Prices a long running job to improve user experience.|
|Subcontracting|	4205520|	[PODW] Actuals aren't generated when Manually Confirming a Vendor Invoice with AutoConfirm = True.|
|Sales|	4212767|	Eliminating memory delays that occur post update or confirmation of Project Contract.|
|Time Entry|	4249478|	Project Operations license doesn't grant access to Team Member App.|
|Billing and Pricing|	4259028|	Provide a fallback when user settings are unavailable in ProjectOperationsDualWrite (relevant to SYSTEM users).|
|Sales|	4318898|	Able to deactivate primary customer on quote.|
|Billing and Pricing|	4319341|	Limit the application of retainers against chargeable transactions only (and not nonchargeable transactions).|
|Billing and Pricing|	4324688|	Correct misaligned privileges for msdyn_actual and msdyn_transactionconnection entities within ProjOps OOB default user roles.|
|Billing and Pricing|	4326097|	Not able to create estimates with the future dates when Modern Estimates Feature is enabled.|
|Subcontracting|	4326960|	Null Reference Exception (NRE) thrown when confirming a vendor invoice.|
|Billing and Pricing|	4344145|	Transaction date (Time zone Independent) field on Invoice Detail is changed when user who creates Invoice is different time zone than user that created order.|
|Project Budgeting|	4374938|	Not able to Create Budget Period where Project doesn't have end date.|
|Project Budgeting|	4375822|	Time phasing Budget lines not working.|
|Billing and Pricing|	4377398|	During Project copy, estimates aren't getting copied completely in Lite org.|
|Project Planning|	4384132|	Online: Not possible to change a plan calendar template in the purple experience.|
|Sales|	4394136|	Project Contract is Missing' Error Thrown When Closing Quote as Won.|
|Resource Management|	4413953|	"An unexpected error occurred" or "Object reference not set to an instance of an object." when trying to book a project resource from the schedule board without using team member generated requirement.|

### Project management and accounting in Finance

For information about the bug fixes that are included in this update, sign in to Microsoft Dynamics 365 Lifecycle Services, and view the [KB article](https://fix.lcs.dynamics.com/Issue/Details?kb=0&bugId=952752&dbType=3&qc=3b907b83fa0fe10ada99211e89737ca71d07b749a67c0a42302cca6fa39b1a5a).

[!INCLUDE[footer-include](../includes/footer-banner.md)]
