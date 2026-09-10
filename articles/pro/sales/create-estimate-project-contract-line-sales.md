---
title: Estimate a project contract line
description:  This article provides information about estimating a project–based contract line.
author: poojafandan
ms.author: poojafandan
ms.date: 09/10/2026
ms.topic: how-to
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak

---

# Estimate a project contract line

[!INCLUDE [banner](../../includes/banner.md)]

_**Applies To:** Project Operations Core_

In Dynamics 365 Project Operations, a project contract line includes details that help you estimate the cost and potential revenue for delivering the contract line.

To estimate a project contract line, go to the **Contract Line Detail** tab on the project-based **Contract Line**. You can create an estimate on a project-based contract line in two ways:

- Create an estimate directly on the contract line by manually adding contract line details.
- Create a project and a project plan, and then associate the project and tasks to the project's contract line. This association enables the process by which you can import the project plan estimate into the contract line based on the components included on the contract line.

## Create an estimate directly on a project-based contract line

To create an estimate directly on a project contract line, follow these steps:

1. Go to the contract line and select the **Contract Line Detail** tab. The lines you create on this tab are summarized and display as the **Contracted Value** for this **Contract Line**.
1. In the **Contract Line Details** subgrid, select **New Contract Line Detail**. A quick-create slider opens. The following fields are available on the **Contract Line Details** page.

| Field | Location | Description | Downstream impact |
| --- | --- | --- | --- |
| **Description** | **Quick Create** | A description of the specific estimate. | This value defaults to the related contract line detail for cost that is automatically created. |
| **Transaction Class** | **Quick Create** | This list of transaction classes is on the **General** tab of the project-based contract line. | This value defaults to the related contract line detail for cost that is automatically created. |
| **Select Product** | **Quick create** | Applies when the transaction class is **Material**. You can specify if this estimate line is for an **Existing** (catalog) product or a **Write in** product. | This value defaults to the related contract line detail for cost that is automatically created. |
| **Product** | **Quick create** | The ID of the product from the product catalog. This field is only enabled when you select **Existing product** in the **Select Product** field. The ID is used to retrieve the sales price from the project price list on the contract. | This value defaults to the related contract line detail for the cost that is automatically created. |
| **WriteIn Product** | **Quick create** | A text field to enter the name of the product. This field is only enabled when you select **Write In** in the **Select Product** field. | This value defaults to the related contract line detail for cost that is automatically created. |
| **Role** | **Quick Create** | The role of the person who is performing this work or incurring this expense. | This value defaults to the related contract line detail for cost that is automatically created. |
| **Category** | **Quick Create** | The category of the work or expense. | This value defaults to the related contract line detail for cost that is automatically created. |
| **Start Date** | **Quick Create** | The start date of the work. | This value defaults to the related contract line detail for cost that is automatically created. |
| **End Date** | **Quick Create** | The end date of the work. | This value defaults to the related contract line detail for cost that is automatically created. |
| **Resourcing Unit** | **Quick Create** | The resourcing unit that incurs this cost and provides the resource to work on it. | This value defaults to the related contract line detail for cost that is automatically created and is used in cost price retrieval. |
| **Unit schedule** | **Quick create** | The unit group of the work, product, or expense. Units belong to a unit schedule or a group of units. For example, _miles_ and _kilometers (kms)_ are units that belong to a group of units that describe distance. | This value defaults to the related contract line detail for cost that is automatically created. |
| **Unit** | **Quick Create** | The unit of work, product, or expense. | This value defaults to the related contract line detail for cost that is automatically created. |
| **Quantity** | **Quick Create** | The quantity of work, product, or expense. | This value defaults to the related contract line detail for cost that is automatically created. |
| **Unit price** | **Quick Create** | The bill rate of the role that is performing the work, the unit price of the product, or the sales price of the product or expense category. This field defaults for **Time** based on the combination of pricing dimension values on the role price line of the project price list that is effective for the start date. For **Expenses**, this field's default is from the price setup for the transaction category in the project price list that is effective for the start date. If the pricing method for the transaction category isn't **price-per-unit**, there isn't a default, and this field is left blank. For products, this field's default is based on the **Price list item**  line in the project price list that is effective for the start date. | The cost rate of the role that is performing the work, or the cost per unit of the expense category or the unit cost of the product. This field defaults for **Time** based on the combination of pricing dimension values on the role price line of the cost price list attached to the contracting unit effective for the start date. For expenses, this field's default is based on the category price line of the cost price list attached to the contracting unit that is effective for the start date. If the pricing method for the transaction category isn't price-per-unit, there isn't a default, and this field is left blank. For products, this field's default is based on the **Price list item**  line of the cost price list attached to the contracting unit that is effective for the start date. |
| **Estimated Tax** | **Quick Create** | The estimated tax for this work or expense. | The estimated tax for this work or expense. |
| **Amount** | **Quick Create** | You can add the value in this field if the **Quantity** and **Price** fields are left blank. If **Quantity** and **Price** are filled, the **Amount** field is read only and is calculated as **(Quantity \* Unit price) + Tax**. | &nbsp; |

## Access contract line details for sales and cost prices

The **Line Detail** tab provides two form views to help you analyze sales and cost details:

- Line details
- Line details: Cost

### Line details

The **Line details** view displays each contract line detail along with its associated sales price. Within the subgrid of each contract line detail, you can see time-phased sales prices broken down by specific periods.

Selecting a contract line detail enables more actions on the toolbar. The first action available is **Open cost detail**. To view the cost details of the contract line detail in an expanded view, select **Open cost detail** and view the related cost rate and amount for the selected contract line detail.

### Line details: Cost

The **Line details: Cost** view provides insight into the cost price associated with each contract line detail. Similar to the **Line details** view, the subgrid displays time-phased cost prices.

These views enhance visibility into both sales and cost prices, making it easier to assess pricing details for each contract line.

> [!NOTE]
> When you change the resourcing unit, quantity, dates, role, or category values on the contract line, detail for cost changes the corresponding values on the contract line details for sales.

## Currency on contract line details for cost and sales

The currency on the contract line detail for sales comes from the project price list that you set for the start date of the contract line detail. The currency on the contract line detail for cost comes from the price list of the contracting unit of the contract that you set for the start date of the contract line detail for cost. Profitability calculations convert the amount on contract line details for cost and sales into the base currency of the environment to report the overall estimated margin on the contract.

> [!NOTE]
> Currency rounding errors and changed margins can happen because of the lack of date effective exchange rates. Use these calculations only on project contracts because these calculations are approximations and aren't intended for actual statutory or other reporting that requires higher precision of rounding and awareness of date effectivity for exchange rates.

## Update prices on contract line details

If you change prices on the project price list that is attached to the contract or the cost price list of the contracting unit, you can refresh the prices on the individual contract line details to reflect the change. On the **Contract** page, select **Recalculate**. A warning appears to inform you that prices for all contract lines on this contract are reset. Select **Yes** to refresh prices for both sales and cost contract line details.

## View time-phased estimates

Time phasing of estimates in Project Operations shows how the quantity, price, and amount of a project contract line detail are distributed over time. Use the time-phased view to review when work is expected to occur, understand price changes across the contract schedule, and adjust estimated quantities at the level where the work is planned.

The enhanced experience displays time-phased values as vertical period columns next to the contract line details. You can compare the parent estimate with its weekly, monthly, or custom time-phased breakdown in the same grid.

> [!NOTE]
> The time-phased view is available when the **Time Phasing of Estimates** feature is enabled. Contact your administrator if you don't see the time-phased columns.

To open the time-phased view, follow these steps:

1. In Project Operations, go to **Sales** > **contracts**.
1. Open a project contract.
1. Select the **Line details** tab (or select Line Details tab on contract Line form)
1. Locate the project contract line details that you want to review.

The standard contract line detail fields remain on the left side of the grid. Depending on the transaction class, these fields can include the role, start date, end date, quantity, unit, average price, tax, and amount.

Time periods appear as columns to the right of the standard fields. Each period can show:

| Value | Description |
| ------- | ------------- |
| **Quantity** | The portion of the contract line detail quantity assigned to the period. |
| **Price** | The sales price that applies to the period. |
| **Amount** | The estimated sales amount for the period. |

The parent contract line detail shows the total quantity, weighted average price, and total amount across all periods. Group and contract line rows show summarized values so that you can compare totals without expanding every detail.

## Navigate the estimate timeline

Use the controls above the time-phased columns to choose which part of the estimate schedule appears in the grid.

- Use the date range control to select the time span that you want to review.
- Use the previous and next controls to move backward or forward through the estimate timeline.
- Use the interval selector to change how dates are grouped.

The period headers update when you change the date range or interval. The standard contract line detail fields remain visible while you move through time-phased periods.

## Select a time interval

Choose an interval based on the level of detail that you need:

| Interval | Use it to |
| ---------- | ----------- |
| **Weekly** | Review quantities, prices, and amounts week by week. |
| **Monthly** | Review summarized values for each month. |
| **Custom** | Define an interval that matches your planning or reporting needs. |

A weekly interval provides more detail for short-term planning and date-effective price changes. A monthly interval provides a more summarized view for longer estimates. Use a custom interval when the standard periods don't match the way that you plan the work.

Changing the interval changes how the values are grouped for display. It doesn't change the total quantity or amount of the parent contract line detail.

## Choose the values to display

Use the **Columns** menu to control which time-phased values appear for each period. You can show quantity, price, amount, or a combination of these values.

For example:

- Show **Quantity** when you want to plan effort or units across periods.
- Show **Price** when you want to review date-effective rates or price overrides.
- Show **Amount** when you want to compare the estimated financial value by period.

Reducing the number of displayed values can make it easier to compare a larger number of periods on the screen.

## Update the parent quantity

You can edit the quantity directly on the parent contract line detail.

To update the parent quantity, follow these steps:

1. Locate the contract line detail in the grid.
1. Select its parent **Quantity** cell.
1. Enter the new total quantity.
1. Save your changes.

Project Operations updates the time-phased breakdown and recalculates the parent price and amount. Review the period columns after the update to confirm that the quantity is distributed as expected.

## Update a time-phased quantity

You can also update the quantity for an individual time period. This capability lets you adjust when work is expected to occur without editing the entire contract line detail.

To update a time-phased quantity, follow these steps:

1. Locate the contract line detail and the period that you want to change.
1. In that period, select the **Quantity** cell.
1. Enter the new quantity.
1. Save your changes.

Project Operations updates the parent quantity to reflect the total of the time-phased quantities. It also recalculates the affected period amounts and the totals on the parent contract line detail.

Use period-level editing when effort or units need to move between weeks, months, or custom periods. After editing, confirm that the parent total and the quantities across all periods represent the complete estimate.

## Understand time-phased prices

Time-phased prices show which sales price applies during each period of the contract line detail. Prices can vary over time because of date-effective price lists or role price overrides.

Each period uses the applicable price for that period. The parent contract line detail displays the weighted average of the time-phased prices based on the quantities in each period. Therefore, changing a time-phased quantity can also change the weighted average price on the parent line.

For example, a contract line detail can use one role price during the first part of the schedule and a different price after a date-effective price change. The period columns show each applicable price, while the parent line shows the weighted average price for the full estimate.

If you apply a role price override to a contract line detail, the override is reflected in the applicable time-phased periods. For more information about price overrides, see the price override guidance for the contract and contract line forms.

## Review sales and cost details

The time-phased grid displays sales values for contract line details. To review the corresponding cost information, select a contract line detail, and then select **Open cost detail**.

The cost detail shows the cost rate and amount associated with the selected sales contract line detail. Use the sales and cost views together to understand how quantities and price changes affect the expected margin.

When you change values such as the resourcing unit, quantity, dates, role, or category, Project Operations updates the corresponding sales and cost details according to the applicable pricing setup.

## Example

A contract line detail contains 40 hours of work across four weeks. The first two weeks use a sales price of $100 per hour, and the last two weeks use a date-effective price of $120 per hour.

In the weekly view:

- Each week appears as a separate period column.
- The **Quantity** value shows the hours planned for that week.
- The **Price** value shows either $100 or $120, based on the applicable price.
- The **Amount** value shows the estimated sales value for the week.
- The parent contract line detail shows 40 hours, the weighted average price, and the total amount.

If you move hours from a $100 period to a $120 period, Project Operations recalculates the period amounts, total amount, and weighted average price.

## Additional information

- [Estimate a project contract line](create-estimate-project-contract-line-sales.md)
- [Manage project price lists on project contracts](manage-project-price-lists-sales.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
