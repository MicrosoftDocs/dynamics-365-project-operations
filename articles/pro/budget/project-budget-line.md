---
title: Project budget line – Time, Material, Expense
description: This article provides the details for how to create and delete a project cost budget line.
author: niranjanmaski
ms.date: 01/13/2023
ms.topic: article
ms.reviewer: johnmichalak
ms.author: nimaski
---

# Project budget line – Time, Material, Expense

**_Applies To:_** _ Project Operations for resource/non-stocked based scenarios, Lite deployment - deal to proforma invoicing_

Project budget will have budget lines which are the snapshot of the budgeted quantity and amount against dimensions which needs to be tracked.

Project budget lines can be created under three Transaction classes

- Time budget line would track the recorded and approved time of bookable resources against the project
- Material budget line would track the consumed materials which are approved against the project
- Expense budget line would track the approved expenses against the project.

Note: Budget dimensions should be unique across all budget lines. You cannot create two budget lines with same dimensions.

### Time budget line:

Pre-requisite: Project budget is created for project as per 'Create, Delete, Revision of Project budget'

Follow the below steps for creating a project budget line for transaction class 'Time'.

1. Sign-in to Project Operations.
2. Change area to **'Projects'** in left nav
3. Click the project you wish to create the Time budget line.
4. Since project budget is created, you should see a tab **'Budget'**
5. Click **'+New Project Budget Line'** to create budget line.
6. A Quick create form would launch with default Transaction class selected as 'Time'
7. Once all fields are updated as per the below table, select 'Save & Create New' to create another budget line or select 'Save & Close' to save the details and close the quick create form.
8. Budget line fields can be edited on the grid under **'Budget'** tab, it would be saved when you tab out to next line in the grid. This is possible only till budget is submitted for approval.


| **Field** | **Requirement** | **Comments** |
| --- | --- | --- |
| **Transaction Class** | Mandatory | Default option is 'Time', leave it with Time. |
| Description | Optional |- Use this field to describe about the budget line. For eg: 'Time for Task1' or 'Time for Foundation' |
| Start Date | Mandatory |- Defines the start date of budget line.- Would define from when the actuals of the projects would be tracked against the budget line.- Defaulted to start date of the project.
- This date must be between start and end date of the project.|
| End Date | Mandatory |- Defines the end date of budget line.- Would define till when the actuals of the projects would be tracked against the budget line.- Defaulted to end date of the project.- This date must be between start and end date of the project. |
| Task | Optional |- Fill this if you wish to track budget against a specific task of the project.- From the drop down for Task, pick the task within list of tasks of the project.
- If you wish to track budget against all tasks of the project, you can leave the task as blank.
 |
| Role | Optional |
- Fill this if you wish to track budget against a specific role.
- From the drop down for Role, pick the role within defined list of roles of the organization.
- If you wish to track budget against all roles, you can leave the role as blank.
 |
| Resource | Optional |
- Fill this if you wish to track budget against a specific bookable resource
- From the drop down for Resource, pick the bookable resource, from the list of bookable resource as per selected task or role.
- You can pick any other specific resource not assigned to any role or a task by clicking on search within the drop down, provided there was no role or task selected.
- If you wish to track budget against all bookable resources, you can leave the resource field as blank.
 |
| Resourcing Unit | Optional |
- Fill this if you wish to track the budget against a particular resourcing unit.
- If Resource is picked, the resourcing unit must align to the resourcing unit of the picked resource.
- If Resource is not picked, pick a resourcing unit if you wish to track budget against a specific resourcing unit. Leave it blank if you wish to track the budget against all resourcing units.
- Default value - Blank

 |
| Cost Source | Optional |
- Allowed choices – Blank, Internal, External
- If you wish to track the costs irrespective of the cost source leave this field as blank.
- Fill this as Internal, to track the costs with cost source as internal
- Fill this as External, to track the costs from subcontractors
- Default value - Blank
 |
| Vendor Name | Optional |
- Applicable only when Cost Source is External
- Pick the vendor if you wish to track the costs from a specific vendor or subcontractor.
- Leave this field as blank if wish to track the costs from any vendor or subcontractor.
- Default value – Blank

 |
| Quantity | Optional |
- Fill the quantity you wanted to budget for the selected dimensions for Time, Material, Expense.
- Actual quantity gets tracked against the budgeted quantity, only if a budget line had quantity.
- Only amount gets tracked against the dimensions of the budget line if quantity is left blank.
- Default value – Blank
 |
| Unit Group | Optional |
- Unit group gets locked with 'Time' for budget line with transaction class as time.

 |
| Unit | Optional |
- Pick the Unit from the units belonging to 'Time' Unit group
- Unit would display only the units from the selected Unit group.
 |
| Unit Price | Optional |
- Unit price is the price of the one-unit quantity of time or material, or expense selected
- If you wish to get the price list unit price based on the selected dimensions, click 'Save & Close' which would calculate the unit price if available in the system based on the selected dimensions.
- You can override and update the defaulted unit price to a new value if you wish to track against a certain unit price.
 |
| Currency | Mandatory |
- If you wish to get the price list currency based on the selected dimensions, click 'Save & Close' which would get the currency from price list.
- You can update currency to any other currency you wanted to budget for. This means the currency conversion would apply while tracking if actual currency is different from budgeted currency for the selected dimensions.
- Defaulted to Organization Currency.
 |
| Amount | Mandatory |
- Calculated as Quantity \* Unit price if quantity is filled.
- If quantity is not filled, fill this field with the amount you wanted to budget against the selected dimensions of the budget line.
- Amount must be a positive non-zero number.
 |
| Contingency % | Optional |
- Fill the contingency % you wish to add to the budgeted amount.
- Budget for the selected dimensions would be equal to
Amount + (Contingency % \* Amount). |
| Budget | Mandatory |
- Auto-filled based on the dimensions.
- This holds the budget for the budget line for the selected dimensions.
- Budget = Amount + (Contingency % \* Amount)
 |
