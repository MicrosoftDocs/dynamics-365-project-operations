---
# required metadata

title: Set up a sales price list 
description: This article provides information about sales price lists for project pricing.
author: rumant
ms.date: 09/18/2020
ms.topic: article
ms.prod: 
#

# optional metadata

# ms.search.form: 
# ROBOTS: 
audience: Application User
# ms.devlang: 
ms.reviewer: johnmichalak
ms.search.scope: 
# ms.tgt_pltfrm: 
ms.custom: 
ms.assetid: 
ms.search.region: Global
ms.search.industry: Service industries
ms.author: suvaidya
ms.dyn365.ops.version: 
ms.search.validFrom: 2020-10-01
---

# Set up a sales price list

_**Applies To:** Project Operations for resource/non-stocked based scenarios, Lite deployment - deal to proforma invoicing_

For project quotes and contracts, a project price list has a different price override pattern than a product price list. On a product catalog–based quote line, you can override the price to roles and categories directly on the quote line, because each quote line points to exactly one catalog item. However, on a project-based quote line, you can't override the price to roles and categories directly on the quote line. You can use the project price list to work with the two distinct override patterns.

> [!NOTE]
> We recommend that you have a separate price list for your project resources and your catalog items, because of the behavior differences between the two when you override pricing.

Each of the following entities can have one or more associated sales price lists for project pricing:

- Customer (account) 
- Opportunity 
- Quote 
- Project Contract

The association of these entities with a price list is indicated by the project price lists. You can associate one or more price lists with the Customer, Opportunity, Quote, and Project Contract sales entities.

A default project price list isn't automatically entered on a customer record. However, you can manually attach a project price list to the customer record. Nevertheless, you should manually attach a project price list only when you have a custom pricing agreement with the customer. 

When a project price list is attached to a sales entity, the following information is validated:

- The price list has a context of **Sales**. 
- The price list currency matches the customer currency. 

On a project contract, the following order of precedence is used to automatically set related project price lists:

1. Quote
2. Opportunity
3. Customer 
4. Global settings 

When a project price list is entered by default, the system validates that the currency matches the customer’s currency, and that the default price lists that have been entered have a context of **Sales**.

You can associate multiple project price lists with the Customer, Opportunity, Quote, and Project Contract entities. This capability supports date-specific default prices for a long-running project contract, where you might require more than one price list to account for price updates that occur because of inflation. However, if the price lists that you associate with the Customer, Opportunity, Quote, or Project Contract entity have overlapping date effectivity, the default prices might be incorrect. Therefore, you should make sure that project price lists that have overlapping date effectivity aren't associated with those entities.


[!INCLUDE[footer-include](../includes/footer-banner.md)]