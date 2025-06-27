---
title: Product-based quote lines overview
description: This article provides information about working with product-based quote lines.
author: poojafandan
ms.date: 06/07/2024
ms.topic: overview
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak
ms.author: poojafandan

---

# Product-based quote lines overview

[!INCLUDE[banner](../../includes/banner.md)]

_**Applies To:** Core deployment - deal to proforma invoicing_

You can create product-based quote lines in Dynamics 365 Project Operations. Product-based quote lines can be manually added, or they can be items from the product catalog.

## Product catalog

Each product in the product catalog has a default unit and unit group. If multiple products share the same set of attributes, you can create a product family that share those attributes. 

For example, a company sells subscription licenses for different kinds of software. All subscription software has the following two attributes:

- Number of users
- A subscription duration measured in months

To maintain this type of catalog, create a product family named **Subscription Software** and add the number of users and the subscription duration as attributes. Next, you can add individual products to the **Subscription Software** product family.

## Add product catalog items to a project quote

The **Project Quote** and **Project Contract** pages have sections for project-based lines and product-based lines. For product-based lines, the drop-down list on the quote line or project contract line includes all the products and units in the product price list. You can also add products that aren't part of the product price list.

Additionally, you can select products from other price lists or directly from the product catalog. When you select products directly from a product catalog, the default price list of that product is used to get the product's sales price. If a default price list isn't set, the price is set to zero (0).

When a quote line is based on a product catalog, you can override the sales price directly on the quote line. A quote line in **Pricing** field with two available values:

- **Override Pricing**
- **Use Default**

If you select **Override Pricing**, the default price isn't set. Instead, you must enter a price for the product on the quote line. If you select **Use Default**, the default sales price is used and the field is locked for editing.

Default sales prices are entered on the product-based lines of a quote. The **Pricing** field is then set to **Override Pricing** so that you can edit the default price on the quote lines. This is a Project Operations-specific override to the product-based lines behavior in Dynamics 365 Sales.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
