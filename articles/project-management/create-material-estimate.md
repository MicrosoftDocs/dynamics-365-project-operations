---
title: Financial estimates for materials on projects
description: This article provides information about defining or estimating project-based materials.
author: rumant
ms.date: 03/30/2021
ms.topic: article
ms.reviewer: johnmichalak
ms.author: rumant
---

# Financial estimates for materials on projects

_**Applies To:** Project Operations for resource/non-stocked based scenarios, Lite deployment - deal to proforma invoicing_

Dynamics 365 Project Operations allows Project managers to define project-based material costs for each project or task. Each material estimate can be associated with a specific project task. Materials that are used on projects can be write-in products or products from the product catalog. For each combination of a product and a unit, a price can be defined in the project price lists for sales and the project price lists for cost.  

Complete the following steps to view, add, or delete a project material estimate.

1. Go to **Projects**, and select the project you want to update.
2. On the **Material Estimates** tab, view the list of project material estimates.
3. Select **New Material estimate** to create a new material estimate. Or, select a material estimate to delete, and then select **Delete Material Estimate**.

> [!NOTE]
> **Now in Preview: Project estimate updates feature**

> A new feature labeled Project estimate updates is currently in Preview. Once the **Enable Project estimate updates** feature is enabled, it can't be disabled. These updates include label changes at the Project level where now the original Estimates tab is showing Time phased estimates, and the newly labeled Estimates tab is a consolidated view of Expense and Material Estimates. The new grid for Expense and Material estimates allows easy creation and editing of those estimates.

>To enable the **Project estimate updates** feature, follow these steps.

>1. Go to **Settings** \> **Parameters**.
>1. Open the **Parameters** record.
>1. On the Action Pane, on the **Feature Control** tab, select **Project estimate updates**.
>1. In the confirmation dialog box, select **OK**.
>1. After a few moments, refresh your browser. The feature capabilities will now be available and the feature will be removed from the list of features to be enabled. 

The following table provides information about the fields on the **Material Estimate line** on a project. 

| **Field** | **Description** | **Downstream impact** |
| --- | --- | --- |
| Task | A list of tasks in the project. This includes summary and leaf node tasks. | When you select a task for a material estimate line, the estimated material cost and estimated material sales for a task are impacted. If this field is empty, the material estimate is tracked and summarized only at the project level. |
| Select Product |  You can specify whether the estimate line is for an existing (catalog) or write-in product. | This field determines if you select a product from the catalog or a write in product. |
| Product | The ID of the product from the product catalog. When you select a product ID, the value in the **Select Product** field is automatically updated to **Existing product**. The ID is used to retrieve the cost and sales prices from the price list. | There's no downstream impact for this field. |
| Write In Product Description | A text field to write in the name of the product. This field should be used when **Write In** is selected in the **Select Product** field.| There's no downstream impact for this field. |
| Start date | The forecasted date on which the material is expected to be used. | There's no downstream impact for this field. |
| Unit group | The default value in this field comes from the default unit group on the catalog product. You can update this field to select another unit group. | There's no downstream impact for this field. |
| Unit | The value in this field comes from the default unit of the selected product. You can update this field to select another unit. | Changing the unit results in a different default unit price and cost. |
| Quantity | The estimated quantity of the product that will be used on the project. | There's no downstream impact for this field. |
| Unit Cost | The unit cost of the selected product and unit combination as set up in the applicable cost price list. | The unit cost is always shown in the project's cost currency. If there is no set up of unit cost for the combination of the product and unit setup in the price list, the unit cost will default to 0.00. |
| Unit Price | The price of the selected product and unit combination as set up in the applicable sales price list. | The unit price is always shown in the project's sales currency. If there is no setup of unit price  for the combination of the product and unit setup in the price list, then unit price will default to 0.00.|
| Total Cost | The cost amount that is calculated as quantity \* unit cost.| The cost amount is always shown in the project's cost currency. |
| Total Sales | The sales amount that is calculated as quantity \* unit price. | The sales amount is always shown in the project's sales currency. |


[!INCLUDE[footer-include](../includes/footer-banner.md)]
