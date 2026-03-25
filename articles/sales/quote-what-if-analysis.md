---
title: Model what-if scenarios for a project quote (Preview)
description: Learn how to use What-if Analysis in Dynamics 365 Project Operations to simulate changes to work quantities and prices and evaluate financial impact before finalizing a quote.
author: poojafandan
ms.date: 03/25/2026
ms.topic: how-to
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak
ms.author: poojafandan
---

# Model what-if scenarios for a project quote (Preview)

_**Applies To:** Project Operations Core, Project Operations Integrated with ERP_

> [!IMPORTANT]
> **This feature is currently available as a preview and is subject to change. Preview features are recommended for evaluation in non-production environments.**

## Overview

What-if analysis on a project quote enables you to simulate adjustments to **work quantities and prices on quote line details** and immediately see how those changes affect the quote's key financial metrics - without altering the actual quote until you choose to apply a scenario.

By creating and comparing multiple what-if scenarios, **sales managers, project managers, and functional consultants** can test different pricing strategies and staffing plans to identify the most profitable quote structure before finalizing a proposal.

For example, you can model scenarios such as:

- _What happens to margin if we shift more hours to a lower-cost delivery center?_
- _How does a 10 percent rate increase for a specific role affect overall profitability?_

For each scenario, the system recalculates and displays four key financial metrics (KPIs) along with the difference from the baseline quote. This provides real-time visibility into the financial impact of each change.

Create what-if analysis scenarios by using the quote's **current estimates as the baseline**. Each scenario uses the quote's existing estimation and pricing data as its starting point, so you can explore alternatives and evaluate trade-offs without affecting the quote.

Changes you make within a scenario **don't impact the quote's estimates**. The original quote remains unchanged until you apply a scenario.

After reviewing and comparing scenarios, you can apply the selected scenario to the quote. When you apply the scenario, the quote updates with the scenario values.

## Key financial metrics

As you work with what-if scenarios, the system tracks the following KPIs and shows both the scenario value and the **delta (difference) compared to the original baseline quote**.

| **KPI**                     | **Description**                                                                                                                                                                                                                                                                                                                                                                                                | **Delta example**                         |
| --------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------- |
| **Total estimated revenue** | The total extended amount (sales amount) of the quote under the scenario                                                               | **▲ 5%** revenue vs. baseline             |
| **Total estimated cost**    | The projected cost to deliver the work in the scenario                                                                                 | **▼ \$12,000** vs. baseline               |
| **Gross margin (%)**        | The gross margin percentage recalculated from the scenario's revenue and cost, shown relative to the baseline and, where applicable, to a target goal| Margin increased from 15% to 18% (+3 pts) |
| **Budget variance**         | The variance of the scenario's financials compared to the quote's original budget, indicating whether the scenario is over or under the baseline budget.                                                                                                                                                                                                                                                       | Under budget by 4%                        |

These metrics update **in real time** as you make adjustments, providing immediate feedback on each change so you can iteratively refine a scenario toward your desired outcome.

## Create a what-if scenario

### Prerequisites and limitations

- You can create what-if analysis scenarios only on quotes that are in Draft status and contain at least one quote line with estimates.
- Activated or closed quotes are read-only and cannot be used for what-if analysis.
- You can create multiple what-if scenarios for the same draft quote.
- If the quote is modified, existing scenarios become invalid and must be recreated.

1. Open the quote and navigate to the **What-if analysis** tab. This tab appears when the What-if Analysis preview feature is enabled through the feature flag in your environment.
1. Select **Create scenario** to create a new scenario.
1. Provide a title for the scenario and optionally add a description. The quote for which the scenario is created is automatically selected. By default, the Time transaction class is selected, meaning you will adjust quantities or prices for quote line details that use the Time transaction class.
1. Select **Save** to create the scenario.
1. Verify that the scenario opens in a simulation workspace, where all adjustments are isolated from the actual quote. The original quote values remain unchanged until you explicitly apply a scenario.

**Scenario grid fields**

The following table describes the key fields (columns) in the what-if analysis scenario grid:

| **Field**                      | **Description**                                                                                                                                                                                                                                                                                                                                                                              |
The following table describes the key fields (columns) in the what-if analysis scenario grid:

| **Field**                      | **Description**                                                                                                                                                                                                                                                                                                                                                                              |
| ------------------------------ | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Group by**                   | The pricing dimension used to aggregate scenario data. You can change this to another dimension-such as Role or a custom pricing dimension-to analyze the quote from different perspectives. The grid displays one row per unique value of the selected dimension. You can also combine dimensions (for example, Resourcing Unit and Role) to refine analysis.                               |
| **Resourcing unit**            | When _Resourcing Unit_ is the selected Group-by dimension, this column lists each resourcing unit (for example, each geography or organizational unit involved in the quote) as a row in the grid. For example, if the quote contains work assigned to US, India, and Canada, those three units appear as rows.                                                                              |
| **Role**                       | When _Role_ is the selected Group-by dimension, this column lists each resource role from the quote (for example, Developer, Architect, Project Manager) as a row in the grid. For price-focused scenarios, grouping by Role allows direct adjustment of billing rates per role.                                                                                                             |
| **Proposed Quantity**          | The total planned **quantity of work** (such as hours) for the row's dimension value **in the scenario**, after your adjustments. For Time-based work, this is typically measured in the primary unit (for example, hours), with unit conversion applied if quote line details use a mix of units. Adjusting this field simulates increasing or decreasing the work allocated to that group. |
| **Proposed sales price (avg)** | The representative **billing rate** for the row's dimension value in the scenario. When grouped by **Role**, this is the proposed sales price for that role. When grouped by **Resourcing unit**, this reflects the blended average sales rate across all roles within that unit. You can edit this value to simulate rate increases, discounts, or other pricing changes.                   |
| **Proposed sales amount**      | The **total sales amount** (revenue) for the row's dimension value in the scenario, derived from the updated quantities and prices across all quote line details in that group. The sum of all Proposed sales amount values in the grid corresponds to the **Total estimated revenue** KPI for the scenario.                                                                                 |
| **Proposed cost amount**       | The **total cost** to deliver the work for the row's dimension value in the scenario, derived from the cost of all quote line details in that group. The sum of all Proposed cost amount values in the grid corresponds to the **Total estimated cost** KPI for the scenario.                                                                                                                |

## Adjust quantities and prices

Within the scenario's simulation workspace, you can modify inputs based on the type of analysis you're performing. You can adjust quantity, price, or both for the quote line details at an aggregated level (aggregated by the selected pricing dimension). Use the **Adjust by** button to choose whether you want to modify values by price, quantity, or both.

The scenario workspace displays the selected pricing dimensions - including any custom pricing dimensions - and their values based on the current quote. It shows how effort and pricing estimates from the quote are distributed across the selected pricing dimension. For example, estimates might be distributed across resourcing units such as the US, India, and Canada used in the quote.

For each value in the selected dimension, an interactive control - consisting of a slider and input field - displays the current aggregated quantity or average price of the estimate (for example, total hours or average price). The initial values reflect the original distribution defined in the quote.

You can increase or decrease the quantity or sales price for each dimension value independently. Hover over the slider to view the profitability associated with each pricing dimension value, which helps indicate which values are more profitable and which are less.

For example, you might increase the hours allocated to one resourcing unit while reducing the hours for another to simulate shifting work toward a lower-cost delivery center.

Each dimension value is adjusted independently - there's no automatic rebalancing between values. As a result, the total allocation across all values might increase above or decrease below 100% as you experiment.

When you adjust quantity, the changes are distributed proportionally across all quote line details (QLDs) associated with that pricing dimension value.

Similarly, you can increase or decrease the average price for a pricing dimension. For example, if you select a resourcing unit and there's a 5% price increase across all roles in that unit, you can increase the average price by 5% using the slider or by manually entering the percentage.

You can also filter and group by multiple pricing dimensions. For example, if you want to adjust the price or quantity for Consultants within Resourcing Unit US, you can drag the Role pricing dimension to the top bar. The workspace then displays estimates aggregated by role, with an interactive slider next to each role. From there, you can increase the price for Consultants within Resourcing Unit US.

When the distribution is shown in hours for the Time transaction class, the system uses the primary unit. If all quote line details share the same unit, the system applies that unit directly. If multiple units are used, the system converts them by using the primary unit as the base. Minor rounding differences might occur due to these conversions. Such approximations are expected and acceptable in the context of what-if analysis, which is designed for exploratory and comparative evaluation.

## Work with the scenario grid and quote line details

The what-if analysis workspace presents scenario data in a grid layout. You can customize this grid by editing the columns shown in the view - add columns for extra data points you want to monitor or remove columns that aren't relevant to your analysis. By tailoring the workspace, you can focus on the information most important for your evaluation.

You can also open individual quote line details by selecting **View line details** to review or adjust quantity or price values at a more granular, line-by-line level. This level of detail is useful when you need precise control over a specific quote line rather than making broad adjustments across an entire pricing dimension.

Use the **expand** button to enlarge the grid and work in a full-screen workspace.

You can undo or redo changes made in the grid. However, changes are reset if the scenario is refreshed.

## Create and compare multiple scenarios

What-if analysis enables you to create **multiple scenarios** for the same quote so that you can explore different strategies side by side.

For example, you might create one scenario that increases offshore hours, another that raises billing rates, and a third that combines both approaches. Each scenario is saved separately with the label you provide. You can revisit and further refine each scenario at any time until you apply it to the quote.

To manage and label scenarios, use the **Save As** capability to create named variations (for example, _"Aggressive Discount"_, _"Balanced Tradeoff"_, _"High-Margin"_). Each variation is stored as a distinct scenario under the relevant goal.

The What-if analysis tab displays all saved scenarios with their key metric summaries, making it easy to identify and compare options.

## Compare scenarios

The comparison view helps you evaluate scenarios against each other and against the baseline quote.

You see the comparison as a **side-by-side KPI table or visual chart**, which highlights differences between scenarios.

For example:

- Scenario A (shifting work offshore) improves margin by **3 percentage points** but slightly reduces revenue.
- Scenario B (raising rates) increases revenue but produces a smaller margin improvement.

These insights help you determine which scenario best meets profitability goals while staying within the client's pricing expectations.

## Apply a what-if scenario to the quote

When you identify a preferred scenario, **apply** it to update the actual quote with that scenario's adjustments.

- On the **What-if analysis** tab, select the scenario you want to implement and then select **Apply to quote**.
- **Confirm the action** when prompted. The system notifies you that you're about to update the quote with the selected scenario's values.

> [!IMPORTANT]
> When you apply a scenario, the changes go directly to the **same draft quote**. You don't create a new revised quote. This behavior differs from the traditional quote revision process in Project Operations, where revising a quote typically closes the original and creates a new quote record. In What-if Analysis, the original quote's values are updated in place to reflect the chosen scenario.

- After you confirm, the system applies all of the scenario's changes to the quote. Modified **quote line details** update with the new quantities or prices from the scenario. If the scenario includes price adjustments, the system creates any necessary **price override records** on the quote at this time. The quote's financial totals (revenue, cost, margin, and budget variance) now reflect the scenario's outcomes.
- The applied scenario is marked as **Applied** in the scenario list. You can't edit a scenario after you apply it to the quote.

As long as the quote remains in Draft status, you can create new what-if scenarios to explore additional adjustments by using the now-updated quote as the new baseline.

After you apply the desired what-if scenario, you can proceed with your sales process - finalizing the quote, obtaining approvals, and activating it - with confidence that the quote reflects the most profitable and strategically sound option you analyzed.

## Summary

By using **What-if Analysis** in Dynamics 365 Project Operations, sales and project managers can move beyond spreadsheets and manual recalculations when optimizing project quotes. The ability to quickly model different staffing strategies and pricing approaches, see immediate real-time feedback on financial KPIs such as total estimated revenue, total estimated cost, gross margin (%), and budget variance, and compare multiple scenarios side by side empowers organizations to make data-driven decisions during the quoting process. When you identify the most favorable scenario, you can apply it directly to the quote. This approach streamlines the transition from planning to execution and helps ensure that every quote aligns with both customer expectations and business profitability goals.
