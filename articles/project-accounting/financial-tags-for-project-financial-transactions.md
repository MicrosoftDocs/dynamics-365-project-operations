---
title: Financial tags for project financial transactions
description: Learn about using financial tags for project transactions
author: ryansandness
ms.author: ryansandness
ms.date: 05/21/2025
ms.topic: overview
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak
---

# Financial tags for project financial transactions

## Overview

[!INCLUDE[banner](../includes/banner.md)]

_**Applies To:** Project Operations for resource/non-stocked based scenarios, Project Operations for stocked/production-based scenarios._

Financial tags let organizations track user-defined fields on accounting entries posted to the general ledger, eliminating the need to create financial dimensions that contain values that aren't reusable. Financial tags on posted transactions can then be used for reporting or analysis purposes. For example, you can create a financial tag to track time and expenses related to a short-lived initiative without requiring a unique financial dimension to do so.

## Feature details

Financial tags for Project-based transactions are now available starting with the 10.0.44 release. To enable this new functionality, enable the **Enable financial tags for project financial transactions** in the **Feature management** workspace.

Additional prerequisite features may be required for tags on certain transactions, such as **Enable financial tags for sales order invoicing** for sales orders and item requirement transactions and **Enable financial tags for purchase order invoicing** for purchase orders and vendor invoices.

For stocked/production-based scenarios, the following enhancements will be available:

- Financial tags are available to be entered on project sales orders and item requirements through a new Financial tags tab.
- Financial tags will be available for all four project journals through a new Financial tags tab control on the header and a new field available within journal lines.
- Financial tags are available to be entered for on-account transactions.
- The financial tags will be present in the financial voucher posting for the document where possible.
- The financial tags will carry forward into the voucher for the project invoice.
- Accrue Revenue will carry the tag forward.

For resource/non-stocked based scenarios, the following enhancements will be available:

- Financial tags will be available on the integration journal for hours, expenses, fees, and materials through a new Financial tags tab control on the header and a new field available within journal lines.
- The financial tags will be present in the financial voucher posting for the document.
- The financial tags will carry forward into the voucher for the project invoice.

### Example scenario

Contoso is participating in an industry event and wants to track all time and expenses related to this event. To accomplish this they create a new financial tag named IndustryEvent with a tag value of “2026 Event”. For any time or expenses related to this event the tag will be manually specified on the transaction line. After the event is over and all expenses are recorded, the financial tag will be removed and further use will not be allowed.

1. Hour journals and expenses are created and the financial tag is added on the relevant transactions prior to submission to workflow or posting.

2. When the transaction lines are posted, the financial tag is applied to the general ledger voucher.

3. Then when the transactions are invoiced, the financial tags carry forward into the voucher for the invoice as well. All transactions that use this tag can be viewed at once through the general ledger **Voucher transactions** page or the **Accounting Source Explorer** page.

## Other financial tag functionality available for project but not enabled by this feature

- Financial tags can be entered on the Free text invoice for project-related transactions
- Financial tags can be entered on project-related purchase orders and vendor invoices
