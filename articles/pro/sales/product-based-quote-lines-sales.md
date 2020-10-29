---
title: 
description: 
author: rumant
manager: Annbe
ms.date: 10/15/2020
ms.topic: article
ms.service: project-operations
ms.reviewer: kfend 
ms.author: rumant
---

# 

_**Applies To:** Lite deployment - deal to proforma invoicing_
# Product – based Quote lines

You can create product-based quote lines in Dynamics 365 Project Operations. Product-based quote lines can be &quot;write-in&quot; lines, or they can be items from the product catalog.

## Product catalog

The products in the Product catalog have a default unit and unit group. If several products share the same set of attributes, you can create a product family that also has those attributes. All the products in one product family inherit the same set of attributes.

For example, a company sells subscription licenses for a variety of software. All subscription software has the following two attributes:

- Number of users
- Subscription duration (in months)

A recommended way to maintain this type of catalog is to create a product family that is named Subscription Software, and that has Number of users and Subscription duration as attributes. You can then add individual products to the Subscription Software product family.

## Adding product catalog items to a project quote

Project quote and project contract pages have sections for two types of lines: project-based lines and product-based lines. For product-based lines, the drop-down list on the quote line or project contract line includes all the products and units in the &quot;Product price list&quot; on the quote or project contract. You can also add products that aren&#39;t part of quote&#39;s &quot;Product price list&quot;.

Additionally, you can select products from other price lists, or you can select products directly from the product catalog. When you select products directly from a product catalog, the default price list of that product is used to get the product&#39;s sales price. If a default price list isn&#39;t set, the price is set to 0 (zero).

If a quote line is based on a product catalog, you can override the sales price directly on the quote line. Note that a quote line in Dynamics 365 has a Pricing field. Two values are available:

- Override pricing
- Use default

If you set this field to Override pricing, Default price is not set. You must enter a price for the product on the quote line. If you set this field to Use default, default sales price is used and locks the field to prevent editing.

After you install Project Operations, default sales prices are entered on the product-based lines on a quote. The Pricing field is then set to Override pricing so that you can edit the default price on the quote lines. This is a Project Operations – specific override to product-based lines behavior that is in Dynamics 365 Sales solution.
