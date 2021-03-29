---
title: Material Uage Log
description: This topic provides information about how to log material usage against projects and projec tasks.
author: rumant
manager: AnnBe
ms.date: 11/19/2020
ms.topic: article
ms.service: project-operations
ms.reviewer: kfend
ms.author: rumant
---

# Material usage log entry 

_**Applies to:** Project Operations for resource/non-stocked based scenarios, Lite deployment - deal to proforma invoicing_

As the project team works on various tasks on the project, they could be consuming or using materials. Material usage log provides a way to record this usage so that it can be approved by the Project Manager and then eventually could also be invoiced to the customer. 

## Record the usage of material

You can record the usage of catalog or write in materials and submit them to the approver.

1. Go to **Material Usage**, and select **New**.
2. On the **New Material usage** page, enter the required material usage information, and then select **Save**.

The following table provides information about the fields on the **Material Usage log** form. 

| **Field** | **Description** | **Downstream impact** |
| --- | --- | --- |
| Description | A description of the specific material usage. |  |
| Date | The date on which the material is expected to be used. | There is no downstream impact for this field. |
| Project | A list projects that are active | Selecting a project for a material usage log will impact the **Task** field to show only those tasks that are on the project |
| Task | A list of tasks in the project. This includes summary and leaf node tasks. | Selecting a task for a material usage log will impact the actual material cost and actual material sales for a task. If this field is left empty, the corresponding material usage cost and sales is tracked and summarized only at the project level. |
| Select Product |  User may select to specify is this material usage is for an **Existing** ie. Catalog product or a **Write in** product | This field determines if the user is selecting a product from the catalog or a write in product. |
| Product | ID of the Product from Product catalog. When the user picks a product id, **Select Product** field is automatically updated to **Existing product** . The ID is used for retrieving cost and sales price from the price list | |
| WriteIn Product Description | A text for write in name of the Product. This field should be used in conjunction with the selection of **Write In** product in the Select product field.| |
| Bookable Resource| Resource that used this material on the project. This field is defaulted to the Bookable Resource of the logged in user but can be changed to record usage on behalf of other members on the project team.| |
| Unit group | The default value in this field comes from the unit group that's set up as default on the catalog product. You can update this field to select another unit group. | There is no downstream impact for this field. |
| Unit | The value in this field defaults to the default unit of the selected product. You can update this field to select another unit. | Changing the unit results in a different default unit price and cost. |
| Quantity | Quantity of the product that has been used on the project or the project task. | There is no downstream impact for this field. |
| Unit Cost | Unit cost of the selected product and unit combination as set up in the applicable cost price list | The unit cost is always shown in the project's cost currency. If there is no setup of unit cost for the combination product and unit setup in the price list, then unit cost will default to 0.00 |
| Total Cost | The cost amount that is calculated as quantity \* unit cost.| The cost amount is always shown in the project's cost currency. |


## Submit material usage for review and approval 
After you've finished capturing all your material usage, and you're ready to have them approved, you must submit them.

1. Go to **Material Usage Log**, and select one or more entries. Or, select all the material usage records by using the check box on the header.
2. Select **Submit**. The system processes the selected entries and then creates material usage approval requests.

## Recall a material usage log

When you submit a material usage by mistake, you can recall it. The time that is required to recall a material usage entry depends on its approval stage.  If the approver hasn't yet approved the entry, the recall can occur immediately. However, if the entry has already been approved, the approver is asked to approve the recall and reverse the transactions.

1. Go to **Material Usage**, and then, in the list of material usage logs, select the material usage to recall.
2. Select **Recall**. If the material usage entry hasn't yet been approved, the system immediately recalls it. If the material entry has already been approved, a recall request is created to notify the approver that you want to recall the material usage. The approver will then confirm that the reversal can be done, and the entry will be returned.

## Delete a material usage log

Material usage logs that haven't yet been submitted can be deleted. To delete a material usage log that has already been submitted, you must first recall it.

## See also

- [Approvals overview](../approvals/approvals-overview.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
