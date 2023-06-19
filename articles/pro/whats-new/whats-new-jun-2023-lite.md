---
title: What's new June 2023 - Project Operations lite deployment
description: This article provides information about the quality updates that are available in the June 2023 release of Microsoft Dynamics 365 Project Operations lite deployment.
author: ramagadu
ms.date: 05/15/2023
ms.topic: article
ms.prod:
ms.reviewer: johnmichalak 
ms.author: ramagadu
---

# What's new June 2023 - Project Operations lite deployment

_**Applies To:** Lite deployment - deal to proforma invoicing_

This article applies to the following components and versions of Microsoft Dynamics 365 Project Operations:

- Project Operations in a Microsoft Dataverse environment version *********

## Features included in this release

| Feature area | Feature name | More information |
| --- | --- | --- |
|Project Planning and Tracking| **Project Operations Copilot (Preview)**<br>We are delighted to share with you the preview of Co-pilot within Dynamics 365 Project Operations. These new features are currently available in North American tenants. Co-pilot is designed to enhance the productivity and performance of project managers by offering them three innovative capabilities: task plan, risk assessment and status reports. These capabilities enable project managers to create tasks automatically based on project requirements, assess and mitigate potential risks, and generate comprehensive and insightful reports on project progress and outcomes. | [Project Operations Copilot](/dynamics365/project-operations/project-management/copilot-features) |

## Quality updates

| Feature area | Reference number | Quality update |
| --- | --- | --- |
|Billing and Pricing|2767640|Material usage logs do not respect Billing type when submitted for approval|
|Billing and Pricing|2900480|Null reference exception when Invoice has no linked Contract in AddInvoiceLinesWithDetails|
|Billing and Pricing|2943191|It should not be possible to create a Milestone record where tax is not 0 when amount is 0|
|Billing and Pricing|3229673|Adding a task to an Expense Estimates doubles the cost amount of the expense|
|Billing and Pricing|3237336|Add exception message when more than one project parameter is found|
|Billing and Pricing|3238895|Add validation to prevent Invoice Line without Contract Line|
|Billing and Pricing|3261790|Estimate Line Update does not correctly aggregate when Task is changed|
|Billing and Pricing|3345529|Project contact line creation failing due to no null check|
|Billing and Pricing|3435058|Null reference exception while creating project team member|
|Opportunity Management|3246566|Update Description of unused fields on Project: QuoteLineProject and ContractLineProject|
|Project Operations Upgrade|3342333|Customers upgrade from PSA to PO are failing when the entity in the top layer has CanCreateAttributes set to 0|
|Project Operations Upgrade|3365216|Upgrade script should not fail on exception disabling plugins.|
|Project Planning and Tracking|3191217|Extending bookings button does not block multiple extensions if the cursor is not moved|
|Project Planning and Tracking|3329498|Null reference exception - WorkHoursHelper.UpdateTargetCalendarRules() method does not deal with empty EntityCollection correctly|
|Project Planning and Tracking|3341078|Missing log for the order of in-memory copied estimate lines to create in database|
|Project Planning and Tracking|3341085|The order of in-memory copied estimate lines (to create in database) is not sorted and causes creation failure|
|Subcontracting|3377695|Not possible to create Bookable resources of type Employee for Accounts. Error presented: "Vendor Account field must be empty for an Employee."|
|Time and Expense|3237532|Modern Approvals can be disabled using power platform|