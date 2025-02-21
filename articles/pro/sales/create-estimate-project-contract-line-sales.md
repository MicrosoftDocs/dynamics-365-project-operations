---
title: Estimate a project contract line
description:  This article provides information about estimating a project–based contract line.
author: poojafandan
ms.author: poojafandan
ms.date: 2/21/2025
ms.topic: how-to
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak

---

# Estimate a project contract line

[!INCLUDE[banner](../../includes/banner.md)]

_**Applies To:** Lite deployment - deal to proforma invoicing_

In Dynamics 365 Project Operations, a project contract line has details that help estimate the cost and potential revenue of the work involved to deliver the contract line.

To estimate a project contract line, go to the **Contract Line Detail** tab on the project-based **Contract Line**. There are two ways to create an estimate on a project-based contract line:

   - Create an estimate directly on the contract line by manually adding contract line details.
   - Create a project and a project plan, and then associate the project and tasks to the project's contract line. This association enables the process by which you can import the project plan estimate into the contract line based on the components included on the contract line.

## Create an estimation directly on a project–based contract line

To create an estimation directly on a project contract line, follow these steps:

1. Go to the contract line and select the **Contract Line Detail** tab. The lines you create on this tab are summarized and display as the **Contracted Value** for this **Contract Line**. 
2. In the **Contract Line Details** subgrid, select **New Contract Line Detail**. A quick-create slider opens. The following fields are available on the **Contract Line Details** page.

| Field | Location | Description | Downstream impact |
| --- | --- | --- | --- |
| **Description** | **Quick Create** | A description of the specific estimate. | This value defaults to the related contract line detail for cost that is automatically created. |
| **Transaction Class** | **Quick Create** | This list of transaction classes is on the **General** tab of the project-based contract line. | This value defaults to the related contract line detail for cost that is automatically created. |
| **Select Product** | **Quick create** | Applies when the transaction class is **Material**. You can specify if this estimate line is for an **Existing** (catalog) product or a **Write in** product. | This value defaults to the related contract line detail for cost that is automatically created. |
| **Product** | **Quick create** | The ID of the product from the product catalog. This field is only enabled when you select **Existing product** in the **Select Product** field. The ID is used to retrieve the sales price from the project price list on the contract. | This value defaults to the related contract line detail for the cost that is automatically created. |
| **WriteIn Product** | **Quick create** | A text field to enter the name of the product. This field is only enabled when you select **Write In** in the **Select Product** field.| This value defaults to the related contract line detail for cost that is automatically created. |
| **Role** | **Quick Create** | The role of the person who is performing this work or incurring this expense. | This value defaults to the related contract line detail for cost that is automatically created.|
| **Category** | **Quick Create** | The category of the work or expense. |This value defaults to the related contract line detail for cost that is automatically created.|
| **Start Date** | **Quick Create** | The start date of the work. | This value defaults to the related contract line detail for cost that is automatically created. |
| **End Date** | **Quick Create** | The end date of the work. | This value defaults to the related contract line detail for cost that is automatically created. |
| **Resourcing Unit** | **Quick Create** | The resourcing unit that incurs this cost and provides the resource to work on it. |This value defaults to the related contract line detail for cost that is automatically created and is used in cost price retrieval. |
| **Unit schedule** | **Quick create** | The unit group of the work, product, or expense. Units belong to a unit schedule or a group of units. For example, *miles* and *kilometers (kms)* are units that belong to a group of units that describe distance. | This value defaults to the related contract line detail for cost that is automatically created. |
| **Unit** | **Quick Create** | The unit of work, product, or expense. | This value defaults to the related contract line detail for cost that is automatically created. |
| **Quantity** | **Quick Create** | The quantity of work, product, or expense. | This value defaults to the related contract line detail for cost that is automatically created. |
| **Unit price** | **Quick Create** | The bill rate of the role that is performing the work, the unit price of the product, or the sales price of the product or expense category. This field defaults for **Time** based on the combination of pricing dimension values on the role price line of the project price list that is effective for the start date. For **Expenses**, this field's default is from the price setup for the transaction category in the project price list that is effective for the start date. If the pricing method for the transaction category isn't **price-per-unit**, there isn't a default, and this field is left blank. For products, this field's default is based on the **Price list item**  line in the project price list that is effective for the start date.| The cost rate of the role that is performing the work, or the cost per unit of the expense category or the unit cost of the product. This field defaults for **Time** based on the combination of pricing dimension values on the role price line of the cost price list attached to the contracting unit effective for the start date. For expenses, this field's default is based on the category price line of the cost price list attached to the contracting unit that is effective for the start date. If the pricing method for the transaction category isn't price-per-unit, there isn't a default, and this field is left blank. For products, this field's default is based on the **Price list item**  line of the cost price list attached to the contracting unit that is effective for the start date.|
| **Estimated Tax** | **Quick Create** | The estimated tax for this work or expense. | The estimated tax for this work or expense. |
| **Amount** | **Quick Create** | You can add the value in this field if the **Quantity** and **Price** fields are left blank. If **Quantity** and **Price** are filled, the **Amount** field is read only and is calculated as **(Quantity \* Unit price) + Tax**. | &nbsp; |

## Update prices on contract line details

If you change prices on the project price list that is attached to the contract or the cost price list of the contracting unit, you can refresh the prices on the individual contract line details to reflect the change. On the **Contract** page, select **Recalculate**. A warning appears to inform you that prices for all contract lines on this contract are reset. Select **Yes** to refresh prices for both sales and cost contract line details.


## Time Phasing of Estimates

> [!IMPORTANT] 
> Time phasing of estimates is available to targeted users as part of a preview release. The content and the functionality are subject to change. Learn more in [One version service updates FAQ](dynamics365/fin-ops-core/dev-itpro/get-started/one-version.md?context=%2Fdynamics365%2Fproject-operations%2Fcontext%2Fdev-itpro).
>
> After the Time phasing of sales estimates feature is enabled in an organization, it can't be disabled.

The Time Phasing of Estimates feature provides visibility into price fluctuations over time within Project Contract Lines. Nested contract line details display price changes phased out on a weekly basis, allowing you to track adjustments due to price overrides or multiple price lists. Throughout the duration of a contract line detail, the system distributes the quantities and prices for each week, making it easier to identify pricing adjustments. The parent contract line detail reflects the weighted average price of all child time-phased lines.
You can create role price overrides scoped to a contract that is reflected in the nested time-phased lines. Each week in the nested contract line detail line retains the price applicable on the first day of that week.

On the **Contract Line Details** tab, select a row in the grid to enable some actions on the toolbar of the subgrid. The first action on the subgrid tool bar when a contract line detail is selected is **Open Cost Detail**. Select **Open Cost Detail** to see the related cost rate and amount for this contract line detail.
**Example Scenario:**

A contract line detail spans from January 1, 2025, to February 15, 2025, covering a total of seven weeks. The role price is set at $200, but a price override of $250 is applied on February 5, 2025.
| **Attribute** | **Value** |
| --- | --- |
| Start Date |January 1,2025 |
| End Date | February 15,2025 |
| Quantity | 350 hours |
| Role Price | $200 |
| Price Override Date | Feb 5th,2025 |
| Price Override | $250 |

•	Until the sixth week (starting February 3, 2025), the price remains $200.

•	In the seventh week (starting February 10, 2025), the price updates to $250, reflecting the override.

•	The parent Contract Line Detail displays the weighted average price, calculated as $206.52.

You can adjust the quantity at either the parent contract line detail or the nested lines, and the system updates the price accordingly. Selecting the **Refresh** button ensures the correct price is displayed.

This feature enables you to accurately track and manage pricing changes, improving transparency and control over contract estimation calculations.

## Access contract line details for sales and cost prices


The **Contract Line Detail** tab provides two form views to help you analyze sales and cost details:

•	Line Details

•	Line Details: Cost

**Line Details**
The Line Details view displays each contract line detail along with its associated sales price. Within the subgrid of each contract line detail, you can see time-phased sales prices broken down by specific periods.

Selecting a contract line detail enables more actions on the toolbar. The first action available is Open Cost Detail. If you want to view the cost details of the contract line detail in an expanded view, click Open Cost Detail and view the related cost rate and amount for the selected contract line detail.

**Line Details: Cost**
The Line Details: Cost view provides insight into the cost price associated with each contract line detail. Like the **Line Details** view, the subgrid displays time-phased cost prices.

These views enhance visibility into both sales and cost prices, making it easier to assess pricing details for each contract line.


> [!NOTE]
> When you change the resourcing company, resourcing unit, quantity, dates, role, or category values on the contract line detail for **Cost**, the corresponding values on the contract line detail for **Sales** also change.

## Currency on contract line details for cost and sales

The contract line detail for **Sales** sets the default currency from the project price list that is effective for the start date of the contract line detail.

The contract line detail for **Cost** sets the default currency from the price list of the contracting unit of the contract that is effective for the start date of the contract line detail for **Cost**.

Profitability calculations convert the amounts for the contract line details for **Cost** and **Sales** into the base currency of the environment to report the overall actual and estimated margins on the contract.

> [!NOTE]
> Currency rounding errors and changed margins could occur because of the lack of date effective exchange rates. Use these calculations only on project contracts because they're approximations and aren't for actual statutory or other reporting that requires higher precision of rounding and awareness of date effectivity for exchange rates.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
