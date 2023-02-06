---
title: Set up cost and sales rates for materials
description: This article provides information about how to set up the cost and sales rates for materials used on projects. 
author: rumant
ms.date: 01/25/2023
ms.topic: article
ms.reviewer: johnmichalak
ms.author: suvaidya
---

# Set up cost and sales rates for materials

_**Applies To:** Project Operations for resource/non-stocked based scenarios, Lite deployment - deal to proforma invoicing_

You can set up cost and sales prices for products in Microsoft Dynamics 365 Project Operations. Cost and sales prices for products can only be listed in one currency, which must be the currency on the price list header.

To set up cost and sales rates for products, complete the following steps. 

1. Go to **Sales** > **Customers** > **Price Lists** and select **New** to create a new price list. 
2. On the **Price list items**, on the subgrid menu, select **New price list item**. 
3. On the **Quick Create** page, enter the product and unit that you are creating the new price for.

For more information about how to define prices for catalog items, see [Define product pricing with price lists and price list items](/dynamics365/sales/create-price-lists-price-list-items-define-pricing-products) and [Decimal precision in currency and pricing](/dynamics365/sales/decimal-precision-currency-pricing).

> [!Note]
> Project Operations does not support all of the pricing methods for products Microsoft Dynamics 365 Sales. Oiginally only the **Currency amount** pricing method was supported for use on projects. Beginning with Project Operations release UR 30, two more pricing methods are supported. See below for more information. 

## Material pricing methods in Project Operations 
Project Operations supports the following pricing methods for Sales price lists:  

- **Price per unit** - The sales price for the material will default to the amount specified in the **Currency amount** field. 
- **At cost** - The sales price for the material will default to the transaction cost for the material. 
- **Markup percentage** - The sales price for the material will be calculated as a mark up percentage over the transaction cost for the material. 

### Example

The following table shows three products with three diferent pricing configurations. The **Currency amount** = $120, and the **Transaction cost** = $100.

| Product | Project Pricing | Cost price | Markup percentage| Sales price| 
| ---  | --- | --- | --- | --- |
|Item A | **Price per unit** | $100 |   | $120 |
|Item B | **At cost**        | $100 |   | $100 |
|Item C | **Markup percentage**| $100| 10%  |  $110|

To use the new pricing methods, turn on the feature **Enable material pricing methods** under Settings --> Parameters--> Feature control. 


[!INCLUDE[footer-include](../includes/footer-banner.md)]
