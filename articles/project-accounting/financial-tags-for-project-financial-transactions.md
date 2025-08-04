---
title: Use financial tags for project financial transactions
description: Learn how you can use financial tags for project transactions.
author: ryansandness
ms.author: ryansandness
ms.date: 08/04/2025
ms.topic: overview
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak
---

# Use financial tags for project financial transactions

[!INCLUDE[banner](../includes/banner.md)]

_**Applies To:** Project Operations Integrated with ERP, Project Operations for manufacturing._

Financial tags enable organizations to track user-defined fields on accounting entries that are posted to the general ledger. Therefore, they don't have to create financial dimensions that contain values that aren't reusable. Financial tags on posted transactions can be used for reporting or analysis.

For example, you can create a financial tag to track time and expenses that are related to an initiative of short duration. You don't have to use a unique financial dimension for this purpose.

## Feature details

Financial tags for project-based transactions are available as of the 10.0.44 release. To use them, enable the **Enable financial tags for project financial transactions** feature in the **Feature management** workspace.

In addition, some transactions might require other features as prerequisites before financial tags can be used. For example, sales orders and item requirement transactions require the **Enable financial tags for sales order invoicing** feature, and purchase orders and vendor invoices require the **Enable financial tags for purchase order invoicing** feature.

For Project Operations for manufacturing, the following enhancements are available:

- Financial tags can be entered on the **Financial tags** tab of project sales orders and item requirements.
- Financial tags are available on the **Financial tags** tab on the header of all four project journals. Financial tags are also available in a new field on journal lines.
- Financial tags can be entered for on-account transactions.
- Financial tags are present in the financial voucher posting for the document, whenever possible.
- Financial tags are carried forward into the voucher for the project invoice.
- Accrue Revenue carries financial tags forward.

For Project Operations Integrated with ERP based scenarios, the following enhancements are available:

- Financial tags are available on the **Financial tags** tab on the header of the integration journal for hours, expenses, fees, and materials. Financial tags are also available in a new field on journal lines.
- Financial tags are present in the financial voucher posting for the document.
- Financial tags are carried forward into the voucher for the project invoice.
- With the 10.0.45 release, the financial tags from a vendor invoice now carry forward onto the integration journal.
- On-account transactions are also supported for financial tags.

### Example scenario

Contoso is participating in an industry event and wants to track all time and expenses that are related to the event. Therefore, a new **IndustryEvent** financial tag is created, and a tag value of **2026 Event** is assigned. For any time or expenses that are related to the event, the tag is manually specified on the transaction line. After the event is over, and all expenses are recorded, the financial tag is removed and can no longer be used.

1. Hour journals and expenses are created, and the financial tag is added on the relevant transactions before submission to the workflow or posting.
1. When the transaction lines are posted, the financial tag is applied to the general ledger voucher.
1. When the transactions are invoiced, the financial tags carry forward into the voucher for the invoice. All transactions that use a tag can be viewed through the general ledger **Voucher transactions** page or the **Accounting Source Explorer** page.

## Other financial tag functionality that is available for projects but not enabled by this feature

- Financial tags can be entered on the free text invoice for project-related transactions.
- Financial tags can be entered on project-related purchase orders and vendor invoices.

## Financial tag rules

[Financial tag rules](/dynamics365/finance/general-ledger/financial-tag-defaulting) can be used to automatically apply tags onto a transaction. Project specific documents that support tagging include:

|Document  |Minimum version  |
|---------|---------|
|Project expense journal     |10.0.45         |
|Project fee journal     |10.0.45          |
|Project hour journal     |10.0.45          |
|Project item journal     |10.0.45          |

[!INCLUDE[footer-include](../includes/footer-banner.md)]
