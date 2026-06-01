---
title: Product price lists
description: This article provides information about the price lists in catalog pricing used for project quotes and contracts. 
author: abriccetti
ms.author: abriccetti
ms.date: 01/09/2025
ms.topic: concept-article
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak
ms.dyn365.ops.version: 
ms.search.validFrom: 2020-10-01
---

# Product price lists

[!INCLUDE[banner](../includes/banner.md)]

_**Applies To:** Project Operations Core_

 In Project Operations, **Product price lists** and related price list item entities support functionality for pricing products on product-based quote and contract lines. For products used on projects, the price list item records for project price lists are used. 

Products should be set up so that they have default cost and price lists in the product catalog. Use the list price, standard cost, and current cost to configure default cost and list prices. The default list prices are used on a quote line or a project contract line only when the system can't find a price list line for that product in the product price list for the quote or project contract.

The cost price of product catalog lines can be changed between quotes. This capability is important, because if you don't accurately track costs, you can't determine operational profits on project engagements. By default, the standard cost of the product is used as the cost price. However, the default cost price can be updated on the quote line if there's a different cost price for that quote.

## Price list items

You can add products from a product catalog to different price lists. Price list lines for products always reference a specific unit. Pricing for a product on price list items can be configured as a currency amount. Alternatively, it can be configured as a function of the list price, current cost, or standard cost.

Pricing functionality supports various rounding options when product prices are configured as a function of the list price, standard cost, or current cost. In addition to taking advantage of multiple pricing methods and rounding options, you can associate discount lists with price list items. 

 
## Default product price list
Each customer record has a **Default Price List** field, where you can specify a price list that matches the currency of the customer. A default value isn't automatically entered in this field. When a custom pricing agreement with a specific customer exists, you can use this field to associate a price list with that customer.

The Opportunity, Quote, and Project Contract entities use the following order to enter default product price lists. The same order is used for project price lists.

1.	Quote
2.	Opportunity
3.	Customer
4.	Global settings 

By default, the **Product** field on the quote line lists all the active products in the product price list of the quote. If a product has been inactivated, or if it's a draft product, it isn't listed, even if it's in the price list. 

Product catalog lines are added as invoice lines on the first invoice that is created for a project contract. On a draft invoice, those invoice lines can be deleted. In that case, the lines will appear on a subsequent invoice until they are invoiced, or until the invoice is sent to the customer. You can't invoice a partial quantity of a product invoice line. When the product lines from the project contract are invoiced, actuals are created. However, those actuals aren't linked to the related project entity. In other words, product-based project contract lines are independent of any project-based use. 


[!INCLUDE[footer-include](../includes/footer-banner.md)]
