---
title: Managing vendors and Purchase Price Lists in Project Operations 
description: This topic covers the creation and maintenance of Vendor data and Purchase Price Lists to be used in the context of Subcontracting in Project Operations.
author: rumant
ms.date: 07/28/2021
ms.topic: article
ms.reviewer: kfend 
ms.author: rumant
---

# Managing vendors and Purchase Price Lists in Project Operations

_**Applies To:** Lite deployment - deal to proforma invoicing_

## Vendors in Project Operations

Vendors in Project Operations are accounts where relationship type is &quot;Vendor&quot; or &quot;Supplier&quot;. All other relationship type values (including blank value) on an Account record do not allow the account to be selected as vendor on a Subcontract.

All references to &quot;Vendor&quot; in Project Operations User Interface and in product documentation should deemed to refer to an account record where the relationship type is &quot;Vendor&quot; or &quot;Supplier&quot;.

On vendor record in Project Operations, you can associate one or more Purchase price lists. However, all purchase price lists attached to a vendor record should have distinct date effectivities. Overlapping date-effectivities for purchase price lists is not supported by Project Operations.

The following fields and concepts on the vendor record will default on a Subcontract that is created for this vendor:

1. Payment terms
2. Bill To contact
3. Primary contact of the vendor is defaulted on the Subcontract as the Vendor Account Manager
4. Currency
5. Purchase price lists that are current

## Purchase price lists in Project Operations

A price list that has the Context field set to &quot;Purchase&quot; is considered a Purchase Price list. Purchase price list can be defined to represent a catalog of purchase rates for Time, Expense and Materials. A Purchase price list has a lot of similarities with Cost and Sales price lists in Project Operations. Below are a list concepts that apply to Purchase price lists in the same way as they apply to Cost and Sales price lists:

1. Date effectivity: Like cost and sales price lists, Purchase price lists also have a date effectivity represented by Start and End date fields on the price list. The period between start and end dates is the period
2. Currency: The currency on the price list header is used as the currency in which purchase prices are expressed for Labor (role prices), Expense Category prices (Category prices), Products in the catalog (Price List Items)
3. Default time unit: This is used as the default unit of time in which Labor prices for purchase are expressed. The time unit field on the Price List is only used for defaulting and can be changed on individual Role prices rows.

Vendor-specific Purchase Price Lists:

Purchase price lists can be attached to Vendor records as associations called Project Price lists. When attached to a vendor record, the most current among them will be defaulted on Subcontracts that are created for the vendor. These project price lists are then used for defaulting prices on Subcontract lines. Only purchase price lists that have the context field set to &quot;Purchase&quot; can be attached to Vendor records

### Subcontract-specific Purchase Price Lists:

Purchase price lists can be attached to Subcontracts as associations called Project Price lists. Purchase price lists attached to a Subcontract record are used for defaulting prices on Subcontract lines. When a Subcontract has multiple purchase price lists attached, they need to have distinct date effectivities. Purchase prices with overlapping date effectivities are not supported in Project Operations. Only purchase price lists that have the context field set to &quot;Purchase&quot; can be attached to Subcontracts.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
