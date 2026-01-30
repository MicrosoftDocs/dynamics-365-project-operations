---
title: Manage complex units for product-based contract lines - Project Operations Core
description:  Learn about supporting the sale of subscription-based products.
author: poojafandan
ms.date: 01/30/2026
ms.topic: how-to
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak
ms.author: poojafandan
---


# Manage complex units for product-based contract lines - Project Operations Core

[!INCLUDE[banner](../../includes/banner.md)]

_**Applies To:** Project Operations Core_

Dynamics 365 Project Operations uses quantity factors to support the sale of subscription-based products. For subscription-based products, express the quantity on the contract or project contract line as the number of user-months.

Store the price of subscription software in the catalog as the price per-user, per-month. During the sales process, the price on the contract line is usually the per-user, per-month price that the sales agent negotiates and discounts. Each deal has a different number of users and a different number of subscription months. Calculate the quantity to calculate the amount of the contract line as a product of the number of users and the number of subscription months.

To support this type of sale, Project Operations supports the concept of *quantity factors*. Quantity factors rely on product attributes. When you configure specific properties for a product, flag a subset of those properties, or all the properties, as quantity factors.

Project Operations validates that only numeric properties or product properties that have a numeric data type are flagged as quantity factors. When you add a product with configured quantity factors to a contract line, the **Quantity** field becomes read-only. After you enter values for product properties that are quantity factors, Project Operations calculates the quantity of the contract line.

For example, Dynamics 365 Sales might have the following properties:

- **No of users**: The number of users.
- **No of Months**: The number of subscription months.
- **Product SKU**: The stock keeping unit (SKU) for the product.

You can flag the **No of Users** and **No of Months** properties as quantity factors by editing the properties of the product line.

To create quantity factors from product properties, complete the following steps.

1. On the **Project Operations**, select **Sales-Products**.
1. Open the product for which you need to set up quantity factors. Make sure that the product has properties already set up.
1. On the **Project Information** page, select the **Quantity Factors** tab.
1. In the subgrid, select **+ New field computation**.
1. Enter the name of the **Quantity Factor** and select the property value that maps to the field computation.
1. Save and close the form.
1. Repeat steps 2-6 for all the properties that together make up the quantity for the product-based contract line.

When you set up quantity factors, the user locks the quantity of the contract line when they create a contract line for this product. Calculate the quantity as a product of the property values for that contract line.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
