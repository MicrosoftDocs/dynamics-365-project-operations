---
# required metadata

title: New Quote form experience
description: This article provides information about the updates to the project quotes form in Microsoft Dynamics 365 Project Operations.
author: poojafandan
ms.date: 09/10/2026
ms.topic: concept-article
ms.custom: bap-template
ms.reviewer: johnmichalak
ms.author: poojafandan
---

# New Quote form experience

[!INCLUDE [banner](../includes/banner.md)]

_**Applies To:** Project Operations Integrated with ERP, Project Operations Core_

This article provides information about the updates to the project quotes form in Dynamics 365 Project Operations.

> [!IMPORTANT]
> The new modern quote experience is available only when the associated feature is enabled. Contact your administrator if you don't see the updated experience.

We're releasing the enhanced version of our new quote experience. The goal is to improve the overall user experience, uptake new platform capabilities, and simplify user interactions when creating a quote. The experience updates the existing **Quote** form. It doesn't introduce a separate form.

Here are some of the features:

- A new, clean experience that uses a single form layout
- A new key performance indicator (KPI) control that highlights key quote metrics
- A reduction in the number of form interactions
- Scenario-focused data views

## Usage changes

The number of tabs on the **Quote** form is reduced to create a cleaner, more intuitive experience. You can now access **Quote Line Details** through a dedicated full-page experience, enabling better planning, improved visibility into quote information, and deeper insights across the entire quote.

## Summary tab

The **Summary** tab provides the financial, schedule, and quote line information that you need to review most frequently.

### Review financial and delivery information

Financial key performance indicators (KPIs) at the top of the tab provide an overview of the quote.

| KPI | Description |
| ----- | ------------- |
| **Gross margin** | The difference between the estimated revenue and estimated cost for the quote. |
| **Total amount** | The total estimated sales value of the quote. |
| **Total cost** | The total estimated cost of delivering the quoted work. |
| **Delivery date** | The expected delivery date for the quoted work. |

Use these KPIs to review the quote's expected financial performance and delivery date without navigating to another tab.

### Manage quote lines and estimates

You can access the quote lines section directly on the **Summary** tab. From this section, you can:

- Create a quote line.
- Edit an existing quote line.
- Delete a quote line.
- Import estimates into a quote line.
- Create estimates for a quote line.

Use the view selector to switch between **Project Lines** and **Product Lines**. Select **Add Line** to create a new project or product quote line. A quick create form opens to capture the required information. Select the quote line hyperlink to open the full quote line details page for more editing. For project-based quote lines, the **Summary** tab shows key attributes such as billing method, invoice schedule type, project association, and budget performance. Budget performance metrics include transaction classes, discounts, fees, margin percentage, and extended amount. These metrics help you evaluate quote profitability and financial impact.

You can also:

- Select and go to the quote lines form to view and edit more details such as line details, chargeable roles, chargeable tasks, chargeable categories, invoice schedule, line customer, and related information.
- Create new quote lines or delete existing ones.
- Import project estimates to generate quote line details automatically.
- Enter quote line details manually when needed.

### Review the cost over revenue chart

The **Cost over revenue** chart provides a monthly breakdown of estimated cost and revenue. Use the chart to compare cost and revenue over time and identify trends across the quote's estimated schedule.

## Line details tab

The **Line details** tab provides a full-page view of all quote line details. By default, it groups line details by quote line so you can review the estimates that contribute to each line.

Quote line details contain the underlying estimates for the work included in a project quote. Depending on the transaction class, a line detail can include information such as quantity, price, cost, and amount. When you select the quote line details, you can edit or delete them. To view the cost detail, select **Open cost detail**.

Use the view selector to switch between **Project Line Details** and **Project Line Details: Cost**. The **Project Line Details** view shows line information from a sales perspective, while the **Project Line Details: Cost** view displays the associated cost details. By using these views, you can analyze both revenue and cost aspects of the quote.

### Group line details

You can group line details by quote line, billing type, transaction category, or pricing dimensions.

Use grouping to review the estimate from different perspectives. For example, group by quote line to understand the estimate for each component of work, or group by a pricing dimension to compare similarly priced work across quote lines.

### View time-phased estimates

If the **Time Phasing of Estimates** feature is enabled, you can view the time-phased breakdown for quote line details.

The time-phased view shows how the following values are distributed across periods:

- Quantity
- Price
- Amount

Use the time-phased breakdown to understand how effort and financial estimates change over the quote schedule.

> [!NOTE]
> The time-phased breakdown is available only when the **Time Phasing of Estimates** feature is enabled.

### Use role price override within Quote and Quote Line form

To create price overrides for time transaction line details, select the line detail, and then select the price override button.
The Price Override button, integrated into the Quote and Quote Line form, helps you change price overrides for quote line details. This feature cuts down on the number of clicks and simplifies the process of adjusting prices while you stay focused on each specific quote line detail.

Usage instructions: Select the quote line detail that needs a price adjustment. Select **Price Override** to start the price modification process. A flyout appears that you can use to edit the price while keeping the context of the quote line detail.

Functionality: If a price override already exists, the new price updates it automatically. If no override exists, the new price creates a price override. The Price Override button appears only if the price you're editing comes from the role price list.

More information: The scope of the price override automatically configures to the respective quote.

## Analysis tab

The **Analysis** tab provides financial performance indicators and charts that help you evaluate the quote and compare quote lines.

### Review financial performance indicators

Financial performance indicator cards appear at the top of the tab. Use these cards to review the quote's financial performance before you analyze individual quote lines or resource roles.

### Review quote line trends

The quote line trend chart compares revenue, cost, and margin across your quote lines. Use this chart to:

- Compare estimated revenue and cost.
- Review expected margin.
- Identify quote lines that contribute the most to the quote's financial results.
- Identify quote lines that might require pricing or estimate changes.
  
### Review top resource roles

The resource role chart compares cost and revenue for the top resource roles in the quote. Use this chart to identify the roles that have the greatest effect on estimated cost and revenue.

To update the KPIs, select **Recalculate** on the quote.

## General tab

The **General** tab contains the primary quote configuration and administrative details. Review and update quote information, including customer, pricing, ownership, and status details. The tab also includes **Customer Billing**, where you can add quote customers, define billing splits, and configure billing rules to support single-customer or split-billing scenarios.

The available fields can vary based on your organization's configuration and your security role.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
