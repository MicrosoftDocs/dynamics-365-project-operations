---
title: Set up cost and sales rates for catalog products
description: This topic provides information about how to set up cost and sales rates for items in a product catalog.
author: rumant
manager: Annbe
ms.date: 10/09/2020
ms.topic: article
ms.service: project-operations
ms.reviewer: kfend 
ms.author: rumant
---

# Set up cost and sales rates for catalog products

_**Applies To:** Lite deployment - deal to proforma invoicing_


Setting up pricing for product catalog items in Dynamics 365 Project Operations is the same as in Dynamics 365 Sales.

Because products can't be estimated or used on projects in Project Operations, there is no need to set product catalog prices on project price lists for quotes and contracts.

Product catalog prices should be set up in the **Product Price** field of a quote, contract, or account. Don't set up product catalog prices in the project price lists for these entities. Project price lists are exclusive to Project Operations. There is application-specific business logic that copies the price lists from a quote to a contract. The result is a contract-specific project price list. The copy operation can delay the quote win process if the project price list on the quote gets too large. Product price lists aren't copied to create custom price lists on contracts. This means that product price lists don't impact the performance of the quote win process.
