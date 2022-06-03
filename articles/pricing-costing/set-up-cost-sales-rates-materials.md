---
title: Set up cost and sales rates for materials
description: This article provides information about how to set up the cost and sales rates for materials used on projects. 
author: rumant
ms.date: 03/21/2022
ms.topic: article
ms.reviewer: johnmichalak
ms.author: rumant
---

# Set up cost and sales rates for materials

_**Applies To:** Project Operations for resource/non-stocked based scenarios, Lite deployment - deal to proforma invoicing_

You can set up cost and sales prices for products in Dynamics 365 Project Operations. Cost and sales prices for products can only be listed in one currency, which must be the currency on the price list header.

To set up cost and sales rates for products, complete the following steps. 

1. Go to **Sales** > **Customers** > **Price Lists** and select **New** to create a new price list. 
2. On the **Price list items**, on the subgrid menu, select **New price list item**. 
3. On the **Quick Create** page, enter the product and unit that you are creating the new price for.

For more information about how to define prices for catalog items, see [Define product pricing with price lists and price list items](/dynamics365/sales/create-price-lists-price-list-items-define-pricing-products) and [Decimal precision in currency and pricing](/dynamics365/sales/decimal-precision-currency-pricing).
> [!NOTE]
> Dynamics 365 Project Operations does not support all the pricing methods for products as Dynamics 365 Sales. The only pricing method supported for products to be used on projects is *Currency amount*.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
