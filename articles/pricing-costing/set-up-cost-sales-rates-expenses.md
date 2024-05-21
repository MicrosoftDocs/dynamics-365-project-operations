---
title: Set up cost and sales rates for expenses
description: This article provides information about how to set up the cost and sales rates for transaction and expense categories. 
author: avisness
ms.author: avisness
ms.date: 05/21/2024
ms.topic: how-to
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak

---

# Set up cost and sales rates for expenses

[!INCLUDE[banner](../includes/banner.md)]

_**Applies To:** Project Operations for resource/non-stocked based scenarios, Lite deployment - deal to proforma invoicing_

You can set up cost and sales prices for transaction categories in Dynamics 365 Project Operations. Because the cost and sales prices are designed for Expenses, each transaction category that includes these, must also be set up as an expense category. This set up ensures accuracy in downstream functionality. Cost and sales prices for transaction categories can only be listed in one currency, which must be the currency on the price list header.

To set up cost and sales rates for transaction categories, complete the following steps. 

1. Go to **Sales** > **Customers** > **Price Lists**.
2. Select **New** to create a new price list. 
3. On the **Category Prices**, on the subgrid menu, select **New Category Price**. 
4. On the **Quick Create** page, enter the transaction category and unit that you are creating the new price for.

The following table lists the fields on the **General** tab and **Quick Create** page of a category price line that you should keep in mind as you create category prices on a sales or cost price list.

| Field | Location | Description | Downstream impact |
| --- | --- | --- | --- |
| Transaction Category | **General** tab and **Quick Create** pages | Select the transaction category you are creating a sales or cost price for. | The transaction category on the incoming estimate or actual for Expense will be matched against this line to default the cost or sales rate of the transaction category. |
| Unit Schedule | **General** tab and **Quick Create** pages | The unit schedule defaults from the unit schedule of the transaction category. | There is no downstream impact from this field. |
| Unit | **General** tab and **Quick Create** pages | Select the unit for which the rates are being set up. | The unit on the incoming estimate or actual is matched against the unit on this line to default the rate on the expense estimate or actual. |
| Pricing Method | **General** tab and **Quick Create** pages | Possible values of the **Pricing Method** field are, **Price Per Unit**, **At Cost**, and **Markup Over Cost**. | During price setup, selecting **Price Per Unit** locks the **Percent** field on the category price line. If **At cost** is selected, the **Price** and **Percent** fields are locked on the sales price list. Selecting **Markup Over Cost** locks the **Price** field on the sales price list. On an incoming actual line for expense, the **At cost** or **Markup Over Cost** pricing method results in the corresponding unbilled sales line being assigned a price that is equal to the price on the cost actual or calculated as a markup over the price. |
| Price | **General** tab and **Quick Create** pages | Set up a per unit rate for the transaction category and unit combination. For example, the rate for mileage is 10 USD per mile and 8 USD per Kilometer. | The mileage rate will be the rate that defaults on the per unit price or cost of the incoming estimate or actual line for an expense transaction class.|
| Percent | **General** tab and **Quick Create** pages | Set up percent over cost for the transaction category and unit combination. For example, the airfare sales rate should be marked up 10 percent over the cost of the incurred airfare expense. | This percent over cost is only applicable on a sales price list when the pricing method selected is **Markup Over Cost**. |
| Currency | **General** tab and **Quick Create** pages | By default, this value comes from the currency on the header of the price list. For transaction category pricing, the currency can't be overridden. | This currency defaults on the per unit price of the incoming actual line for the expense transaction class for cost and sales. |

## Pricing methods for expenses

When you set up category prices that are only relevant in the context of expense pricing, you can use one of the following three pricing methods:

- **Price per unit**
- **At cost**
- **Markup over cost**

### Price per unit
When this pricing method is selected on a category price line that is linked to a sales price list, the price defaults for the category and unit combination in both the estimate and the actual. Estimate refers to the project estimate lines for expenses, the quote line detail, and the contract line detail for expenses.

### At cost
When this pricing method is selected on the category price line that is linked to a sales price list, the price defaults for the category and unit combination only for the expense actual. For example, unbilled sales actuals for the expense transaction class. The unit price is set on the unbilled sales actual from the unit price on the cost actual for that expense. Price defaulting based on cost isn't done on project estimates for expenses or the quote line and contract line details for expenses.

### Markup over cost
When this pricing method is selected on the category price line that is linked to a sales price list, the price defaults for the category and unit combination only for an expense actual. For example, unbilled sales actuals for the expense transaction class. This unit price is set on the unbilled sales actual to a calculated value from the unit price on the cost actual for that expense after the defined markup percent is applied. Price defaulting based on cost isn't done in on project estimates for expenses or quote line and contract line details for expenses.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
