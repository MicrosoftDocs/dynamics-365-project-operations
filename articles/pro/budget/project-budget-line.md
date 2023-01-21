---
title: Project budget line – Time, Material, and Expense
description: This article provides the details for how to create and delete a project cost budget line.
author: niranjanmaski
ms.date: 01/13/2023
ms.topic: article
ms.reviewer: johnmichalak
ms.author: nimaski
---

# Project budget line – Time, Material, and Expense

**_Applies To:_** _Lite deployment - deal to proforma invoicing_

The Project budget has budget lines that are a snapshot of the budgeted quantity and the amount against dimensions which needs to be tracked.

Project budget lines can be created under three Transaction classes.

- A **Time** budget line tracks the recorded and approved time of bookable resources against the project.
- A **Material** budget line tracks the consumed materials which are approved against the project.
- An **Expense** budget line tracks the approved expenses against the project.

> [!NOTE]
> Budget dimensions should be unique across all budget lines. You can't create two budget lines with the same dimensions.

### Time budget line:

Pre-requisite: A Project budget is created for the project. For more information, see [Create, Delete, Revision of Project budget](create-delete-project-budget.md).

To create a project budget line for the transaction class **Time**, follow these steps.

1. Sign-in to Microsoft Dynamics 365 Project Operations.
2. Change area to **Projects** in the left navigation.
3. Select the project you wish to create the Time budget line for.
4. Because project budget is created, you should see the **Budget** tab.
5. Select **+ New Project Budget Line** to create budget line.
6. A quick create form launches with the default **Transaction class** selected as **Time**.
7. Once all of the fields are updated as per the below table, select **Save & Create New** to create another budget line, or select **Save & Close** to save the details and close the quick create form.
8. Budget line fields can be edited on the grid on the **Budget** tab. Changes are saved when you tab out to next line in the grid. This is possible only till budget is submitted for approval.

| **Field** | **Requirement** | **Comments** |
| --- | --- | --- |
| Transaction Class | Mandatory | Default option is 'Time', leave it with Time. |
| Description | Optional | Use this field to describe the budget line. </br> For example, Time for design task or Time for foundation activity. |
| Start Date | Mandatory | Defines the start date of the budget line.</br> Defines when the actuals of the projects are tracked against the budget line. </br> Defaults to the start date of the project. </br>This date must be between the start and the end date of the project.|
| End Date | Mandatory | Defines the end date of the budget line. </br>Defines the duration the actuals of the projects are tracked against the budget line. </br> Defaults to the end date of the project. </br>This date must be between the start and the end date of the project. |
| Task | Optional | Complete this field in if you wish to track the budget against a specific task of the project. </br>From the drop down for Task, select the task within list of tasksof the project. </br>If you wish to track budget against all tasks of the project, you can leave the task as blank. | 
| Role | Optional | Complete this field if you wish to track budget against a specific role. </br>From the drop down for Role, select the role within defined list of roles of the organization. </br>If you wish to track budget against all roles, you can leave the role as blank. |
| Resource | Optional | Complete this field if you wish to track budget against a specific bookable resource. </br>From the drop down for Resource, pick the bookable resource, from the list of bookable resource for the selected task or role. </br>You can select any other specific resource that is not assigned to any role or a task by selecting **Search** from within the drop down, provided there was no role or task selected. </br>If you wish to track budget against all bookable resources, you can leave the resource field as blank. |
| Resourcing Unit | Optional | Complete this field if you wish to track the budget against a particular resourcing unit. </br>If **Resource** is selected, the resourcing unit must align to the resourcing unit of the selected resource. </br>If **Resource** is not selected, select a resourcing unit if you wish to track budget against a specific resourcing unit. </br> Leave it blank if you wish to track the budget against all resourcing units. </br> Default value - Blank|
| Cost Source | Optional | Allowed choices - **Blank**, **Internal**, **External**. </br> If you wish to track the costs irrespective of the cost source, leave this field as blank. </br> Select **Internal** to track the costs with cost source as internal. </br> Select **External**, to track the costs from subcontractors. </br> Default value - **Blank**. |
| Vendor Name | Optional | Applicable only when the **Cost Source** is **External**. </br> Select a vendor if you wish to track the costs from a specific vendor or subcontractor. </br> Leave this field as blank if wish to track the costs from any vendor or subcontractor. </br> Default value – Blank | 
| Quantity | Optional | Complete the quantity you wanted to budget for the selected dimensions for **Time**, **Material**, and **Expense**. </br> Actual quantity gets tracked against the budgeted quantity only if a budget line has a quantity. </br> Only the amount gets tracked against the dimensions of the budget line if quantity is left blank. </br> Default value – **Blank**. |
| Unit Group | Optional | Unit group gets locked with **Time** for budget line with transaction class as time. |
| Unit | Optional | Select the **Unit** from the units belonging to the **Time** Unit group. </br> **Unit** displays only the units from the selected **Unit group**. |
| Unit Price | Optional | Unit price is the price of the one-unit quantities of **Time**, **Material**, or **Expense**. </br> If you wish to get the price list unit price based on the selected dimensions, select **Save & Close** which calculates the unit price if available in the system based on the selected dimensions. </br> You can override and update the defaulted unit price to a new value if you wish to track against a certain unit price. |
| Currency | Mandatory | If you wish to get the price list currency based on the selected dimensions, select **Save & Close** which would get the currency from price list. </br> You can update currency to any other currency you wanted to budget for. This means the currency conversion would apply while tracking if actual currency is different from budgeted currency for the selected dimensions. </br> Defaulted to Organization Currency. |
| Amount | Mandatory | Calculated as Quantity \* Unit price if quantity is filled. </br> If quantity is not filled, fill this field with the amount you wanted to budget against the selected dimensions of the budget line. </br> Amount must be a positive non-zero number. |
| Contingency | Optional | Fill the contingency amount you wish to add to the budgeted amount. </br> Budget for the selected dimensions would be equal to Amount + Contingency. |
| Budget | Mandatory | Auto-filled based on the dimensions. </br> This holds the budget for the budget line for the selected dimensions. </br> Budget = Amount + Contingency. |


### Material budget line:

Pre-requisite: A Project budget is created for the project. For more information, see [Create, Delete, Revision of Project budget](create-delete-project-budget.md).

To create a project budget line for the transaction class **Material**, follow these steps.

1. Sign-in to Project Operations.
2. Change area to **Projects** in the left navigation.
3. Select the project you wish to create the material budget line.
4. Because the project budget is created, you should see the **Budget** tab.
5. Select **+ New Project Budget Line** to create a budget line.
6. A quick create form launches with the default **Transaction class** selected as **Time**.
7. Change the **Transaction class** to **Material** from the drop down.
8. After all of the fields are updated as per the below table, select **Save & Create New** to create another budget line, or select **Save & Close** to save the details and close the quick create form.
9. Budget line fields can be edited on the grid on the **Budget** tab. Changes are saved when you tab out to next line in the grid. This is possible only till budget is submitted for approval.

| **Field** | **Requirement** | **Comments** |
| --- | --- | --- |
| Transaction Class | Mandatory | From the drop down, change the **Transaction class** to **Material**. |
| Description | Optional | Use this field to describe the budget line. </br> For example, Time for design task or Time for foundation activity. |
| Start Date | Mandatory | Defines the start date of the budget line.</br> Defines when the actuals of the projects are tracked against the budget line. </br> Defaults to the start date of the project. </br>This date must be between the start and the end date of the project.|
| End Date | Mandatory | Defines the end date of the budget line. </br>Defines the duration the actuals of the projects are tracked against the budget line. </br> Defaults to the end date of the project. </br>This date must be between the start and the end date of the project. |
| Task | Optional | Complete this field in if you wish to track the budget against a specific task of the project. </br>From the drop down for Task, select the task within list of tasksof the project. </br>If you wish to track budget against all tasks of the project, you can leave the task as blank. | 
| Select Product | Optional | This field lets you choose to budget for an existing product in the organization or a write-in product. </br> Select from the drop down if it's an **Existing/Write-In** product. |
| Write in Product | Optional | Applicable only when Select Product is – Write-In. </br> Complete the name of the product you wish to budget for. </br> **Writing in a new product in budget line doesn't create a new product in the list of products of an organization**. </br> Matching of actual material usage against this budget line happens only if the product in actual material usage, matches exactly with that of budget line, along with other dimensions. |
| Product | Optional | Applicable only when **Select Product** is **Existing**. </br> From the drop down select the product you wish to budget for. </br> Default value is **Blank**. |
| Cost Source | Optional | Allowed choices - **Blank**, **Internal**, **External**. </br> If you wish to track the costs irrespective of the cost source, leave this field as blank. </br> Select **Internal** to track the costs with cost source as internal. </br> Select **External**, to track the costs from subcontractors. </br> Default value - **Blank**. |
| Vendor Name | Optional | Applicable only when the **Cost Source** is **External**. </br> Select a vendor if you wish to track the costs from a specific vendor or subcontractor. </br> Leave this field as blank if wish to track the costs from any vendor or subcontractor. </br> Default value – Blank | 
| Quantity | Optional | Complete the quantity you wanted to budget for the selected dimensions for **Time**, **Material**, and **Expense**. </br> Actual quantity gets tracked against the budgeted quantity only if a budget line has a quantity. </br> Only the amount gets tracked against the dimensions of the budget line if quantity is left blank. </br> Default value – **Blank**. |
| Unit Group | Optional | Unit group gets locked with **Time** for budget line with transaction class as time. |
| Unit | Optional | Select the **Unit** from the units belonging to the **Time** Unit group. </br> **Unit** displays only the units from the selected **Unit group**. |
| Unit Price | Optional | Unit price is the price of the one-unit quantities of **Time**, **Material**, or **Expense**. </br> If you wish to get the price list unit price based on the selected dimensions, select **Save & Close** which calculates the unit price if available in the system based on the selected dimensions. </br> You can override and update the defaulted unit price to a new value if you wish to track against a certain unit price. |
| Currency | Mandatory | If you wish to get the price list currency based on the selected dimensions, select **Save & Close** which would get the currency from price list. </br> You can update currency to any other currency you wanted to budget for. This means the currency conversion would apply while tracking if actual currency is different from budgeted currency for the selected dimensions. </br> Defaulted to Organization Currency. |
| Amount | Mandatory | Calculated as Quantity \* Unit price if quantity is filled. </br> If quantity is not filled, fill this field with the amount you wanted to budget against the selected dimensions of the budget line. </br> Amount must be a positive non-zero number. |
| Contingency | Optional | Fill the contingency amount you wish to add to the budgeted amount. </br> Budget for the selected dimensions would be equal to Amount + Contingency. |
| Budget | Mandatory | Auto-filled based on the dimensions. </br> This holds the budget for the budget line for the selected dimensions. </br> Budget = Amount + Contingency. |


### Expense budget line:

Pre-requisite: A Project budget is created for the project. For more information, see [Create, Delete, Revision of Project budget](create-delete-project-budget.md).

To create a project budget line for the transaction class **Expense**, follow these steps.

1. Sign-in to Project Operations.
2. Change area to **Projects** in the left navigation.
3. Select the project you wish to create the expense budget line.
4. Because project budget is created, you should see the **Budget** tab.
5. Select **+ New Project Budget Line** to create budget line.
6. A quick create form launches with the default **Transaction class** selected as **Time**.
7. Change the **Transaction class** to **Expense** from the drop down.
8. After all of the fields are updated as per the below table, select **Save & Create New** to create another budget line, or select **Save & Close** to save the details and close the quick create form.
9. Budget line fields can be edited on the grid on the **Budget** tab. Changes are saved when you tab out to next line in the grid. This is possible only till budget is submitted for approval.

| **Field** | **Requirement** | **Comments** |
| --- | --- | --- |
| Transaction Class | Mandatory | From the drop down, change the **Transaction class** to **Expense**. |
| Description | Optional | Use this field to describe the budget line. </br> For example, Time for design task or Time for foundation activity. |
| Start Date | Mandatory | Defines the start date of the budget line.</br> Defines when the actuals of the projects are tracked against the budget line. </br> Defaults to the start date of the project. </br>This date must be between the start and the end date of the project.|
| End Date | Mandatory | Defines the end date of the budget line. </br>Defines the duration the actuals of the projects are tracked against the budget line. </br> Defaults to the end date of the project. </br>This date must be between the start and the end date of the project. |
| Task | Optional | Complete this field in if you wish to track the budget against a specific task of the project. </br>From the drop down for Task, select the task within list of tasksof the project. </br>If you wish to track budget against all tasks of the project, you can leave the task as blank. | 
| Cost Source | Optional | Allowed choices - **Blank**, **Internal**, **External**. </br> If you wish to track the costs irrespective of the cost source, leave this field as blank. </br> Select **Internal** to track the costs with cost source as internal. </br> Select **External**, to track the costs from subcontractors. </br> Default value - **Blank**. |
| Vendor Name | Optional | Applicable only when the **Cost Source** is **External**. </br> Select a vendor if you wish to track the costs from a specific vendor or subcontractor. </br> Leave this field as blank if wish to track the costs from any vendor or subcontractor. </br> Default value – Blank | 
| Quantity | Optional | Complete the quantity you wanted to budget for the selected dimensions for **Time**, **Material**, and **Expense**. </br> Actual quantity gets tracked against the budgeted quantity only if a budget line has a quantity. </br> Only the amount gets tracked against the dimensions of the budget line if quantity is left blank. </br> Default value – **Blank**. |
| Unit Group | Optional | Unit group gets locked with **Time** for budget line with transaction class as time. |
| Unit | Optional | Select the **Unit** from the units belonging to the **Time** Unit group. </br> **Unit** displays only the units from the selected **Unit group**. |
| Unit Price | Optional | Unit price is the price of the one-unit quantities of **Time**, **Material**, or **Expense**. </br> If you wish to get the price list unit price based on the selected dimensions, select **Save & Close** which calculates the unit price if available in the system based on the selected dimensions. </br> You can override and update the defaulted unit price to a new value if you wish to track against a certain unit price. |
| Currency | Mandatory | If you wish to get the price list currency based on the selected dimensions, select **Save & Close** which would get the currency from price list. </br> You can update currency to any other currency you wanted to budget for. This means the currency conversion would apply while tracking if actual currency is different from budgeted currency for the selected dimensions. </br> Defaulted to Organization Currency. |
| Amount | Mandatory | Calculated as Quantity \* Unit price if quantity is filled. </br> If quantity is not filled, fill this field with the amount you wanted to budget against the selected dimensions of the budget line. </br> Amount must be a positive non-zero number. |
| Contingency | Optional | Fill the contingency amount you wish to add to the budgeted amount. </br> Budget for the selected dimensions would be equal to Amount + Contingency. |
| Budget | Mandatory | Auto-filled based on the dimensions. </br> This holds the budget for the budget line for the selected dimensions. </br> Budget = Amount + Contingency. |
  

[!INCLUDE[footer-include](../../includes/footer-banner.md)]

[Microsoft](https://www.microsoft.com)
