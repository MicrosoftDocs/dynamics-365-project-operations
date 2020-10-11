---
title: Set up cost and sales rates for expenses
description: 
author: rumant
manager: Annbe
ms.date: 10/09/2020
ms.topic: article
ms.service: dynamics-365-projectoperations
ms.reviewer: kfend 
ms.author: rumat
---

# Set up cost and sales rates for expenses

_**Applies To:** Project Operations for resource/non-stocked based scenarios, Lite deployment - deal to proforma invoicing_
## Setting up cost and sales prices for Expenses in Project Operations

Cost and Sales prices can be setup for Transaction Categories in Project Operations. These are designed to be used for Expenses and therefore it is required for accurate downstream functionality that each Transaction category that has cost / sales price setup is also referenced as an Expense Category. Cost and Sales prices for Transaction categories in only be in one currency. This is the currency on the Price list header.

To setup Cost and Sales rates for Transaction Categories, create a price list based on the above section on Price List Header and then navigate to the tab called &quot;Category Prices&quot;. A sub-grid that shows all the Category rates will be shown. From the Sub-grid menu, click on &quot;+ New Category price&quot;. On the quick create slider, enter the Transaction Category and unit for which you need to express the price (cost or sales price).

Below are the fields on the General tab of a Category Price line and the Quick create form of a Category Price line that you need keep in mind as you are creating Category Prices on a &quot;Sales&quot; or a &quot;Cost&quot; price list:

| **Field** | **Location** | **Relevance, purpose, and guidance** | **Downstream impact** |
| --- | --- | --- | --- |
| Transaction Category | General tab and Quick create forms | Select the Transaction Category for which you are expressing the cost or sales rate | Transaction category on the incoming estimate or actual for Expense will be matched against this line to default cost / sales rate of the Transaction Category. |
| Unit Schedule | General tab and Quick create forms | This is defaulted from the Unit Schedule of the Transaction Category | No downstream impact |
| Unit | General tab and Quick create forms | Select the unit for which the rates are being setup. | Unit on the incoming estimate or actual will be matched against the Unit on this line to default rate on the Expense estimate or Actual |
| Pricing method | General tab and Quick create forms | This is an option set with the possible values of Price per unit, At cost and Markup over cost | During price setup, selecting Price per unit will lock Percent field on the Category price line.Selecting &quot;At cost&quot; will lock both Price field and Percent fields. This is only relevant for &quot;Sales&quot; Price list.Selecting &quot;Markup over cost&quot; will lock Price field. This is only relevant for &quot;Sales&quot; Price list. On an incoming actual line for expense, the &quot;At cost&quot; or &quot;Markup over cost&quot; pricing method will result the corresponding unbilled sales line getting price that is either equal to the price on cost actual or calculated as a markup over it. |
| Price | General tab and Quick create forms | Setup per unit rate for the Transaction Category and unit combination.For Eg: The rate for Mileage is 10 USD per mile and 8 USD per Kilometer. | This will be the rate that defaults on the per unit price or cost of the incoming estimate or actual line for Expense transaction class |
| Percent | General tab and Quick create forms | Setup percent over cost for the Transaction Category and unit combination.For Eg: Airfare sales rate should marked-up by 10% over cost of the Airfare expense incurred. | This is only applicable on &quot;Sales&quot; price list and when the pricing method selected is &quot;Markup over cost&quot; |
| Currency | General tab and Quick create forms | By default, this value comes from the currency on the header of the price list. For Transaction category pricing, this cannot be overridden | This will be the currency that defaults on the per unit price of the incoming actual line for Expense transaction class for both cost and sales. |

### Pricing methods for Expenses:

Category price setup that is relevant only in the Expense pricing context allows for the setup of different pricing methods. The following are the methods supported for pricing Expenses in the sales context:

Price per unit: When this pricing method is selected on the Category price line that is linked to a &quot;Sales&quot; price list, price is defaulted for the Category and unit combination defaulting in both the estimate and actual context. Estimate context here is generally meant to denote Project Estimate lines for Expenses and Quote line detail and Contract line detail for Expenses.

At cost: When this pricing method is selected on the Category price line that is linked to a &quot;Sales&quot; price list, price is defaulted for the Category and unit combination only for Expense actual in the sales context i.e. Unbilled sales actuals for Expense transaction class. This is done by setting the unit price on the Unbilled sales actual from the unit price on the Cost actual for that Expense. Price defaulting based on Cost is not done in estimate context i.e. on Project Estimates for Expenses or Quote line detail and contract line details for Expenses.

Markup over cost: When this pricing method is selected on the Category price line that is linked to a &quot;Sales&quot; price list, price is defaulted for the Category and unit combination only for Expense actual in the sales context i.e. Unbilled sales actuals for Expense transaction class. This is done by setting the unit price on the Unbilled sales actual to a calculated value from the unit price on the Cost actual for that Expense after applying the defined markup percent. Price defaulting based on Cost is not done in estimate context i.e on Project Estimates for Expenses or Quote line detail and contract line details for Expenses.
