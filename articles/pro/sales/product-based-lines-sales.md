---
title: Product-based opportunity lines
description: This topic provides information about product-based opportunity line items in Project Operations.
author: rumant
manager: Annbe
ms.date: 10/01/2020
ms.topic: article
ms.service: dynamics-365-customerservice
ms.reviewer: kfend 
ms.author: rumant
---

# Product-based opportunity lines

_**Applies To:** Lite deployment - deal to proforma invoicing_

Product-based opportunity lines are line items on the Opportunity. These lines are delivered to the customer as distinct line items on the eventual invoice without any other value-added services. The associated spend and consumption isn't tracked on tasks of any related projects.

Product-based lines can be catalog items or write-in products. Most of the functionality on an Opportunity's product-based lines follows the functionality provided by the Dynamics 365 Sales application. For more information about product-based opportunity lines, see [Add products to an opportunity](https://docs.microsoft.com/dynamics365/sales-enterprise/add-products-opportunity).

One concept about product-based opportunity lines that is specific to project-based opportunities is **Customer Budget**. Use this field to track the amount the customer is willing to pay for the line item.

If the revenue method of the Opportunity summary is set to **System Calculated**, the customer budget values across product- and project-based lines are summarized to calculate the estimated revenue.
