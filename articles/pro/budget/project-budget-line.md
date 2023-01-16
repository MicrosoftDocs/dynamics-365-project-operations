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
| Transaction Class | Mandatory | Default option is 'Time', leave it with Time. |
| Description | Optional | Use this field to describe about the budget line. </br> For eg: 'Time for design task' or 'Time for foundation activity' |
| Start Date | Mandatory | Defines the start date of budget line.</br> Would define from when the actuals of the projects would be tracked against the budget line. </br> Defaulted to start date of the project. </br>This date must be between start and end date of the project.|
| End Date | Mandatory | Defines the end date of budget line. </br>Would define till when the actuals of the projects would be tracked against the budget line. </br> Defaulted to end date of the project. </br>This date must be between start and end date of the project. |
| Task | Optional | Fill this if you wish to track budget against a specific task of the project. </br>From the drop down for Task, pick the task within list of tasksof the project. </br>If you wish to track budget against all tasks of the project, you can leave the task as blank. | 
| Role | Optional | Fill this if you wish to track budget against a specific role. </br>From the drop down for Role, pick the role within defined list of roles of the organization. </br>If you wish to track budget against all roles, you can leave the role as blank. |
| Resource | Optional | Fill this if you wish to track budget against a specific bookable resource. </br>From the drop down for Resource, pick the bookable resource, from the list of bookable resource as per selected task or role. </br>You can pick any other specific resource not assigned to any role or a task by clicking on search within the drop down, provided there was no role or task selected. </br>If you wish to track budget against all bookable resources, you can leave the resource field as blank. |
| Resourcing Unit | Optional | Fill this if you wish to track the budget against a particular resourcing unit. </br>If Resource is picked, the resourcing unit must align to the resourcing unit of the picked resource. </br>If Resource is not picked, pick a resourcing unit if you wish to track budget against a specific resourcing unit. </br> Leave it blank if you wish to track the budget against all resourcing units. </br> Default value - Blank|
| Cost Source | Optional | Allowed choices - Blank, Internal, External. </br> If you wish to track the costs irrespective of the cost source leave this field as blank. </br> Fill this as Internal, to track the costs with cost source as internal. </br> Fill this as External, to track the costs from subcontractors. </br> Default value - Blank. |
| Vendor Name | Optional | Applicable only when Cost Source is External. </br> Pick the vendor if you wish to track the costs from a specific vendor or subcontractor. </br> Leave this field as blank if wish to track the costs from any vendor or subcontractor. </br> Default value – Blank | 
| Quantity | Optional | Fill the quantity you wanted to budget for the selected dimensions for Time, Material, Expense. </br> Actual quantity gets tracked against the budgeted quantity, only if a budget line had quantity. </br> Only amount gets tracked against the dimensions of the budget line if quantity is left blank. </br> Default value – Blank. |
| Unit Group | Optional | Unit group gets locked with 'Time' for budget line with transaction class as time. |
| Unit | Optional | Pick the Unit from the units belonging to 'Time' Unit group. </br> Unit would display only the units from the selected Unit group. |
| Unit Price | Optional | Unit price is the price of the one-unit quantity of time or material, or expense selected. </br> If you wish to get the price list unit price based on the selected dimensions, click 'Save & Close' which would calculate the unit price if available in the system based on the selected dimensions. </br> You can override and update the defaulted unit price to a new value if you wish to track against a certain unit price. |
| Currency | Mandatory | If you wish to get the price list currency based on the selected dimensions, click 'Save & Close' which would get the currency from price list. </br> You can update currency to any other currency you wanted to budget for. This means the currency conversion would apply while tracking if actual currency is different from budgeted currency for the selected dimensions. </br> Defaulted to Organization Currency. |
| Amount | Mandatory | Calculated as Quantity \* Unit price if quantity is filled. </br> If quantity is not filled, fill this field with the amount you wanted to budget against the selected dimensions of the budget line. </br> Amount must be a positive non-zero number. |
| Contingency | Optional | Fill the contingency amount you wish to add to the budgeted amount. </br> Budget for the selected dimensions would be equal to Amount + Contingency. |
| Budget | Mandatory | Auto-filled based on the dimensions. </br> This holds the budget for the budget line for the selected dimensions. </br> Budget = Amount + Contingency. |


### Material budget line:

Pre-requisite: Project budget is created for project as per 'Create, Delete, Revision of Project budget'

Follow the below steps for creating a project budget line for transaction class 'Material'.

1. Sign-in to Project Operations.
2. Change area to **'Projects'** in left nav
3. Click the project you wish to create the material budget line.
4. Since project budget is created, you should see a tab **'Budget'**
5. Click **'+New Project Budget Line'** to create budget line.
6. A Quick create form would launch with default Transaction class selected as 'Time'
7. Change the Transaction class to **'Material'** from the drop down.
8. Once all fields are updated as per the below table, select 'Save & Create New' to create another budget line or select 'Save & Close' to save the details and close the quick create form.
9. Budget line fields can be edited on the grid under **'Budget'** tab, it would be saved when you tab out to next line in the grid. This is possible only till budget is submitted for approval.

| **Field** | **Requirement** | **Comments** |
| --- | --- | --- |
| **Transaction Class** | Mandatory | </br> From the drop down, change the transaction class to 'Material' |
| Description | Optional | Use this field to describe about the budget line. </br> For eg: 'Budget for laptops' or 'Budget for bricks'. |
| Start Date | Mandatory | Defines the start date of budget line. </br> Would define from when the actuals of the projects would be tracked against the budget line. </br> Defaulted to start date of the project. </br> This date must be between start and end date of the project. |
| End Date | Mandatory | Defines the end date of budget line. </br> Would define till when the actuals of the projects would be tracked against the budget line. </br> Defaulted to end date of the project. </br> This date must be between start and end date of the project. |
| Task | Optional | Fill this if you wish to track budget against a specific task of the project. </br> From the drop down for Task, pick the task within list of tasks of the project. </br> If you wish to track budget against all tasks of the project, you can leave the task as blank. |
| Select Product | Optional | This field will let you choose if you wish to budget for an existing product in the organization or a write-in product. </br> Pick from the drop down if its 'Existing/Write-In' product. |
| Write in Product | Optional | Applicable only when Select Product is – Write-In. </br> Fill the name of the product you wish to budget for. </br> Note: Writing a new product in budget line would not create a new product in the list of products of organization. </br> Matching of actual material usage against this budget line would happen only if the product in actual material usage, matches exactly with that of budget line, along with other dimensions. |
| Product | Optional | Applicable only when Select Product is – Existing. </br> From the drop down pick the product you wish to budget for. </br> Default value - Blank. |
| Cost Source | Optional | Allowed choices – Blank, Internal, External. </br> If you wish to track the costs irrespective of the cost source leave this field as blank. </br> Fill this as Internal, to track the costs with cost source as internal. </br> Fill this as External, to track the costs from subcontractors. </br> Default value - Blank |
| Vendor Name | Optional | Applicable only when Cost Source is External. </br> Pick the vendor if you wish to track the costs from a specific vendor or subcontractor. </br> Leave this field as blank if wish to track the costs from any vendor or subcontractor. </br> Default value – Blank |
| Quantity | Optional | Fill the quantity you wanted to budget for the selected dimensions of material. </br> Actual quantity gets tracked against the budgeted quantity, only if a budget line had quantity. </br> Only amount gets tracked against the dimensions of the budget line if quantity is left blank. </br> Default value – Blank. |
| Unit Group | Optional | If Select Product is 'Existing', Unit group would be defaulted from the unit group of the selected product. </br> If Select Product is 'Write-In', you can pick the suitable Unit group for the product from the list of unit groups in the drop down. |
| Unit | Optional |If Select Product is 'Existing', Unit would be defaulted from the unit of the selected product. </br> If Select Product is 'Write-In', you can pick the suitable unit for the product from the list of units in the Unit-group selected. </br> If you choose to pick a unit, other than the list of units displayed in drop down for the selected Unit group, the unit group field would be cleared to pick the right unit group for the selected unit. |
| Unit Price | Optional | Unit price is the price of the one-unit quantity of time or material, or expense selected. </br> If you wish to get the price list unit price based on the selected dimensions, click 'Save & Close' which would calculate the unit price if available in the system based on the selected dimensions. </br> You can override and update the defaulted unit price to a new value if you wish to track against a certain unit price. |
| Currency | Mandatory |If you wish to get the price list currency based on the selected dimensions, click 'Save & Close' which would get the currency from price list. </br> You can update currency to any other currency you wanted to budget for. </br> This means the currency conversion would apply while tracking if actual currency is different from budgeted currency for the selected dimensions. </br> Defaulted to Organization Currency. |
| Amount | Mandatory | Calculated as Quantity \* Unit price if quantity is filled. </br> If quantity is not filled, fill this field with the amount you wanted to budget against the selected dimensions of the budget line. </br> Amount must be a positive non-zero number. |
| Contingency | Optional | Fill the contingency amount you wish to add to the budgeted amount. </br> Budget for the selected dimensions would be equal to Amount + Contingency. |
| Budget | Mandatory | Auto-filled based on the dimensions. </br> This holds the budget for the budget line for the selected dimensions. </br> Budget = Amount + Contingency. |


### Expense budget line:

Pre-requisite: Project budget is created for project as per 'Create, Delete, Revision of Project budget'

Follow the below steps for creating a project budget line for transaction class 'Expense'.

1. Sign-in to Project Operations.
2. Change area to **'Projects'** in left nav
3. Click the project you wish to create the expense budget line.
4. Since project budget is created, you should see a tab **'Budget'**
5. Click **'+New Project Budget Line'** to create budget line.
6. A Quick create form would launch with default Transaction class selected as 'Time'
7. Change the Transaction class to **'Expense'** from the drop down.
8. Once all fields are updated as per the below table, select 'Save & Create New' to create another budget line or select 'Save & Close' to save the details and close the quick create form.
9. Budget line fields can be edited on the grid under **'Budget'** tab, it would be saved when you tab out to next line in the grid. This is possible only till budget is submitted for approval.

| **Field** | **Requirement** | **Comments** |
| --- | --- | --- |
| Transaction Class | Mandatory | From the drop down, change the transaction class to 'Expense' |
| Transaction Category | Optional | Pick the transaction category from drop down, which would describe the specific expense category you want to budget for. </br> This would display only the transaction categories that have a related expense category. </br> Leave this as blank if the budget line needs to be applicable for all expense categories. |
| Description | Optional | Use this field to describe about the budget line. </br> For eg: 'Expense budget for flights' or 'Expense budget for meals' |
| Start Date | Mandatory | Defines the start date of budget line. </br> Would define from when the actuals of the projects would be tracked against the budget line. </br> Defaulted to start date of the project. </br> This date must be between start and end date of the project. |
| End Date | Mandatory | Defines the end date of budget line. </br> Would define till when the actuals of the projects would be tracked against the budget line. </br> Defaulted to end date of the project. </br> This date must be between start and end date of the project. |
| Task | Optional | Fill this if you wish to track budget against a specific task of the project. </br> From the drop down for Task, pick the task within list of tasks of the project. </br> If you wish to track budget against all tasks of the project, you can leave the task as blank. |
| Cost Source | Optional | Allowed choices – Blank, Internal, External. </br> If you wish to track the costs irrespective of the cost source leave this field as blank. </br> Fill this as Internal, to track the costs with cost source as internal. </br> Fill this as External, to track the costs from subcontractors. </br> Default value - Blank. |
| Vendor Name | Optional | Applicable only when Cost Source is External. </br> Pick the vendor if you wish to track the costs from a specific vendor or subcontractor. </br> Leave this field as blank if wish to track the costs from any vendor or subcontractor. </br> Default value – Blank. |
| Quantity | Optional | Fill the quantity you wanted to budget for the selected dimensions of material. </br> Actual quantity gets tracked against the budgeted quantity, only if a budget line had quantity. </br> Only amount gets tracked against the dimensions of the budget line if quantity is left blank. </br> Default value – Blank. |
| Unit Group | Optional | Unit group to be defaulted to the selected Transaction Category. </br> If Transaction Category was left empty, you can pick the Unit group from the list of unit groups displayed in the drop down. |
| Unit | Optional | Unit would be defaulted to the unit of selected transaction category. </br> If Transaction Category was left empty, you can pick the Unit from the list of units displayed in the drop down from the selected Unit group. </br> If you choose to pick a unit, other than the list of units displayed in drop down for the selected Unit group, the unit group field would be cleared to pick the right unit group for the selected unit. |
| Unit Price | Optional | Unit price is the price of the one-unit quantity of time or material, or expense selected. </br> If you wish to get the price list unit price based on the selected dimensions, click 'Save & Close' which would calculate the unit price if available in the system based on the selected dimensions. </br> You can override and update the defaulted unit price to a new value if you wish to track against a certain unit price. |
| Currency | Mandatory | If you wish to get the price list currency based on the selected dimensions, click 'Save & Close' which would get the currency from price list. </br> You can update currency to any other currency you wanted to budget for. This means the currency conversion would apply while tracking if actual currency is different from budgeted currency for the selected dimensions. </br> Defaulted to Organization Currency. |
| Amount | Mandatory | Calculated as Quantity \* Unit price if quantity is filled. </br> If quantity is not filled, fill this field with the amount you wanted to budget against the selected dimensions of the budget line. </br> Amount must be a positive non-zero number. |
| Contingency | Optional | Fill the contingency amount you wish to add to the budgeted amount. </br> Budget for the selected dimensions would be equal to Amount + Contingency. |
| Budget | Mandatory | Auto-filled based on the dimensions. </br> This holds the budget for the budget line for the selected dimensions. </br> Budget = Amount + Contingency. |

