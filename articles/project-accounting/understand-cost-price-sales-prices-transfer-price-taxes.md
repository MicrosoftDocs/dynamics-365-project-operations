---
title: Understand how cost prices, sales prices, transfer prices, and taxes work together
description: This article helps you understand how cost prices, sales prices, transfer prices, and taxes work together.
author: ryansandness
ms.author: ryansandness
ms.date: 02/26/2026
ms.topic: concept-article
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak

---

# Understand how cost prices, sales prices, transfer prices, and taxes work together

_**Applies To:** Project Operations for manufacturing-based scenarios_

You must configure several prices to calculate and determine the internal organizational cost of goods and services, and the amount that your customers are billed for, based on the sales prices that they pay. Additionally, you can set the sales price for intercompany billing by configuring transfer prices. For these scenarios, you must also consider other conditions that are related to the way that taxes are included in calculated prices.

### Cost prices

Project cost prices exist in several areas in Project management and accounting, such as timesheets, journals, item requirements, purchase orders, and expenses. Cost prices don't apply to fees or subscriptions. They apply to all project types. 

- Configure cost prices for hours at **Project Management and accounting** \> **Setup** \> **Cost price - (hour)**.
- Configure cost prices for expenses at **Project Management and accounting** \> **Setup** \> **Cost price - (expense)**.
- Configure cost prices for items in Inventory Management.

### Sales prices

Sales prices exist for the previously mentioned documents, and they include fees and subscriptions. Sales prices apply differently, depending on the project type. For example, item sales prices don't apply to a fixed price project, but fee prices do apply. Sales prices apply to all document types in time and material projects.

- Configure sales prices for hours at **Project Management and accounting** \> **Setup** \> **Sales price - (hour)**.
- Configure sales prices for expenses at **Project Management and accounting** \> **Setup** \> **Sales price - (expense)**.
- Configure sales prices for fees at **Project Management and accounting** \> **Setup** \> **Sales price - (fee)**.
- Configure sales prices for subscriptions at **Project Management and accounting** \> **Setup** \> **Sales price - (subscription)**.
- Configure sales prices for items in Inventory Management.

### Transfer prices

Transfer prices exist for hours, expenses, and vendor invoices.

You use transfer prices to set sales prices for workers who work on projects in related legal entities, for project expenses in other legal entities, and for purchased goods that you transfer to related legal entities.

For a lending legal entity, use the transfer price for an **Hour** transaction type as the sales price for hours that a worker spends working on a project for another legal entity in your organization. Use the transfer price for an **Expense** or **Vendor invoice line** transaction type as the value of costs that one legal entity incurs, and that a related legal entity then reimburses to that legal entity. The transfer price for these transaction types represents a project cost for the borrowing legal entity.

You can set up a transfer price that applies to all project work and expenses that you record in a borrowing legal entity. Alternatively, set specific prices for any combination of worker, project, transaction type, and category criteria for each borrowing legal entity.

Before you can use the transfer prices that you set up, you must enable the **Enable intercompany resource scheduling and timesheets** option on the **Intercompany** tab of the **Project management and accounting parameters** page.

## Taxes

The calculation of taxes can affect both your cost price and your sales price. You see this effect most clearly in scenarios where the prices that you enter include tax, and a calculation is done to determine the individual costs, taxes, and sales prices.

### Enable the Streamline cost price and sales price calculations feature

In the 10.0.32 release, the **Streamline cost price and sales price calculations** feature can be enabled in your Dynamics 365 environment. This feature introduces improvements to project-related scenarios in the following areas:

- Purchase orders and vendor invoices that are created in combination with the general ledger parameter for applying taxation rules
- Purchase orders and vendor invoices in combination with posting where amounts include sales tax
- Tax that involves use tax
- Funding source limits
- Committed costs
- Purchase order corrections

This feature also adds support for the **Amount includes sales tax** option on the purchase order header.

This feature should be enabled as a baseline to ensure that taxes affect cost and sales prices in a consistent manner.

### Taxes that affect project cost

In both the following scenarios, taxes should be included in the project cost:

- Legal entities where the **Sales taxation rules** sales tax parameter is enabled. Typically, these legal entities are based in the United States.
- Legal entities that use non-deductible tax percentages. This non-deductible tax is always included in the project cost.

### Expense-related scenarios with markup

For any project expense–type transaction, Dynamics 365 can dynamically modify the sales price, based on one of several factors that are defined on the **Sales price – (expense)** page. In one commonly used method, a *charge percentage* markup is applied to mark up all costs by a specific amount. For example, a 5-percent markup on all expenses makes a $1,000 expense invoiceable at $1,050 by entering that sales price by default on the vendor invoice. That sales price will then be transferred to the customer invoice.

The following examples will help you understand how prices and taxes are calculated. For these examples, the tax percentage is set to 5 percent, and there's a sales price 5-percent markup on the cost price. You'll follow the document flow of a purchase order through to a vendor invoice and review the financial impact on the **Posted project transactions** page.

| Apply sales taxation rules | Amounts include sales tax | Non-deductible percentage | Cost price in document | Sales price in document | Posted project cost | Posted project sales price | Notes |
|---|---|--|---|---|---|---|---|
| No | No | 0 | 1,000 | 1,050 | 1,000 | 1,000 &times; 1.05 markup = 1,050 | |
| Yes | No | 0 | 1,000 | 1,050 | 1,000 + 50 tax = 1,050 | 1,000 &times; 1.05 markup &times; 1.05 tax = 1,102.50 | |
| No | No | 20 | 1,000 | 1,050 | 1,000 + 10 tax = 1,010 | 1,000 &times; 1.05 markup &times; 1.01 tax = 1,060.50 | <p>5% tax multiplied by 20% non-deductible = 1%</p><p>20% of 50 tax amount = 10</p> |

These same rules are applied to determine the project cost and sales price when you enter a purchase order where an amount already includes sales tax. In the case of a purchase order or vendor invoice, the header includes a **Prices include sales tax** option. You can use this option to indicate that the amount that's entered should include tax, and the base amount and tax must be calculated based on the entered amount. Because the actual cost and sales price might include a markup of tax, the amounts that are entered for sales price and cost will be recalculated, and different values will be posted in the final voucher. The following examples use the same 5-percent tax rate and 5-percent markup as the previous examples.

| Apply sales taxation rules | Amounts include sales tax | Non-deductible percentage | Cost price in document | Sales price in document | Posted project cost | Posted project sales price | Notes |
|---|---|--|---|---|---|---|---|
| No | Yes | 0 | 1,000 | 1,050 | 1,000 &divide; 1.05 = 952.38 | 952.38 &times; 1.05 markup = 1,000 | Divide the original amount by 1 + tax rate for cost without tax. |
| Yes | Yes | 0 | 1,000 | 1,050 | 1,000 &divide; 1.05 = 952.38 + 47.62 tax = 1,000 | 952.38 &times; 1.05 markup &times; 1.05 tax = 1,050 | Divide the original amount by 1 + tax rate for cost without tax. |
| No | Yes | 20 | 1,000 | 1,050 | 1,000 &divide; 1.05 = 952.38 + 9.52 tax = 961 | 952.38 &times; 1.05 markup &times; 1.01 tax = 1,010 | <p>5% tax multiplied by 20% non-deductible = 1%</p><p>20% of 47.62 tax amount = 9.52</p> |

[!INCLUDE[footer-include](../includes/footer-banner.md)]