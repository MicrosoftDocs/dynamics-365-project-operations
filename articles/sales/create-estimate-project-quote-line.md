---
title: Estimate a project quote line
description: This article provides information about how to create an estimate on a project quote line.
author: rumant
ms.date: 04/01/2021
ms.topic: article
ms.reviewer: johnmichalak
ms.author: rumant
---

# Estimate a project quote line

_**Applies To:** Project Operations for resource/non-stocked based scenarios_

A project-based quote line has details that help with estimating the cost and potential revenue of the work involved to deliver the quote line.

To estimate a project-based quote line, on the quote line, select the **Quote Line Detail** tab. There are two ways to create an estimate on a project-based quote line:

   - Manually create the estimate directly on the quote line using quote line details. 
   - Create a project and a project plan, and then associate the project and tasks on the project to the quote line. The process to import the estimates on the project plan into the quote line based on the information you provided will be enabled.

## Create estimates directly on a project-based quote line

To create estimates directly on a project-based quote line, follow these steps:

1. To create an estimate on a project-based quote line, select the **Quote Line Detail** tab. The line item that you create on this tab will summarize the quoted value for this quote line. 
2. To create quote line details, select **New quote line detail** on the **Quote Line Details** subgrid. A quick create slider will open. The following fields on the **Quote Line** page.

| **Field** | **Location** | **Description** | **Downstream impact** |
| --- | --- | --- | --- |
| Description | Quick create | A description of the specific estimate. | This value defaults to the related quote line detail for cost that is automatically created. |
| Transaction Class | Quick create | This drop-down list provides the transaction classes that are included on the **General** tab of project-based quote line.  | This value defaults to the related quote line detail for cost that is automatically created. |
| Select Product | Quick create | Applies when the transaction class is **Material**. You can select to specify that this estimate line is for an **Existing** (catalog) product or a **Write in** product. | This value defaults to the related quote line detail for cost that is automatically created. |
| Product | Quick create | The ID of the product from the product catalog. This field is only enabled when you select **Existing** in the **Select Product** field. The ID is used to retrieve the sales price from the project price list on the quote. | This value defaults to the related quote line detail for cost that is automatically created. |
| Write In Product | Quick create | A text box to write in the product name. This field is only enabled when you select **Write In** in the **Select Product** field.| This value defaults to the related quote line detail for cost that is automatically created. |
| Role | Quick create | The role of the person that will perform this work or incur this expense. | This value defaults to the related quote line detail for cost that is automatically created. |
| Category | Quick create | The category of the work or expense. | This value defaults to the related quote line detail for cost that is automatically created. |
| Start Date | Quick create | The start date of the work. | This field defaults to the quote line detail for cost that is automatically created. |
| End Date | Quick create | The end date of the work. | This field defaults to the quote line detail for cost that is automatically created. |
| Resourcing Company | Quick Create | The resourcing company or legal entity that incurs this cost and provides the resource to work on it. | The value defaults to the related quote line detail for cost that is automatically created and is used in cost price retrieval. |
| Resourcing Unit | Quick create | The resourcing unit that incurs this cost and provides the resource to work on it. | This value defaults to the related quote line detail for cost that is automatically created and is used in cost price retrieval. |
| Unit schedule | Quick create | The unit group of the work, product, or expense. Units belong to a unit schedule or a group of units. For example, miles and kilometers are units that belong to a group of units that describes distance. | This value defaults to the related quote line detail for cost that is automatically created. |
| Unit | Quick create | The unit of the work, product, or expense. | This value defaults to the related quote line detail for cost that is automatically created. |
| Quantity | Quick create | The quantity of work, product, or expense. | This value defaults to the related quote line detail for cost that is automatically created. |
| Unit price | Quick Create |The bill rate of the role that is performing the work, the unit price of the product, or the sales price of the product or expense category. The default for **Time** is based on the combination of pricing dimension values on the role price line of the project price list that is effective for the start date. For **Expenses**, the default is from the price setup for the transaction category in the project price list that is effective for the start date. If the pricing method for the transaction category is not price-per-unit, there is no default, and this field is left blank. For products, this field's default is based on the **Price list item**  line in the project price list that is effective for the start date.| The cost rate of the role that is performing the work, the cost per unit of the expense category, or the unit cost of the product. The default for **Time** is based on the combination of pricing dimension values on the role price line of the cost price list attached to the contracting unit effective for the start date. For expenses, the default is based on the category price line of the cost price list attached to the contracting unit that is effective for the start date. If the pricing method for the transaction category isn't price-per-unit, there's no default and this field is left blank. For products, this field's default is based on the **Price list item**  line of the cost price list attached to the contracting unit that is effective for the start date.|
| Estimated Tax | Quick create | You can manually enter the estimated tax for this work or expense. | There is no downstream impact for this field. |
| Amount | Quick create | You can manually input information into this field if the **Quantity** and **Price** fields are left blank. If these fields are not blank, this field becomes read only and is calculated as (Quantity \* Unit price) + Tax. | There is no downstream impact for this field. |

## Update prices on quote line details

If you have changed prices on the project price list that is attached to the quote, or on cost price list of the contracting unit, you can select **Recalculate** on the **Quote** page, to refresh the prices on the individual quote line details to reflect this change. When you select **Recalculate**, a warning appears that informs you that prices on quote line details for all quote lines on this quote will be reset. Select **Yes** to refresh prices for both sales and cost quote line details.

## Access quote line details for cost

To access quote line details for cost, follow these steps:

1. On the **Quote Line Details** tab, select a row in the grid to enable actions on the toolbar of the subgrid. 
2. Select **Open Cost Detail** to see the related cost rate and amount for this quote line.

> [!NOTE]
> Changing the resourcing unit, quantity, dates, role, or category values on the quote line detail for cost will change the corresponding values on the quote line details for sales.

## Currency on quote line details for cost and sales

The currency on the quote line detail for sales defaults from the project price list that is effective for the start date of the quote line detail.

The currency on the quote line detail for cost defaults from the price list of the contracting unit of the quote that is effective for the start date of the quote line detail for cost.

> [!NOTE]
> Profitability calculations convert the amount on quote line details for cost and sales into the base currency of the environment to report the overall estimated margin on the quote. Currency rounding errors and changed margins could occur because of the lack of date effective exchange rates. Use these calculations only on project quotes as these are approximations and are not actual statutory or other reporting that requires higher precision of rounding and awareness of date effectivity for exchange rates.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
