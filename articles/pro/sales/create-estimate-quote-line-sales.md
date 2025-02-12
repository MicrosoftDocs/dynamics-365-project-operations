---
title: Estimate a project quote line
description: This article provides information about how to create an estimate on a project quote line.
author: poojafandan
ms.date: 06/07/2024
ms.topic: how-to
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak
ms.author: poojafandan
---

# Estimate a project quote line

[!INCLUDE[banner](../../includes/banner.md)]

_**Applies To:** Lite deployment - deal to proforma invoicing, Project Operations for resource/non-stocked based scenarios_

A project-based quote line has details that help with estimating the cost and potential revenue of the work involved to deliver the quote line.

To estimate a project-based quote line, on the project-based quote line, select the **Quote Line Detail** tab. There are two ways to create an estimate on a project-based quote line:

- Manually create the estimate directly on the quote line using quote line details. 
- Create a project and a project plan, and then associate the project and tasks on the project to the quote line. The process to import the estimates on the project plan into the quote line based on the information you provided will be enabled.

## Create estimates directly on a project quote line

To create an estimate on a project-based quote line, select the **Quote Line Detail** tab. The line item that you create on this tab will summarize the quoted value for this quote line. 

To create quote line details, select **New quote line detail** on the **Quote Line Details** subgrid. A quick create slider will open. The following table provides details about the fields on the **Quote Line Detail** page and how the values impact the functionality.

| **Field** | **Location** | **Description** | **Downstream impact** |
| --- | --- | --- | --- |
| Description | Quick create | A description of the specific estimate. | This value defaults to the related quote line detail for cost that is automatically created. |
| Transaction Class | Quick create | This drop-down list provides the transaction classes that are included on the **General** tab of the project-based quote line.  | This value defaults to the related quote line detail for cost that is automatically created. |
| Select Product | Quick create | Applies when the transaction class is **Material**. You can select to specify that this estimate line is for an **Existing** (catalog) product or a **Write In** product. | This value defaults to the related quote line detail for cost that is automatically created. |
| Product | Quick create | The ID of the product from the product catalog. This field is only enabled if you select **Existing** in the **Select Product** field. The ID is used to retrieve the sales price from the project price list on the quote. | This value defaults to the related quote line detail for cost that is automatically created. |
| Write In Product | Quick create | A text box to write in the name of the product. This field is only enabled if you select **Write In** in the **Select Product** field.| This value defaults to the related quote line detail for cost that is automatically created. |
| Role | Quick create | The role of the person that will perform this work or incur this expense. | This value defaults to the related quote line detail for cost that is automatically created. |
| Category | Quick create | The category of the work or expense. | This value defaults to the related quote line detail for cost that is automatically created. |
| Start Date | Quick create | The start date of the work. | This field defaults to the quote line detail for cost that is automatically created. |
| End Date | Quick create | The end date of the work. | This field defaults to the quote line detail for cost that is automatically created. |
| Resourcing Unit | Quick create | The resourcing unit that will incur this cost and provide the resource to work on it. | This value defaults to the related quote line detail for cost that is automatically created and used in the cost price retrieval. |
| Unit schedule | Quick create | The unit group of the work, product, or expense. Units belong to a unit schedule or a group of units. For example, miles and kilometers are units that belong to a group of units that describes distance. | This value defaults to the related quote line detail for cost that is automatically created. |
| Unit | Quick create | The unit of the work, product, or expense. | This value defaults to the related quote line detail for cost that is automatically created. |
| Quantity | Quick create | The quantity of work, product, or expense. | This value defaults to the related quote line detail for cost that is automatically created. |
| Unit price | Quick Create |The bill rate of the role that is performing the work, the unit price of the product, or the sales price of the product or expense category. The  default for this field is **Time** based on the combination of the pricing dimension values on the role price line of the project price list that is effective for the start date. For **Expenses**, the default is from the price setup for the transaction category in the project price list that is effective for the start date. If the pricing method for the transaction category isn't price-per-unit, there is no default, and this field is left blank. For products, the default is based on the **Price list item**  line in the project price list that is effective for the start date.| The cost rate of the role that is performing the work, the cost per unit of the expense category, or the unit cost of the product. The default for this field is **Time** based on the combination of the pricing dimension values on the role price line of the project price list that is effective for the start date. For **Expenses**, the default is from the price setup for the transaction category in the project price list that is effective for the start date. If the pricing method for the transaction category isn't price-per-unit, there is no default, and this field is left blank. For products, the default is based on the **Price list item**  line in the project price list that is effective for the start date.|
| Estimated Tax | Quick create | You can manually enter the estimated tax for this work or expense. | There is no downstream impact for this field. |
| Amount | Quick create | You can manually input information into this field if the **Quantity** and **Price** fields are left blank. If these fields are not blank, this field becomes read only and is calculated as (Quantity \* Unit price) + Tax. | There is no downstream impact for this field. |


## Update prices on quote line details

If you have changed prices on the project price list that is attached to the quote, or on the cost price list of the contracting unit, you can select **Recalculate** on the **Quote** page to refresh the prices on the individual quote line details to reflect this change. When you select **Recalculate**, a warning appears that informs you that prices on quote line details for all quote lines on this quote will be reset. Select **Yes** to refresh prices for both sales and cost quote line details.

## Time Phasing of Prices
The Time Phasing of Prices feature provides visibility into price fluctuations over time within Project Quote Lines. Nested quote line details display price changes phased out on a weekly basis, allowing you to track adjustments due to price overrides or multiple price lists. Throughout the duration of a quote line detail, the system distributes the quantities and prices for each week, making it easier to identify pricing adjustments. The parent quote line detail reflects the weighted average price of all child time-phased lines.
You can create role price overrides on a quote line detail, which are then reflected in the nested time-phased lines. Each week in the nested Quote Line detail line retains the price applicable on the first day of that week.

On the **Quote Line Details** tab, select a row in the grid to enable some actions on the toolbar of the subgrid. The first action on the subgrid tool bar when a quote line detail is selected is **Open Cost Detail**. Select **Open Cost Detail** to see the related cost rate and amount for this quote line.
**Example Scenario:**

A quote line detail spans from January 1, 2025, to February 15, 2025, covering a total of seven weeks. The role price is set at $200, but a price override of $250 is applied on February 5, 2025.
| **Attribute** | **Value** |
| --- | --- |
| Start Date |Jan 1st,2025 |
| End Date | Feb 15th,2025 |
| Quantity | 350 hours |
| Role Price | $200 |
| Price Override Date | Feb 5th,2025 |
| Price Override | $250 |

•	Until the sixth week (starting February 3, 2025), the price remains $200.

•	In the seventh week (starting February 10, 2025), the price updates to $250, reflecting the override.

•	The parent Quote Line Detail displays the weighted average price, calculated as $206.52.

You can adjust the quantity at either the parent quote line detail or the nested lines, and the system updates the price accordingly. Clicking the "Refresh" button ensures the correct price is displayed.
This feature enables you to accurately track and manage pricing changes, improving transparency and control over quote calculations.



## Access quote line details for sales and cost prices

The **Quote Line Detail** tab provides two form views to help you analyze sales and cost details:

•	Line Details

•	Line Details: Cost

**Line Details**
The Line Details view displays each quote line detail along with its associated sales price. Within the subgrid of each quote line detail, you can see time-phased sales prices broken down by specific periods.

Selecting a quote line detail enables additional actions on the toolbar. The first action available is Open Cost Detail. If you want to view the cost details of the Quote line detail in an expanded view, click Open Cost Detail and view the related cost rate and amount for the selected quote line detail.

**Line Details: Cost**
The Line Details: Cost view provides insight into the cost price associated with each quote line detail. Similar to the Line Details view, the subgrid displays time-phased cost prices.

These views enhance visibility into both sales and cost prices, making it easier to assess pricing details for each quote line.


> [!NOTE]
> Changing the resourcing unit, quantity, dates, role, or category values on the quote line detail for cost will change the corresponding values on the quote line details for sales.
## Currency on quote line details for cost and sales

Currency on the quote line detail for sales defaults from the project price list that is effective for the start date of the quote line detail.

Currency on the quote line detail for cost defaults from the price list of the contracting unit of the quote that is effective for the start date of the quote line detail for cost.

Profitability calculations convert the amount on quote line details for cost and sales into the base currency of the environment to report the overall estimated margin on the quote.

> [!NOTE
> Currency rounding errors and changed margins could occur because of the lack of date effective exchange rates. Use these calculations only on project contracts as these are approximations and are not for actual statutory or other reporting that requires higher precision of rounding and awareness of date effectivity for exchange rates.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
