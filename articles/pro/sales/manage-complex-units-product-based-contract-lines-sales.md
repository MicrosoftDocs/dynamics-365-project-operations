---
title: Manage complex units for product-based contract lines - lite
description:  This article provides information about supporting the sale of subscription-based products.
author: poojafandan
ms.date: 06/10/2024
ms.topic: how-to
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak
ms.author: poojafandan
---


# Manage complex units for product-based contract lines - lite

[!INCLUDE[banner](../../includes/banner.md)]

_**Applies To:** Core deployment - deal to proforma invoicing_

Dynamics 365 Project Operations uses quantity factors to support the sale of subscription-based products. For subscription-based products, the quantity on the contract or project contract line is expressed as the number of user-months.

The price of subscription software is stored in the catalog as the price per-user, per-month. During the sales process, the price on the contract line is usually the per-user, per-month price that was negotiated and discounted by the sales agent. Each deal has a different number of users and a different number of subscription months. The quantity used to calculate the amount of the contract line is a product of the number of users and the number of subscription months.

To support this type of sale, Project Operations supports the concept of *quantity factors*. Quantity factors rely on product attributes. When you configure specific properties for a product, you can flag a subset of those properties, or all the properties, as quantity factors.

Project Operations validates that only numeric properties or product properties that have a numeric data type are flagged as quantity factors. When a product with configured quantity factors is added to a contract line, the **Quantity** field  becomes read-only. After you enter values for product properties that are quantity factors, Project Operations calculates the quantity of the contract line.

For example, Dynamics 365 Sales might have the following properties:

- **No of users**: The number of users.
- **No of Months**: The number of subscription months.
- **Product SKU**: The stock keeping unit (SKU) for the product.

The **No of Users** and **No of Months** properties can be flagged as quantity factors by editing the properties of the product line.

To create quantity factors from product properties, complete the following steps.

1. On the **Project Operations**, select **Sales-Products**.
2. Open the product for which you need to set up quantity factors. Make sure that the product has properties already set up.
3. On the **Project Information** page, select the **Quantity Factors** tab.
4. In the subgrid, select **+ New field computation**.
5. Enter the name of the **Quantity Factor** and select the property value that maps to the field computation.
6. Save and close the form.
7. Repeat steps 2-6 for all the properties that together will make up the quantity for the product-based contract line.

With quantity factors set up, when the user creates a contract line for this product, the quantity of the contract line is locked. The quantity is then calculated as a product of the property values for that contract line.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
