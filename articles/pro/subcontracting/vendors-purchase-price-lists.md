---
title: Vendor and purchase price list management in Project Operations
description: Learn how to create and maintain vendor data and purchase price lists in Project Operations. Optimize subcontracting with clear pricing strategies.
author: rumant
ms.date: 02/04/2026
ms.topic: concept-article
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak
ms.author: rumant
---

# Vendor and purchase price list management in Project Operations

[!INCLUDE[banner](../../includes/banner.md)]

_**Applies To:** Project Operations Core_

## Vendors in Project Operations

In Microsoft Dynamics 365 Project Operations, vendor accounts have a relationship type of **Vendor** or **Supplier**. You can select only an account record that has one of these relationship types as a vendor on a subcontract.

You can associate one or more purchase price lists with a vendor record. However, each purchase price list that you associate with a vendor record should have distinct date effectivity. Project Operations doesn't support overlapping date effectivity for purchase price lists.

By default, the following fields and concepts on a vendor record are used for any subcontract that you create for the vendor:

- Payment terms
- Bill to contact
- Primary contact

    > [!NOTE]
    > By default, the primary contact of the vendor is used as the vendor account manager of the subcontract.

- Currency
- Current purchase price lists

## Purchase price lists in Project Operations

A price list where you set the **Context** field to **Purchase** is a purchase price list. Define purchase price lists to represent a catalog of purchase rates for time, expenses, and materials. Purchase price lists resemble cost and sales price lists in Project Operations. The following concepts apply to purchase price lists in the same way that they apply to cost and sales price lists:

- **Date effectivity** – Purchase price lists have date effectivity. The start date and end date fields on each price list represent date effectivity. The time between the start date and end date is the date effective period.
- **Currency** – The currency on the price list header is the currency that purchase prices are expressed in for labor, expense categories, and products in the catalog.
- **Default time unit** – The default time unit expresses labor prices for purchases. The time unit field on a price list only provides a default value. You can change that value on individual role price rows.

Attach purchase price lists to vendor records as associations known as project price lists. Use these price lists to enter default prices on subcontract lines. By default, when you attach multiple purchase price lists to a vendor record, the most current price list is used for subcontracts that you create for the vendor. You can only attach price lists where the **Context** field is set to **Purchase** to vendor records.

### Subcontract-specific purchase price lists

Attach purchase price lists to subcontracts as associations known as project price lists. Use these price lists to enter default prices on subcontract lines. By default, when you attach multiple purchase price lists to a subcontract, each price list must have distinct date effectivity. Project Operations doesn't support purchase price lists that have overlapping date effectivity. You can only attach price lists where the **Context** field is set to **Purchase** to subcontracts.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
