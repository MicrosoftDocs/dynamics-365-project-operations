---
title: Managing vendors and purchase price lists in Project Operations 
description: This topic explains how to create and maintain vendor data and purchase price lists for subcontracting.
author: rumant
ms.date: 08/02/2021
ms.topic: article
ms.reviewer: kfend 
ms.author: rumant
---

# Managing vendors and purchase price lists in Project Operations

_**Applies To:** Lite deployment - deal to proforma invoicing_

## Vendors in Project Operations

In Dynamics 365 Project Operations, vendors accounts have the relationship type **Vendor** or **Supplier**. You can only select an account record with these relationship types as a vendor on a subcontract.

You can associate one or more purchase price lists to a vendor record. However, all purchase price lists associated with a vendor record should have distinct date effectivities. Overlapping date-effectivities for purchase price lists isn't supported by Project Operations.

The following fields and concepts on the vendor record default on any subcontract that's created for the vendor:

   - Payment terms
   - Bill to contact
   - The primary contact of the vendor defaults on the subcontract as the Vendor Account Manager
   - Currency
   - Current purchase price lists 

## Purchase price lists in Project Operations

A price list that has the **Context** field set to **Purchase** is considered a purchase price list. Purchase price lists can be defined to represent a catalog of purchase rates for Time, Expense, and Materials. A purchase price list is similar to cost and sales price lists in Project Operations. The following concepts apply to purchase price lists in the same way as they apply to cost and sales price lists:

  - Date effectivity: Purchase price lists have date effectivity that is represented by start and end date fields on the price list. The time between the start and end dates is the date effective period.
  - Currency: The currency on the price list header is used as the currency in which purchase prices are expressed for labor, expense category, and products in the catalog.
  - Default time unit: The default time unit expresses labor prices for purchases. The time unit field on the price list is only used for default and can be changed on individual role prices rows.

Purchase price lists can be attached to vendor records as associations called project price lists. When attached to a vendor record, the most current project price list defaults on subcontracts that are created for the vendor. These project price lists are used to default prices on subcontract lines. Only purchase price lists that have the **Context** field set to **Purchase** can be attached to vendor records.

### Subcontract-specific purchase price lists

Purchase price lists can be attached to subcontracts as associations called, project price lists. Purchase price lists attached to a subcontract record are used to default prices on subcontract lines. When a subcontract has multiple purchase price lists attached, each list must have distinct date effectivities. Purchase prices with overlapping date effectivities aren;t supported in Project Operations. Only purchase price lists that have the **Context** field set to **Purchase** can be attached to subcontracts.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
