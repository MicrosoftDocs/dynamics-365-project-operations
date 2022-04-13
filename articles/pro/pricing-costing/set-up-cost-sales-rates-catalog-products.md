---
title: Set up cost and sales rates for catalog products - lite
description: This topic provides information about how to set up cost and sales rates for items in a product catalog.
author: rumant
ms.date: 10/09/2020
ms.topic: article
ms.prod:
ms.reviewer: johnmichalak
ms.author: rumant
---

# Set up cost and sales rates for catalog products - lite

_**Applies To:** Lite deployment - deal to proforma invoicing_


Setting up pricing for product catalog items in Dynamics 365 Project Operations is the same as in Dynamics 365 Sales.

In Project Operations, products can't be estimated or used on projects, so product catalog prices don't need to be set on project price lists for quotes and contracts.

Use the **Product Price** field of a quote, contract, or account to set up product catalog prices. Don't set up product catalog prices in the project price lists. Project price lists are exclusive to Project Operations. Application-specific business logic copies the price lists from a quote to a contract. The result is a contract-specific project price list. The copy operation can delay the quote win process if the project price list on the quote gets too large. Product price lists aren't copied to create custom price lists on contracts. Because there's no copying involved, the performance of the quote process isn't affected.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]