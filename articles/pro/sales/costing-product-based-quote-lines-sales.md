---
title: Costing product-based quote lines
description: This article provides information about applying a cost price to a product-based quote line.
author: poojafandan
ms.date: 02/26/2026
ms.topic: concept-article
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak
ms.author: poojafandan
---

# Costing product-based quote lines

[!INCLUDE[banner](../../includes/banner.md)]

_**Applies To:** Project Operations Core_


Product-based quote lines in Dynamics 365 Project Operations also have a **Cost Price** field. Use this field to track the cost price for the product on the quote line and for downstream profitability calculations.

When you create a product-based quote line for a catalog product, the system defaults the cost of the product-based quote line from the **Standard Cost** field in the product catalog. Set the standard cost field in the product catalog in the organization's base currency. The system converts the default unit cost on the product-based quote line to the sales currency on the quote.

## Unit cost on a product-based quote line

The purpose of the unit cost on a product-based quote line is to allow for different costs for a product for each sale. This cost isn't a typical scenario, but sometimes the supplier discounts the cost of the product depending on the customer of the final sale.

For example:

Fabrikam Robotics is installing robotic arms at A Datum Corporation's assembly lines. Fabrikam provides installation services but the robotic arms are procured from Trey robotics. If the installation of robotic arms at A Datum Corporation opens a new industry vertical for Trey's robotic arms, Trey could give a special discount for this deal to Fabrikam.

In this case, Fabrikam creates product-based quote line for Robotic Arms and inputs a special per unit cost for this quote. This cost is different from the standard cost of Trey Robotic Arms.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
