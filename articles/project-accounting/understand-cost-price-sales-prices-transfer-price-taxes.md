---
title: Project adjustments
description: This article provides information about project adjustments.
author: ryansandness
ms.date: 03/17/2023
ms.topic: article
ms.reviewer: johnmichalak
ms.author: ryansandness
---

# Understanding how cost prices, sales prices, transfer prices and taxes work together

_**Applies To:** Project Operations for stocked/production-based scenarios_

## Overview

There are multiple different prices to be configured in order to calculate and determine the internal organizational cost of goods and services and what your customer is billed for through the sales price they pay. Additionally, you can set what the sales price is for intercompany billing through the configuration of transfer prices. For these scenarios, there are also added conditions on how to consider how taxes are included in calculated prices.

### Cost Prices

Project cost prices exist in several areas in **Project management and accounting** including timesheets, journals, item requirements, purchase orders, and expenses. Cost prices do not apply to fees or subscriptions. Cost prices apply to all project types. 

- Cost prices for hours are configured from **Project Management and accounting** \> **Setup** \> **Cost price - (hour)**
- Cost prices for expenses are configured from **Project Management and accounting** \> **Setup** \> **Cost price - (expense)**
- Cost prices for items are configured within **Inventory Management** 

### Sales Prices

Sales prices exist for the documents previously mentioned and also include fees and subscriptions. Sales prices apply differently depending on the project type. For example, item sales price would not apply to a fixed price project, but fee prices would apply. Sales prices would apply for all document types in Time and material projects.

- Sales prices for hours are configured from **Project Management and accounting** \> **Setup** \> **Sales price - (hour)**
- Sales prices for expenses are configured from **Project Management and accounting** \> **Setup** \> **Sales price - (expense)**
- Sales prices for fees are configured from **Project Management and accounting** \> **Setup** \> **Sales price - (fee)**
- Sales prices for expenses are configured from **Project Management and accounting** \> **Setup** \> **Sales price - (subscription)**
- Sales prices for items are configured within **Inventory Management**

### Transfer Prices

Transfer prices exist for hours, expenses, and vendor invoices.

Transfer prices define sales prices for workers who work on projects in related legal entities, for project expenses in other legal entities, and for purchased goods that are transferred to related legal entities. For a lending legal entity, a transfer price for an **Hour** transaction type is used as a sales price for hours that a worker spends working on a project for another legal entity in your organization. The transfer price for an **Expense** or **Vendor invoice line** transaction type is is used as the value for costs that one legal entity incurs, and that a related legal entity then reimburses to that legal entity. The transfer price for these transaction types represents a project cost for the borrowing legal entity.

You can set up a transfer price that applies to all project work and expenses that are recorded in a borrowing legal entity. Alternatively, you can set specific prices for any combination of worker, project, transaction type, and category criteria for each borrowing legal entity.

Before you can use the transfer prices that you set up, you must enable **Enable intercompany resource scheduling and timesheets** in the **Project management and accounting parameters** form, on the **Intercompany** page.

## Taxes

The calculation of taxes can have an impact on both your cost and sales price. This is most noticeable when working with scenarios where the prices you are entering is inclusive of tax and a calculation is performed to determine the individual cost, tax, and sales prices.

### Enable the streamline cost price and sales price calculations feature
With the 10.0.32 release, the **Streamline cost price and sales price calculations** feature is available to be enabled in your Dynamics 365 environment. With this change, improvements have been made to project-related scenarios in the following areas:

- Purchase orders and vendor invoices created in combination with the general ledger parameter for applying taxation rules
- Purchase orders and vendor invoices in combination with posting with amounts including sales tax
- Tax involving use tax
- Funding source limits
- Committed costs
- Purchase order corrections
- Adds support for **Amount includes sales tax** in the Purchase Order header

This feature should be enabled as a baseline to ensure behavior is consistent in how taxes should impact cost and sales prices.

### Taxes impacting project cost
The two scenarios below are situations where taxes should be included in the project cost:

- Legal entities with the sales tax parameter Sales taxation rules is enabled. Typically, this is US-based legal entities. 
- Legal entities with non-deductible tax percentages. This non-deductible tax is always included in the project cost.

### Expense-related scenarios with markup
For any project expense type transaction, Dynamics 365 can modify the sales price dynamically based on one of several factors defined in the **Sales price – (expense)** form. One of the commonly used methods is to apply a **charges percentage** markup, to mark up all costs by a set amount. For example, a 5% markup on all expenses which makes a $1000 expense invoiceable at $1050 by defaulting that sales price in the vendor invoice which will later transfer to our customer invoice.

Let’s look at some specific examples to understand how prices and taxes are calculated. For these examples, the tax percentage is set to 5% and there is a sales price 5% markup on cost price. We will follow the document flow of a purchase order through to a vendor invoice and review the financial impact in the **Posted project transactions** form.

|Apply sales taxation rules|Amounts including Sales Tax|Non-Deductible %|Cost Price in Document|Sales Price In Document|Posted Project Cost|Posted Project Sales Price|Notes|
|---|---|--|---|---|---|---|---|
|No |No |0 |1000|1050|1000|1000 x 1.05 markup = 1050|   |
|Yes|No |0 |1000|1050|1000 + 50 tax = 1050          |1000 x 1.05 markup x 1.05 tax = 1102.50|   |
|No |No |20|1000|1050|1000 + 10 tax = 1010          |1000 x 1.05 markup x 1.01 tax = 1060.50|5% tax multiplied by 20% non-deductible = 1%. <br> 20% of 50 tax amount = 10   |

These same rules apply when determining the project cost and sales price when entering a purchase order with an amount that already includes sales tax. In the case of the purchase order or vendor invoice, there is an option in the header that **Prices include sales tax** to indicate the amount entered should be inclusive of tax and the base amount and tax need to be calculated from the entered amount. Since the actual cost and sales price may include a markup of tax, the amounts entered for sales price and cost will be recalculated and different values will be posted in the final voucher. Consider the examples below with the same 5% tax rate and 5% markup described earlier:

|Apply sales taxation rules|Amounts including Sales Tax|Non-Deductible %|Cost Price in Document|Sales Price In Document|Posted Project Cost|Posted Project Sales Price|Notes|
|---|---|--|---|---|---|---|---|
|No |Yes|0 |1000|1050|1000 / 1.05 = 952.38|952.38 x 1.05 markup = 1000|Divide the original amount by 1 + tax rate for cost without tax|
|Yes|Yes|0 |1000|1050|1000 / 1.05 = 952.38 + 47.62 tax = 1000|952.38 x 1.05 markup x 1.05 tax = 1050|Divide the original amount by 1 + tax rate for cost without tax|
|No |Yes|20|1000|1050|1000 / 1.05 = 952.38 + 9.52 tax = 961|952.38 x 1.05 markup x 1.01 tax = 1010|5% tax multiplied by 20% non-deductible = 1%. 20% of 47.62 tax amount = 9.52
 |
