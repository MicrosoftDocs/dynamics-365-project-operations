---
title: Estimating a project–based contract line
description:  This topic provides information about estimating a project–based contract line.
author: rumant
manager: Annbe
ms.date: 10/27/2020
ms.topic: article
ms.service: dynamics-365-customerservice
ms.reviewer: kfend 
ms.author: rumant
---

# Estimating a project–based contract line

_**Applies To:** Lite deployment - deal to proforma invoicing_

In Dynamics 365 Project Operations, a project-based contract line has details that help estimate the cost and potential revenue of the work involved to deliver the contract line.

To estimate a project-based contract line, go to the **Contract Line Detail** tab on the project-based **Contract Line**.  There are two ways to create an estimate on a project-based contract line:

   - Create an estimate directly on the contract line by manually adding contract line details.
   - Create a project and a project plan, and then associate the project and tasks to the project's contract line. This enables the process by which you can import the project plan estimate into the contract line based on the components included on the contract line.

## Create an estimation directly on a project–based contract line

1. Go to the contract line and select the **Contract Line Detail** tab. The lines you create on this tab are summarized and display as the **Contracted Value** for this **Contract Line**. 
2. In the **Contract Line Details** subgrid, select **+ New Contract Line Detail**. A quick-create slider opens. The following fields are available on the **Contract Line Details** form:

| Field | Location | Relevance, purpose, and guidance | Downstream impact |
| --- | --- | --- | --- |
| **Description** | **Quick Create** | A description of the specific estimate. | This field defaults to the related contract line detail for costs that are automatically created. |
| **Transaction Class** | **Quick Create** | This drop-down is a list of transaction classes included on the **General** tab of the project-based contract line. | This field defaults to the related contract line detail for costs that are automatically created. |
| **Role** | **Quick Create** | The role of the person who is performing this work or incurring this expense. | This field defaults to the related contract line detail for costs that are automatically created. |
| **Category** | **Quick Create** | The category of the work or expense. | This field defaults to the related contract line detail for costs that are automatically created. |
| **Start Date** | **Quick Create** | The start date of the work. | This field defaults to the related contract line detail for costs that are automatically created. |
| **End Date** | **Quick Create** | The end date of the work. | This field defaults to the related contract line detail for the cost that is automatically created. |
| **Resourcing Unit** | **Quick Create** | The resourcing unit that incurs this cost and provies the resource to work on it. | This field defaults to the related contract line detail for costs that are automatically created. This field is also used in cost price retrieval. |
| **Unit schedule** | **Quick create** | The unit group of the work or expense. Units belong to a unit schedule or a group of units. For example, *miles* and *kilometers (Kms)* are units that belong to a group of units that describe distance. | This field defaults to the related contract line detail for costs that are automatically created. |
| **Unit** | **Quick Create** | The unit of work or expense. | This field defaults to the related contract line detail for costs that are automatically created. |
| **Quantity** | **Quick Create** | The quantity of work or expense. | This field defaults to the related contract line detail for costs that are automatically created. |
| **Unit price** | **Quick Create** | The bill rate of the role that is performing the work or the sales price of the expense category. This field defaults for **Time** based on the role and resourcing unit combination on the project price list that is effective for the start date. For expenses, this field's default is from the price setup for the transaction category in the project price list that is effective for the start date. If the pricing method for the transaction category is not **price-per-unit**, there is no default, and this field is left blank. | The cost rate of the role that is performing the work, or the cost per unit of the expense category. This field defaults for **Time based on the role** and the resourcing unit combination on the role price line of the cost price list attached to the contracting unit effective for the start date. For expenses, this field's default is based on the category price line of the cost price list attached to the contracting unit that is effective for the start date. If the pricing method for the transaction category is not price-per-unit, there is no default and this field is left blank. |
| **Estimated Tax** | **Quick Create** | The estimated tax for this work or expense as input by the user. | The estimated tax for this work or expense as input by the user. |
| **Amount** | **Quick Create** | This value in this field can be added by the user if the **Quantity** and **Price** fields are left blank. If **Quantity** and **Price** are filled, the **Amount** field is read-only and is calculated as **(Quantity \* Unit price) + Tax**. | &nbsp; |

## Update prices on contract line details

If you change prices on the project price list that is attached to the contract or the cost price list of the contracting unit, you can refresh the prices on the individual contract line details to reflect the change. On the **Contract** page, select **Recalculate**. A warning opens to inform you that prices for all contract lines on this contract are reset. Select **Yes** to refresh prices for both sales and cost contract line details.

## Access contract line details for cost

On the **Contract Line Details** tab, select a row in the grid to display actions on the toolbar of the subgrid. The first action on the subgrid tool bar is **Open Cost Detail**. To see the related cost rate and amount for this contract line detail, select **Open Cost Detail**. 

> [!NOTE]
> Changing the resourcing company, resourcing unit, quantity, dates, role, or category values on the contract line detail for **Cost** also changes the corresponding values on the contract line detail for **Sales**.

## Currency on contract line details for cost and sales

The contract line detail for **Sales** sets the default currency from the project price list that is effective for the start date of the contract line detail.

The contract line detail for **Cost** sets the default currency from the price list of the contracting unit of the contract that is effective for the start date of the contract line detail for **Cost**.

Profitability calculations convert the amounts for the contract line details for **Cost** and **Sales** into the base currency of the environment to report the overall actual and estimated margins on the contract.

> [!NOTE]
> Currency rounding errors and changed margins could occur because of the lack of date effective exchange rates. Use these calculations on project contracts only as approximations and not for actual statutory or other reporting that requires higher precision of rounding and awareness of date effectivity for exchange rates.
