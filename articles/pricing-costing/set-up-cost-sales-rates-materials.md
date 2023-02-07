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

> [!NOTE]
> Project Operations doesn't support all the pricing methods for products that Dynamics 365 Sales supports. Originally, only the **Currency amount** pricing method could be used for projects. However, as of Project Operations release UR 30, three pricing methods are supported. For more information, see the next section.

## Material pricing methods in Project Operations

Project Operations supports the following pricing methods for sales price lists:

- **Price per unit** – By default, the sales price of the material will be set to the amount that's specified in the **Currency amount** field.
- **At cost** – By default, the sales price of the material will be set to the transaction cost of the material.
- **Markup percentage** – The sales price of the material will be calculated as a markup percentage over the transaction cost of the material.

### Example

The following table shows three products, each of which has a different pricing configuration. The currency amount is $120, and the transaction cost is $100.

| Product | Project pricing | Cost price | Markup percentage | Sales price |
|---|---|---|---|---|
| Item A | Price per unit | $100 | | $120 |
| Item B | At cost | $100 | | $100 |
| Item C | Markup percentage | $100| 10% | $110 |

To use the new pricing methods, turn on the **Enable material pricing methods** feature at **Settings** \> **Parameters** \> **Feature control**.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
