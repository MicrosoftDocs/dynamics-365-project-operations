---
title: Estimating a project-based quote line
description: This topic provides information about how to create an estimate on a project-based quote line.
author: rumant
manager: Annbe
ms.date: 10/01/2020
ms.topic: article
ms.service: project-operations
ms.reviewer: kfend 
ms.author: rumant
---

# Estimating a project-based quote line

_**Applies To:** Lite deployment - deal to proforma invoicing_

A project-based quote line has details that help with estimating the cost and potential revenue of the work involved to deliver the quote line.

To estimate a project-based quote line, on the project-based quote line, select the **Quote Line Detail** tab. There are two ways to create an estimate on a project-based quote line:

- Manually create the estimate directly on the quote line using quote line details 
- Create a project and a project plan, and then associate the project and tasks on the project to the quote line. The process to import the estimates on the project plan into the quote line based on the information you provided will be enabled.

## Create estimates directly on a project-based quote line

To create an estimate on a project-based quote line, select the **Quote Line Detail** tab. The line item that you create on this tab will summarize the quoted value for this quote line. 

To create quote line details, select **+ New quote line detail** on the **Quote Line Details** subgrid. A quick create slider will open. The following table provides details for the fields on the **Quote Line Detail** form and the how the values impact the functionality:

| **Field** | **Location** | **Description** | **Downstream impact** |
| --- | --- | --- | --- |
| Description | Quick create | A description of the specific estimate. | This field value defaults onto the related quote line detail for cost that is automatically created. |
| Transaction Class | Quick create | This drop-down list provides the transaction classes that are included on the **General** tab of project-based quote line.  | This field value defaults onto the related quote line detail for cost that is automatically created. |
| Select Product | Quick create | Applies when transaction class is Material. User may select to specify is this estimate line is for an **Existing** ie. Catalog product or a **Write in** product | This field value defaults onto the related quote line detail for cost that is automatically created. |
| Product | Quick create | ID of the Product from Product catalog. This field is only enabled when the user chose **Existing product** in the Select product field. The ID is used for retrieving the sales price from Project price list on the Quote | This field value defaults onto the related quote line detail for cost that is automatically created. |
| WriteIn Product | Quick create | A text for write in name of the Product. This field is only enabled when the user chose **Write In** product in the Select product field.| This field value defaults onto the related quote line detail for cost that is automatically created. |
| Role | Quick create | The role of the person that will perform this work or incur this expense. | This field value defaults onto the related quote line detail for cost that is automatically created. |
| Category | Quick create | Category of the work or expense. | This field value defaults onto the related quote line detail for cost that is automatically created. |
| Start Date | Quick create | Start date of the work. | This field defaults to the quote line detail for cost that is automatically created. |
| End Date | Quick create | End date of the work. | This field defaults to the  quote line detail for cost that is automatically created. |
| Resourcing Unit | Quick create | Resourcing unit that will incur this cost and provide the resource to work on it. | This field value defaults onto the related quote line detail for cost that is automatically created and is used in cost price retrieval. |
| Unit schedule | Quick create | Unit group of the work, product or expense. Units belong to a unit schedule or a group of units. For example, Miles and KMs are units that belong to a group of units that describes distance. | This field value also defaults to the related quote line detail for cost that is automatically created. |
| Unit | Quick create | Unit of the work, product or expense. | This field value defaults onto the related quote line detail for cost that is automatically created. |
| Quantity | Quick create | Quantity of work, product or expense | This field value defaults onto the related quote line detail for cost that is automatically created. |
| Unit price | Quick Create |The bill rate of the role that is performing the work, unit price of the product or the sales price of the product or expense category. This field defaults for **Time** based on the combination of pricing dimension values on the role price line of the project price list that is effective for the start date. For **Expenses**, this field's default is from the price setup for the transaction category in the project price list that is effective for the start date. If the pricing method for the transaction category is not **price-per-unit**, there is no default, and this field is left blank. For products, this field's default is based on the **Price list item**  line in the project price list that is effective for the start date.| The cost rate of the role that is performing the work, or the cost per unit of the expense category or the unit cost of the product. This field defaults for **Time** based on the combination of pricing dimension values on the role price line of the cost price list attached to the contracting unit effective for the start date. For expenses, this field's default is based on the category price line of the cost price list attached to the contracting unit that is effective for the start date. If the pricing method for the transaction category is not price-per-unit, there is no default and this field is left blank. For products, this field's default is based on the **Price list item**  line of the cost price list attached to the contracting unit that is effective for the start date.|
| Estimated Tax | Quick create | You can manually enter the estimated tax for this work or expense. | There is no downstream impact of this field. |
| Amount | Quick create | You can manually input information into this field if the **Quantity** and **Price** fields are left blank. If these fields are not blank, this field becomes read-only and is calculated as (Quantity \* Unit price) + Tax. | There is no downstream impact of this field. |


## Update prices on quote line details

If you have changed prices on the project price list that is attached to the quote, or on cost price list of the contracting unit, you can select **Recalculate** on the **Quote** page, to refresh the prices on the individual quote line details to reflect this change. When you select **Recalculate**, a warning occurs that informs you that prices on quote line details for all quote lines on this quote will be reset. Select **Yes**, to refresh prices for both sales and cost quote line details.

## Access quote line details for cost

On the **Quote Line Details** tab, select a row in the grid to enable some actions on the toolbar of the subgrid. The first action on the subgrid tool bar when a quote line detail is selected is **Open Cost Detail**. Select **Open Cost Detail** to see the related cost rate and amount for this quote line.

> [!NOTE]
> Changing the resourcing unit, quantity, dates, role, or category values on the quote line detail for cost will change the corresponding values on the quote line details for sales.
## Currency on quote line details for cost and sales

Currency on the quote line detail for sales defaults from the project price list that is effective for the start date of the quote line detail.

Currency on the quote line detail for cost defaults from the price list of the contracting unit of the quote that is effective for the start date of the quote line detail for cost.

Profitability calculations convert the amount on quote line details for cost and sales into the base currency of the environment to report the overall estimated margin on the quote.

This could result in currency rounding errors and changing margins because of the lack of date effective exchange rates. Use these calculations on Project quotes only as approximations and not actual statutory or other reporting that requires higher precision of rounding and awareness of date effectivity for exchange rates.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
