---
title: Vendor and purchase price list management in Project Operations
description: This article provides information that will help you create and maintain vendor data and purchase price lists for subcontracting.
author: rumant
ms.date: 12/15/2023
ms.topic: article
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

You can associate one or more purchase price lists with a vendor record. However, each purchase price list that is associated with a vendor record should have distinct date effectivity. Project Operations doesn't support overlapping date effectivity for purchase price lists.

By default, the following fields and concepts on a vendor record are used for any subcontract that is created for the vendor:

- Payment terms
- Bill to contact
- Primary contact

    > [!NOTE]
    > By default, the primary contact of the vendor is used as the vendor account manager of the subcontract.

- Currency
- Current purchase price lists

## Purchase price lists in Project Operations

A price list where the **Context** field is set to **Purchase** is considered a purchase price list. Purchase price lists can be defined to represent a catalog of purchase rates for time, expenses, and materials. Purchase price lists resemble cost and sales price lists in Project Operations. The following concepts apply to purchase price lists in the same way that they apply to cost and sales price lists:

- **Date effectivity** – Purchase price lists have date effectivity. Date effectivity is represented by start date and end date fields on each price list. The time between the start date and end date is the date effective period.
- **Currency** – The currency on the price list header is used as the currency that purchase prices are expressed in for labor, expense categories, and products in the catalog.
- **Default time unit** – The default time unit expresses labor prices for purchases. The time unit field on a price list is used only to provide a default value. That value can be changed on individual role price rows.

Purchase price lists can be attached to vendor records as associations that are known as project price lists. These price lists are used to enter default prices on subcontract lines. By default, when multiple purchase price lists are attached to a vendor record, the most current price list is used for subcontracts that are created for the vendor. Only  price lists where the **Context** field is set to **Purchase** can be attached to vendor records.

### Subcontract-specific purchase price lists

Purchase price lists can also be attached to subcontracts as associations that are known as project price lists. These price lists are used to enter default prices on subcontract lines. By default, when multiple purchase price lists are attached to a subcontract, each must have distinct date effectivity. Project Operations doesn't support purchase price lists that have overlapping date effectivity. Only price lists where the **Context** field is set to **Purchase** can be attached to subcontracts.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
