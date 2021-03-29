---
title: Financial estimates for materials on projects
description: This topic provides information about defining or estimating project-based materials.
author: rumant
manager: Annbe
ms.date: 03/19/2021
ms.topic: article
ms.service: project-operations
ms.reviewer: kfend 
ms.author: rumant
---

# Financial estimates for materials on projects
_**Applies To:** Project Operations for resource/non-stocked based scenarios, Lite deployment - deal to proforma invoicing_

Dynamics 365 Project Operations allows Project managers to define project-based material costs for each project or a task. Each material estimate can be associated with a specific project task. Expenses are categorized into different expense categories, which are defined at the organizational level. Pricing and costing for each expense category is defined in the price list. 

Complete the following steps to view, add, or delete a project material estimate.

1. Go to **Projects**, and select the project you want to work on.
2. Select the **Material Estimates** tab and view the list of project material estimates.
3. Select **New Material estimate** to create a new material estimate. Or, select a material estimate to delete, and then select **Delete Material Estimate**.

The following table provides information about the fields on the **Material Estimate line** on a Project. 

| **Field** | **Description** | **Downstream impact** |
| --- | --- | --- |
| Task | A list of tasks in the project. This includes summary and leaf node tasks. | Selecting a task for a material estimate line will impact the estimated material cost and estimated material sales for a task. If this field is left empty, the material estimate is tracked and summarized only at the project level. |
| Select Product |  User may select to specify is this estimate line is for an **Existing** ie. Catalog product or a **Write in** product | This field determines if the user is selecting a product from the catalog or a write in product. |
| Product | ID of the Product from Product catalog. When the user picks a product id, **Select Product** field is automatically updated to **Existing product** . The ID is used for retrieving cost and sales price from the price list | |
| WriteIn Product Description | A text for write in name of the Product. This field should be used in conjunction with the selection of **Write In** product in the Select product field.| |
| Start date | The forecasted date on which the material is expected to be used. | There is no downstream impact for this field. |
| Unit group | The default value in this field comes from the unit group that's set up as default on the catalog product. You can update this field to select another unit group. | There is no downstream impact for this field. |
| Unit | The value in this field defaults to the default unit of the selected product. You can update this field to select another unit. | Changing the unit results in a different default unit price and cost. |
| Quantity | The estimated quantity of the product that is to be used on the project. | There is no downstream impact for this field. |
| Unit Cost | Unit cost of the selected product and unit combination as set up in the applicable cost price list | The unit cost is always shown in the project's cost currency. If there is no setup of unit cost for the combination product and unit setup in the price list, then unit cost will default to 0.00 |
| Unit Price | The price of the selected product and unit combination as setup in the applicable sales price list. | The unit price is always shown in the project's sales currency. If there is no setup of unit price  for the combination product and unit setup in the price list, then unit price will default to 0.00|
| Total Cost | The cost amount that is calculated as quantity \* unit cost.| The cost amount is always shown in the project's cost currency. |
| Total Sales | The sales amount that is calculated as quantity \* unit price. | The sales amount is always shown in the project's sales currency. |


[!INCLUDE[footer-include](../includes/footer-banner.md)]
