---
title: Product-based contract lines overview
description: This topic provides information about working with approvals in Project Operations.
author: rumant
manager: Annbe
ms.date: 10/07/2020
ms.topic: article
ms.service: dynamics-365-customerservice
ms.reviewer: kfend 
ms.author: rumant
---

# Product-based contract lines overview

_**Applies To:** Lite deployment - deal to proforma invoicing_


You can create product-based contract lines in Dynamics 365 Project Operations. Product-based contract lines can be manually created lines, or they can be items from the product catalog.

## Product catalog

The products in the product catalog have a default unit and unit group. If several products share the same set of attributes, you can create a product family that also has those attributes. All the products in one product family inherit the same set of attributes.

For example, a company sells subscription licenses for a variety of software. All subscription software has the following two attributes:

- Number of users
- Subscription duration (in months)

To maintain this type of catalog, create a product family that is named **Subscription Software** and add the attributes, **Number of users** and **Subscription duration**. Then add individual products to the **Subscription Software** product family.

## Add product catalog items to a project Contract

Project contracts and project contract pages have sections for two types of lines, project-based and product-based. For product-based lines, the drop-down list on the contract line or project contract line includes all products and units in the product price list on the contract or project contract. You can also add products that aren't part of contract's product price list.

Additionally, you can select products from other price lists, or directly from the product catalog. When you select products directly from a product catalog, the default price list of that product is used to get the product's sales price. If a default price list isn't set, the price is set to 0 (zero).

If a contract line is based on a product catalog, you can override the sales price directly on the line. A contract line has the **Pricing** field with the two values:

- **Override pricing**
- **Use default**

If you set the **Pricing** field to **Override pricing**, the default price is not set. You must enter a price for the product on the contract line. If you set the field to **Use default**, the default sales price is used and the field can't be edited.

After you install Project Operations, default sales prices are entered on the product-based lines on a contract. The **Pricing** field is set to **Override pricing** so that you can edit the default price on the contract lines. This is a Project Operations-specific override to product-based lines behavior in Dynamics 365 Sales.
