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
2. In the newly created price list, select the **Project Price list** form from the view selector. 
3. On the **Material prices**, on the subgrid menu, select **New price list item**. 
4. On the **Quick Create** page, enter the product and unit that you are creating the new price for.
5. Select the pricing method under **Project Pricing** and update the Pricing method and amount fields under **Product Pricing**

![Screenshot of Project form for material price set up](media/Material-Pricing-Project-Price-List-Form.png)


## Material pricing methods in Project Operations

Project Operations supports the following pricing methods for sales price lists:

- **Price per unit** – By default, the sales price of the material will be set to the amount that's specified in the **Currency amount** field.
- **At cost** – By default, the sales price of the material will be set to the **transaction cost of the material**.
- **Markup percentage** – The sales price of the material will be calculated as a **markup percentage** over the transaction cost of the material.

### Example

Below, you can see a view of 3 different products, set up with different project pricing methods. The amount field refers to the amount used for pricing product based contract lines.

![Screenshot of List of products/materials and their prices when used in projects](media/Transaction-cost-based-PM-Material.png)

Assuming a transaction cost of $100 for each product, the unbilled sales actuals per unit of usage in projects will be calculated as below-  

| Product | Project pricing method | Markup percentage | Sales price |Currency|
|---|---|---|---|---| 
|Material at Cost | At Cost | | 100 |USD |
|Material at Mark up over transaction cost | Mark up percentage |10 |110|USD |
|Material at price per unit | Price per unit | | 200 |USD |

To use the new cost based material pricing methods, turn on the **Enable material pricing methods** feature at **Settings** \> **Parameters** \> **Feature control**.


For more information about how to define prices for catalog items, see [Define product pricing with price lists and price list items](/dynamics365/sales/create-price-lists-price-list-items-define-pricing-products) and [Decimal precision in currency and pricing](/dynamics365/sales/decimal-precision-currency-pricing).

> [!NOTE]
> Project Operations doesn't support all the pricing methods for products that Dynamics 365 Sales supports. Originally, only the **Currency amount** pricing method could be used for projects. However, as of Project Operations release UR 30, 2 additional pricing methods are supported. 

[!INCLUDE[footer-include](../includes/footer-banner.md)]
