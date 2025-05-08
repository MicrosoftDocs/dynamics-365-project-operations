---
title: Costing product-based quote lines
description: This article provides information about applying a cost price to a product-based quote line.
author: poojafandan
ms.date: 06/07/2024
ms.topic: concept-article
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak
ms.author: poojafandan
---

# Costing product-based quote lines

[!INCLUDE[banner](../../includes/banner.md)]

_**Applies To:** Lite deployment - deal to proforma invoicing_


Product-based quote lines in Dynamics 365 Project Operations also have a **Cost Price** field. This field is used to track the cost price for the product on the quote line and for downstream profitability calculations.

When a product-based quote line is created for a catalog product, the cost of the product-based quote line is defaulted from the **Standard Cost** field in the product catalog. The standard cost field in the product catalog is set up in the Organization's base currency. The default unit cost on the product-based quote line is converted to the sales currency on the quote.

## Unit cost on a product-based quote line

The purpose of having a unit cost on a product-based quote line is to allow for different costs for a product for each sale. This is not a typical scenario, but sometimes the cost of the product may be discounted by the supplier depending on the customer of the final sale.

For example:

Fabrikam Robotics is installing robotic arms at A Datum Corporation's assembly lines. Fabrikam provides installation services but the robotic arms are procured from Trey robotics. If the installation of robotic arms at A Datum Corporation opens a new industry vertical for Trey's robotic arms, Trey could give a special discount for this deal to Fabrikam.

In this case, Fabrikam will create product-based quote line for Robotic Arms and input a special per unit cost for this quote. This cost is different from the standard cost of Trey Robotic Arms.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
