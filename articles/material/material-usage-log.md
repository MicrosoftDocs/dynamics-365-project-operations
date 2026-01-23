---
title: Record material usage on projects and project tasks
description: This article provides information about how to log material usage against projects and project tasks.
author: suvaidya
ms.date: 06/10/2024
ms.topic: how-to
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak
ms.author: nshrivastava
---

# Record material usage on projects and project tasks

[!INCLUDE[banner](../includes/banner.md)]

_**Applies to:** Project Operations Integrated with ERP, Project Operations Core_

As a project team works through tasks on a project, they consume or use materials. A material usage log provides a way to record this usage so that it can be approved by the project manager and eventually invoiced to the customer. 

To record the usage of catalog or write-in materials and submit them to the approver, follow these steps: 

1. In the navigation pane, select **Material Usage**, and then select **New**.
2. On the **New Material Usage** page, enter the required material usage information, and then select **Save**.

The following table provides information about the fields on the **Material Usage Log** page. 

| **Field** | **Description** | **Downstream impact** |
| --- | --- | --- |
| Description | A description of the specific material usage. | There is no downstream impact for this field. |
| Date | The date on which the material is expected to be used. | There is no downstream impact for this field. |
| Project | A list projects that are active. | Selecting a project for a material usage log impacts the **Task** field to show only those tasks that are on the project. |
| Task | A list of tasks for the project including summary and leaf node tasks. | Selecting a task for a material usage log impacts the actual material cost and actual material sales for a task. If this field is empty, the corresponding material usage cost and sales is tracked and summarized only at the project level. |
| Select Product | Specify if this material usage is for an **Existing** (catalog) product or a **Write in** product. | This field determines the type of product. |
| Product | The ID of the product from product catalog. When you select a product ID, the **Select Product** field automatically updates to **Existing product**. The ID is used to retrieve cost and sales prices from the price list. | There is no downstream impact for this field. |
| WriteIn Product Description | A text field to write in the name of the product. This field is available when you select **Write In** product in the **Select product** field.| There is no downstream impact for this field. |
| Bookable Resource| Resource that used this material on the project. The default for this field is the bookable resource of the logged in user, but can be changed to record usage on behalf of other members on the project team. | There is no downstream impact for this field. |
| Unit group | The default value in this field comes from the unit group that's set up as the default on the catalog product. You can update this field to select another unit group. | There is no downstream impact for this field. |
| Unit | The default value in this field is the default unit of the selected product. You can update this field to select another unit. | Changing the unit results in a different default unit price and cost. |
| Quantity | The quantity of the product that has been used on the project or the project task. | There is no downstream impact for this field. |
| Unit Cost | The unit cost of the selected product and unit combination as set up in the applicable cost price list. | The unit cost is always shown in the project's cost currency. If there's no unit cost for the combination product and unit in the price list, the unit cost will default to 0.00. |
| Total Cost | The cost amount that is calculated as quantity \* unit cost.| The cost amount is always shown in the project's cost currency. |


## Submit material usage for review and approval 
After you capture all your material usage, and you're ready to have it approved, you must submit the usage information for review.

1. Go to **Material Usage Log** and select one or more entries. Or, select all the material usage records by using the check box on the header.
2. Select **Submit**. The system processes the selected entries and then creates material usage approval requests.

## Recall a material usage log

When necessary, you can recall a submitted material usage. The time required to recall a material usage entry depends on the approval stage.  If the approver hasn't yet approved the entry, the recall can occur immediately. However, if the entry has already been approved, the approver is asked to approve the recall and reverse the transactions.

1. Go to **Material Usage**, and in the list of material usage logs, select the material usage to recall.
2. Select **Recall**. If the material usage entry hasn't yet been approved, the system immediately recalls it. If the material entry has already been approved, a recall request is created to notify the approver that you want to recall the material usage. The approver will then confirm that the reversal can be done, and the entry will be returned.

## Delete a material usage log

You can delete material usage logs that haven't been submitted. To delete a material usage log that has already been submitted, you must first recall it.



[!INCLUDE[footer-include](../includes/footer-banner.md)]
