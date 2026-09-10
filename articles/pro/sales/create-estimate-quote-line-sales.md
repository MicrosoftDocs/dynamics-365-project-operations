---
title: Estimate a project quote line
description: This article provides information about how to create an estimate on a project quote line.
author: poojafandan
ms.date: 09/08/2026
ms.topic: how-to
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak
ms.author: poojafandan
---

# Estimate a project quote line

[!INCLUDE [banner](../../includes/banner.md)]

_**Applies To:** Project Operations Core, Project Operations Integrated with ERP_

A project-based quote line has details that help with estimating the cost and potential revenue of the work involved to deliver the quote line.

To estimate a project-based quote line, on the project-based quote line, select the **Quote Line Detail** tab. There are two ways to create an estimate on a project-based quote line:

- Manually create the estimate directly on the quote line using quote line details. 
- Create a project and a project plan, and then associate the project and tasks on the project to the quote line. The process to import the estimates on the project plan into the quote line based on the information you provided is enabled.

## Create estimates directly on a project quote line

To create an estimate on a project-based quote line, select the **Quote Line Detail** tab. The line item that you create on this tab summarize the quoted value for this quote line. 

To create quote line details, select **New quote line detail** on the **Quote Line Details** subgrid. A quick create slider opens. The following table provides details about the fields on the **Quote Line Detail** page and how the values impact the functionality.

| **Field** | **Location** | **Description** | **Downstream impact** |
| --- | --- | --- | --- |
| Description | Quick create | A description of the specific estimate. | This value defaults to the related quote line detail for cost that is automatically created. |
| Transaction Class | Quick create | This drop-down list provides the transaction classes that are included on the **General** tab of the project-based quote line.  | This value defaults to the related quote line detail for cost that is automatically created. |
| Select Product | Quick create | Applies when the transaction class is **Material**. You can select to specify that this estimate line is for an **Existing** (catalog) product or a **Write In** product. | This value defaults to the related quote line detail for cost that is automatically created. |
| Product | Quick create | The ID of the product from the product catalog. This field is only enabled if you select **Existing** in the **Select Product** field. The ID is used to retrieve the sales price from the project price list on the quote. | This value defaults to the related quote line detail for cost that is automatically created. |
| Write In Product | Quick create | A text box to write in the name of the product. This field is only enabled if you select **Write In** in the **Select Product** field.| This value defaults to the related quote line detail for cost that is automatically created. |
| Role | Quick create | The role of the person that performs this work or incur this expense. | This value defaults to the related quote line detail for cost that is automatically created. |
| Category | Quick create | The category of the work or expense. | This value defaults to the related quote line detail for cost that is automatically created. |
| Start Date | Quick create | The start date of the work. | This field defaults to the quote line detail for cost that is automatically created. |
| End Date | Quick create | The end date of the work. | This field defaults to the quote line detail for cost that is automatically created. |
| Resourcing Unit | Quick create | The resourcing unit that incurs this cost and provide the resource to work on it. | This value defaults to the related quote line detail for cost that is automatically created and used in the cost price retrieval. |
| Unit schedule | Quick create | The unit group of the work, product, or expense. Units belong to a unit schedule or a group of units. For example, miles and kilometers are units that belong to a group of units that describes distance. | This value defaults to the related quote line detail for cost that is automatically created. |
| Unit | Quick create | The unit of the work, product, or expense. | This value defaults to the related quote line detail for cost that is automatically created. |
| Quantity | Quick create | The quantity of work, product, or expense. | This value defaults to the related quote line detail for cost that is automatically created. |
| Unit price | Quick Create |The bill rate of the role that is performing the work, the unit price of the product, or the sales price of the product or expense category. The  default for this field is **Time** based on the combination of the pricing dimension values on the role price line of the project price list that is effective for the start date. For **Expenses**, the default is from the price setup for the transaction category in the project price list that is effective for the start date. If the pricing method for the transaction category isn't price-per-unit, there's no default, and this field is left blank. For products, the default is based on the **Price list item**  line in the project price list that is effective for the start date.| The cost rate of the role that is performing the work, the cost per unit of the expense category, or the unit cost of the product. The default for this field is **Time** based on the combination of the pricing dimension values on the role price line of the project price list that is effective for the start date. For **Expenses**, the default is from the price setup for the transaction category in the project price list that is effective for the start date. If the pricing method for the transaction category isn't price-per-unit, there's no default, and this field is left blank. For products, the default is based on the **Price list item**  line in the project price list that is effective for the start date.|
| Estimated Tax | Quick create | You can manually enter the estimated tax for this work or expense. | There's no downstream impact for this field. |
| Amount | Quick create | You can manually input information into this field if the **Quantity** and **Price** fields are left blank. If these fields aren't blank, this field becomes read only and is calculated as (Quantity \* Unit price) + Tax. | There's no downstream impact for this field. |

## Access quote line details for sales and cost prices

The **Line Detail** tab provides two form views to help you analyze sales and cost details:

- Line details
- Line details: Cost

### Line details

The **Line details** view displays each quote line detail along with its associated sales price. Within the subgrid of each quote line detail, you can see time-phased sales prices broken down by specific periods.

Selecting a quote line detail enables more actions on the toolbar. The first action available is **Open cost detail**. If you want to view the cost details of the Quote line detail in an expanded view, select **Open cost detail** and view the related cost rate and amount for the selected quote line detail.

### Line details: Cost

The **Line details: Cost** view provides insight into the cost price associated with each quote line detail. Similar to the **Line details** view, the subgrid displays time-phased cost prices.

These views enhance visibility into both sales and cost prices, making it easier to assess pricing details for each quote line.


> [!NOTE]
> When you change the resourcing unit, quantity, dates, role, or category values on the quote line, detail for cost will change the corresponding values on the quote line details for sales.

## Currency on quote line details for cost and sales

Currency on the quote line detail for sales defaults from the project price list that is effective for the start date of the quote line detail.

Currency on the quote line detail for cost defaults from the price list of the contracting unit of the quote that is effective for the start date of the quote line detail for cost.

Profitability calculations convert the amount on quote line details for cost and sales into the base currency of the environment to report the overall estimated margin on the quote.

> [!NOTE]
> Currency rounding errors and changed margins could occur because of the lack of date effective exchange rates. Use these calculations only on project contracts because these are approximations and aren't intended for actual statutory or other reporting that requires higher precision of rounding and awareness of date effectivity for exchange rates.

## View time-phased estimates

Time phasing of estimates in Microsoft Dynamics 365 Project Operations shows how the quantity, price, and amount of a project quote line detail are distributed over time. Use the time-phased view to review when work is expected to occur, understand price changes across the quote schedule, and adjust estimated quantities at the level where the work is planned.

The enhanced experience displays time-phased values as vertical period columns next to the quote line details. You can compare the parent estimate with its weekly, monthly, or custom time-phased breakdown in the same grid.

> [!NOTE]
> The time-phased view is available when the **Time Phasing of Estimates** feature is enabled. Contact your administrator if you don't see the time-phased columns.

To open the time-phased view:

1. In Project Operations, go to **Sales** > **Quotes**.
1. Open a project quote.
1. Select the **Line details** tab (or select Line Details tab on Quote Line form)
1. Locate the project quote line details that you want to review.

The standard quote line detail fields remain on the left side of the grid. Depending on the transaction class, these fields can include the role, start date, end date, quantity, unit, average price, tax, and amount.

Time periods appear as columns to the right of the standard fields. Each period can show:

| Value | Description |
|-------|-------------|
| **Quantity** | The portion of the quote line detail quantity assigned to the period. |
| **Price** | The sales price that applies to the period. |
| **Amount** | The estimated sales amount for the period. |

The parent quote line detail shows the total quantity, weighted average price, and total amount across all periods. Group and quote line rows show summarized values so that you can compare totals without expanding every detail.

## Navigate the estimate timeline

Use the controls above the time-phased columns to choose which part of the estimate schedule appears in the grid.

- Use the date range control to select the time span that you want to review.
- Use the previous and next controls to move backward or forward through the estimate timeline.
- Use the interval selector to change how dates are grouped.

The period headers update when you change the date range or interval. The standard quote line detail fields remain visible while you move through time-phased periods.

## Select a time interval

Choose an interval based on the level of detail that you need:

| Interval | Use it to |
|----------|-----------|
| **Weekly** | Review quantities, prices, and amounts week by week. |
| **Monthly** | Review summarized values for each month. |
| **Custom** | Define an interval that matches your planning or reporting needs. |

A weekly interval provides more detail for short-term planning and date-effective price changes. A monthly interval provides a more summarized view for longer estimates. Use a custom interval when the standard periods don't match the way that you plan the work.

Changing the interval changes how the values are grouped for display. It doesn't change the total quantity or amount of the parent quote line detail.

## Choose the values to display

Use the **Columns** menu to control which time-phased values appear for each period. You can show quantity, price, amount, or a combination of these values.

For example:

- Show **Quantity** when you want to plan effort or units across periods.
- Show **Price** when you want to review date-effective rates or price overrides.
- Show **Amount** when you want to compare the estimated financial value by period.

Reducing the number of displayed values can make it easier to compare a larger number of periods on the screen.

## Update the parent quantity

You can edit the quantity directly on the parent quote line detail.

1. Locate the quote line detail in the grid.
1. Select its parent **Quantity** cell.
1. Enter the new total quantity.
1. Save your changes.

Project Operations updates the time-phased breakdown and recalculates the parent price and amount. Review the period columns after the update to confirm that the quantity is distributed as expected.

## Update a time-phased quantity

You can also update the quantity in an individual time period. This capability lets you adjust when work is expected to occur without editing the entire quote line detail.

1. Locate the quote line detail and the period that you want to change.
1. In that period, select the **Quantity** cell.
1. Enter the new quantity.
1. Save your changes.

Project Operations updates the parent quantity to reflect the total of the time-phased quantities. It also recalculates the affected period amounts and the totals on the parent quote line detail.

Use period-level editing when effort or units need to move between weeks, months, or custom periods. After editing, confirm that the parent total and the quantities across all periods represent the complete estimate.

## Understand time-phased prices

Time-phased prices show which sales price applies during each period of the quote line detail. Prices can vary over time because of date-effective price lists or role price overrides.

Each period uses the applicable price for that period. The parent quote line detail displays the weighted average of the time-phased prices based on the quantities in each period. Therefore, changing a time-phased quantity can also change the weighted average price on the parent line.

For example, a quote line detail can use one role price during the first part of the schedule and a different price after a date-effective price change. The period columns show each applicable price, while the parent line shows the weighted average price for the full estimate.

If you apply a role price override to a quote line detail, the override is reflected in the applicable time-phased periods. For more information about price overrides, see the price override guidance for the Quote and Quote Line forms.

## Review sales and cost details

The time-phased grid displays sales values for quote line details. To review the corresponding cost information, select a quote line detail, and then select **Open cost detail**.

The cost detail shows the cost rate and amount associated with the selected sales quote line detail. Use the sales and cost views together to understand how quantities and price changes affect the expected margin.

When you change values such as the resourcing unit, quantity, dates, role, or category, Project Operations updates the corresponding sales and cost details according to the applicable pricing setup.

## Example

A quote line detail contains 40 hours of work across four weeks. The first two weeks use a sales price of $100 per hour, and the last two weeks use a date-effective price of $120 per hour.

In the weekly view:

- Each week appears as a separate period column.
- The **Quantity** value shows the hours planned for that week.
- The **Price** value shows either $100 or $120, based on the applicable price.
- The **Amount** value shows the estimated sales value for the week.
- The parent quote line detail shows 40 hours, the weighted average price, and the total amount.

If you move hours from a $100 period to a $120 period, Project Operations recalculates the period amounts, total amount, and weighted average price.

## Related content

- [Estimate a project quote line](https://learn.microsoft.com/dynamics365/project-operations/pro/sales/create-estimate-quote-line-sales)
- [Manage project price lists on project quotes](https://learn.microsoft.com/dynamics365/project-operations/pro/sales/manage-project-price-lists-sales)
- [Modern Quote experience](quotes-new-form.md)


## Update prices on quote line details

If you change prices on the project price list that is attached to the quote, or on the cost price list of the contracting unit, select **Recalculate** on the **Quote** page to refresh the prices on the individual quote line details to reflect this change. When you select **Recalculate**, a warning appears that informs you that prices on quote line details for all quote lines on this quote will be reset. Select **Yes** to refresh prices for both sales and cost quote line details.

## Time phasing of prices
The Time phasing of prices feature provides visibility into price fluctuations over time within Project quote lines. Nested quote line details display price changes phased out on a weekly basis, so you can track adjustments due to price overrides or multiple price lists. Throughout the duration of a quote line detail, the system distributes the quantities and prices for each week, making it easier to identify pricing adjustments. The parent quote line detail reflects the weighted average price of all child time-phased lines.
You can create role price overrides on a quote line detail that is then reflected in the nested time-phased lines. Each week in the nested Quote Line detail line retains the price applicable on the first day of that week.

On the **Quote line details** tab, select a row in the grid to enable some actions on the toolbar of the subgrid. The first action on the subgrid tool bar when a quote line detail is selected is **Open cost detail**. Select **Open cost detail** to see the related cost rate and amount for this quote line.

### Example scenario

A quote line detail spans a total of seven weeks from January 1, 2025, to February 15, 2025. The role price is set at $200, but a price override of $250 is applied on February 5, 2025.

| **Attribute** | **Value** |
| --- | --- |
| Start Date |January 1, 2025 |
| End Date | February 15, 2025 |
| Quantity | 350 hours |
| Role Price | $200 |
| Price Override Date | February 5, 2025 |
| Price Override | $250 |

- Until the sixth week (starting February 3, 2025), the price remains $200.
- In the seventh week (starting February 10, 2025), the price updates to $250 reflecting the override.
- The parent quote line detail displays the weighted average price, calculated as $206.52.

You can adjust the quantity at either the parent quote line detail or the nested lines, and the system updates the price accordingly. Selecting the **Refresh** button ensures the correct price is displayed.
This feature enables you to accurately track and manage pricing changes, improving transparency and control over quote calculations.



[!INCLUDE[footer-include](../../includes/footer-banner.md)]
