---
title: Product-based contract lines overview - Project Operations Core
description: This article provides information about product-based contract lines.
author: poojafandan
ms.date: 06/07/2024
ms.topic: overview
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak
ms.author: poojafandan

---

# Product-based contract lines overview - Project Operations Core

[!INCLUDE[banner](../../includes/banner.md)]

_**Applies To:** Project Operations Core_

You can create product-based contract lines in Dynamics 365 Project Operations. Product-based contract lines can be manually created lines, or they can be items from the product catalog.

## Product catalog

The products in the product catalog have a default unit and unit group. If several products share the same set of attributes, you can create a product family that also has those attributes. All the products in one product family inherit the same set of attributes.

For example, a company sells subscription licenses for different kinds of software. All subscription software has the following two attributes:

- Number of users
- Subscription duration (in months)

To maintain this type of catalog, create a product family that is named **Subscription Software**. Add the attributes, **Number of users** and **Subscription duration** to the product family. Then, add individual products to the **Subscription Software** product family.

## Add product catalog items to a project Contract

Project contracts have sections for two types of lines, project-based and product-based. Product-based lines include all of the products and units in the product price list on the contract. Products that aren't part of contract's product price list can be added.

You can select products from other price lists, or directly from the product catalog. When you select products directly from a product catalog, the default price list of that product is used for the product's sales price. If a default price list isn't set, the price is set to 0 (zero).

If a contract line is based on a product catalog, you can override the sales price directly on the line. A contract line has the **Pricing** field with the two values:

- **Override pricing**
- **Use default**

If you set the **Pricing** field to **Override pricing**, the default price isn't set. Enter a price for the product on the contract line. If you set the field to **Use default**, the default sales price is used and the field can't be edited.

After you install Project Operations, default sales prices are entered on the product-based lines on a contract. The **Pricing** field is set to **Override pricing** so that you can edit the default price on the contract lines. This is a Project Operations-specific override to product-based lines behavior in Dynamics 365 Sales.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
