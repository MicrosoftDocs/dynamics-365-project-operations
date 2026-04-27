---
title: Managing complex units such as per-user, per-month for product-based quote lines
description: This article provides information about managing complex units for product-based quote lines.
author: rumant
ms.date: 02/26/2026
ms.topic: how-to
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak
ms.author: rumant
---

# Managing complex units such as per-user, per-month for product-based quote lines

[!INCLUDE[banner](../../includes/banner.md)]

_**Applies To:** Project Operations Core_

Dynamics 365 Project Operations uses quantity factors to support the sale of subscription-based products. For subscription-based products, the quantity on the quote or project contract line is expressed as the number of user-months.

Usually, the price of subscription software is stored in the catalog as the price per user per month. During the sales process, the price on the quote line is usually the per-user, per-month price that the IT sales agent negotiated and discounted. Each deal has a different number of users and a different number of subscription months. The quantity used to compute the quote line is a product of the number of users and the number of subscription months.

To support this type of sale, Project Operations introduced the concept of quantity factors. Quantity factors rely on the product attributes in Dynamics 365. When you configure specific properties for a product, Project Operations lets you flag a subset, or all of the properties, as quantity factors.

Project Operations validates that only numeric properties or product properties that have a numeric data type are flagged as quantity factors. When you add a product with quantity factors to a quote line, the **Quantity** field becomes read-only. After you enter values for product properties that are quantity factors, Project Operations calculates the quantity of the quote line.

For example, Dynamics 365 Sales might have the following properties:

- **No of users**: The number of users
- **No of Months**: The number of subscription months
- **Product SKU**

You can flag the **No of Users** and **No of Months** properties as quantity factors by editing the properties of the product line.

To create quantity factors from product properties, follow these steps:

1. On the Project Operations left navigation pane, go to **Sales** > **Products**.
1. Open the product for which you need to configure quantity factors. Make sure the product has properties already configured.
1. On the **Project Information** page for the product, select the **Quantity Factors** tab.
1. In the subgrid, select **+ New field computation**.
1. Enter the name of the quantity factor and select the property value that maps to the field computation.
1. Save and close the form. Repeat these steps for all properties to use for computing the quantity for the product-based quote line.

When you create a product-based quote line for a product, the quantity of the quote line is locked. The quantity is computed as a product of the property values that you input for that quote line.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
