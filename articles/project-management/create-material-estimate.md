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

1. Go to **Projects**, and select the project you want to work on.
2. Select **Project Estimates** tab.
3. At the top left of the grid, there is a view switcher which allows the selection of **Expenses** or **Materials**.
4. Once **Materials** is selected, all materials will be visible.
5. Select **New material estimate** to create a new material estimate. Or, select a material estimate to delete, and then select **Delete Estimate Line**.

The following table provides information about the fields on the **Material Estimate line** on a project. 

| **Field** | **Description** | **Downstream impact** |
| --- | --- | --- |
| Task | A list of tasks in the project. This includes summary and leaf node tasks. | When you select a task for a material estimate line, the estimated material cost and estimated material sales for a task are impacted. If this field is empty, the material estimate is tracked and summarized only at the project level. |
| Select Product |  You can specify whether the estimate line is for an existing (catalog) or write-in product. | This field determines if you select a product from the catalog or a write in product. |
| Product | The ID of the product from the product catalog. When you select a product ID, the value in the **Select Product** field is automatically updated to **Existing product**. The ID is used to retrieve the cost and sales prices from the price list. | There's no downstream impact for this field. |
| Write In Product | A text field to write in the name of the product. This field should be used when **Write In** is selected in the **Select Product** field.| There's no downstream impact for this field. |
| Start date | The forecasted date on which the material is expected to be used. | There's no downstream impact for this field. |
| Quantity | The estimated quantity of the product that will be used on the project. | There's no downstream impact for this field. |
| Unit group | The default value in this field comes from the default unit group on the catalog product. You can update this field to select another unit group. | There's no downstream impact for this field. |
| Unit | The value in this field comes from the default unit of the selected product. You can update this field to select another unit. | Changing the unit results in a different default unit price and cost. |
| Cost price | The unit cost of the selected product and unit combination as set up in the applicable cost price list. | The unit cost is always shown in the project's cost currency. If there is no set up of unit cost for the combination of the product and unit setup in the price list, the unit cost will default to 0.00. |

>[!NOTE]
> The grid allows in-line editing with the first line of the estimate being in cost context, which is always shown in the project's cost currency. When selecting the chevron, the grid will expand to a child row which provides the sales context of the estimate line, this is always shown in the project's sales currency.    

[!INCLUDE[footer-include](../includes/footer-banner.md)]
