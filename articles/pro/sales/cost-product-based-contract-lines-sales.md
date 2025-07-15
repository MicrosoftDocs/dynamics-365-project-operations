---
title: Cost product-based contract lines - Project Operations Core
description: This article provides information about creating cost product-based contract lines
author: rumant
ms.date: 10/19/2020
ms.topic: article
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak
ms.author: rumant
---

# Cost product-based contract lines - Project Operations Core

[!INCLUDE[banner](../../includes/banner.md)]

_**Applies To:** Project Operations Core_


Product-based contract lines in Dynamics 365 Project Operations include the **Cost Price** field, which stores the cost price of the product for downstream profitability calculations.

When a product-based contract line is created for a catalog product, the cost of the line defaults from the **Standard Cost** field in the product catalog. The **Standard Cost** field in the product catalog is set up in the Organization's base currency. When the unit cost defaults on the contract line, it's converted into the sales currency on the contract.

## Unit cost on a product-based contract line

Having a unit cost on a product-based contract line allows for different product costs for each sale of a unit. While not always necessary, there are certain scenarios where the cost of the product may be discounted for the customer by the supplier. Consider the following scenario:

Fabrikam Robotics is installing robotic arms at Adatum Corporation's assembly lines. Fabrikam provides installation services but the robotic arms are from Trey Research. If the installation of robotic arms at Adatum Corporation opens a new industry vertical for Trey Research, they could offer a special discount for this deal to Fabrikam. In this case, Fabrikam creates a product-based contract line for Robotic Arms. A per unit cost is entered for this contract. The cost is different from the cost of robotic arms from Trey Research.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
