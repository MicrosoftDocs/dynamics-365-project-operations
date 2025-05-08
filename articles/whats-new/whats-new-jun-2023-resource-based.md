---
title: What's new June 2023 - Project Operations for resource/non-stocked based scenarios
description: This article provides information about the quality updates that are available in the June 2023 release of Microsoft Dynamics 365 Project Operations for resource/non-stocked based scenarios.
author: ramagadu
ms.custom:
  - evergreen
ms.date: 04/09/2024
ms.topic: whats-new
ms.reviewer: johnmichalak 
ms.author: ramagadu
---

# What's new June 2023 - Project Operations for resource/non-stocked based scenarios

_**Applies To:** Project Operations for resource/non-stocked based scenarios_

This article applies to the following components and versions of Microsoft Dynamics 365 Project Operations:

- Project Operations in a Microsoft Dataverse environment version 4.73.0.78
- Project management and accounting in a Microsoft Dynamics 365 Finance environment version 10.0.34

## Project Operations dual-write maps updates

There aren't any updates for Project Operations dual-write maps in this release. For a current list and versions of Project Operations dual-write maps, see [Project Operations dual-write map versions](../environment/resource-dual-write-maps.md).

Always run the latest version of the map in your environment and enable all related table maps as you update your Project Operations Dataverse solution and Finance solution version. Some features and capabilities might not work correctly if the latest version of the map isn't activated. You can view the active version of the map in the **Version** column on the **Dual-write** page. To activate a new version of the map, select **Table map versions**, select the latest version, and then save the selected version. If you've customized an out-of-box table map, reapply the changes. For more information, see [Application lifecycle management](/dynamics365/fin-ops-core/dev-itpro/data-entities/dual-write/app-lifecycle-management).

If you encounter an issue when you start the map, follow the instructions in the [Missing table columns issue on maps](/dynamics365/fin-ops-core/dev-itpro/data-entities/dual-write/dual-write-troubleshooting-finops-upgrades#missing-table-columns-issue-on-maps) section of the Dual-write troubleshooting guide.

## Features included in this release

| Feature area | Feature name | More information |
| --- | --- | --- |
|Expense Management| **Expense Mobile - Intuitive Expense Entry (Public Preview)**</br>The Expense mobile app is a powerful solution that's designed to simplify and enhance the expense reimbursement process and increase user productivity. Thanks to its focus on being intuitive and easy to use, the Expense mobile app offers a range of features that make reporting expenses seamless and efficient.| [Expense Mobile - Intuitive Expense Entry](/dynamics365/project-operations/expense/new-expense-mobile-app-overview) |
|Project Planning and Tracking| **Project management Copilot (Preview)**<br>We're delighted to share with you the preview of Copilot within Project Operations. These new features are currently available in North American tenants. Copilot is designed to enhance the productivity and performance of project managers by offering them three innovative capabilities: task plan, risk assessment and status reports. These capabilities enable project managers to create tasks automatically based on project requirements, assess and mitigate potential risks, and generate comprehensive and insightful reports on project progress and outcomes. | [Project Operations Copilot](/dynamics365/project-operations/project-management/copilot-features) |

## Quality updates

### Project Operations on Dataverse

| Feature area | Reference number | Quality update |
| --- | --- | --- |
|Billing and Pricing|2767640|Material usage logs don't respect Billing type when submitted for approval.|
|Billing and Pricing|2900480|Null reference exception when an Invoice doesn't have a linked Contract in AddInvoiceLinesWithDetails.|
|Billing and Pricing|2943191|It should not be possible to create a Milestone record where tax isn't 0 when amount is 0.|
|Billing and Pricing|3229673|Adding a task to an Expense Estimates doubles the cost amount of the expense.|
|Billing and Pricing|3237336|Add exception message when more than one project parameter is found.|
|Billing and Pricing|3238895|Add validation to prevent Invoice Line without Contract Line.|
|Billing and Pricing|3261790|Estimate Line Update doesn't correctly aggregate when Task is changed.|
|Billing and Pricing|3345529|Project contact line creation failing due to no null check.|
|Billing and Pricing|3435058|Null reference exception while creating project team member.|
|Opportunity Management|3246566|Update Description of unused fields on Project: QuoteLineProject and ContractLineProject.|
|Project Operations Upgrade|3342333|Customers upgrade from PSA to PO are failing when the entity in the top layer has CanCreateAttributes set to 0.|
|Project Operations Upgrade|3365216|Upgrade script should not fail on exception disabling plugins.|
|Project Planning and Tracking|3191217|Extending bookings button doesn't block multiple extensions if the cursor isn't moved.|
|Project Planning and Tracking|3329498|Null reference exception - WorkHoursHelper.UpdateTargetCalendarRules() method doesn't deal with empty EntityCollection correctly.|
|Project Planning and Tracking|3341078|Missing log for the order of in-memory copied estimate lines to create in database.|
|Project Planning and Tracking|3341085|The order of in-memory copied estimate lines (to create in database) isn't sorted and causes creation failure.|
|Subcontracting|3377695|Not possible to create Bookable resources of type Employee for Accounts. Error presented: "Vendor Account field must be empty for an Employee."|
|Time and Expense|3237532|Modern Approvals can be disabled using power platform.|

### Project management and accounting in Finance

For information about the bug fixes that are included in this update, sign in to Microsoft Dynamics 365 Lifecycle Services, and view the [KB article](https://fix.lcs.dynamics.com/Issue/Details?bugId=805875).
