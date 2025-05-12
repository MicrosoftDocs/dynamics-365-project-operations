---
title: Financial tags for project financial transactions
description: Learn about using financial tags for project transactions
author: ryansandness
ms.author: ryansandness
ms.date: 05/15/2025
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

Financial tags for Project-based transactions are now available starting with the 10.0.44 release. To enable this new functionality, enable the **Enable financial tags for project fincancials transactions** in the **Feature management** workspace.

For stocked/production-based scenarios: the following enhancements will be available:

- Financial tags are available to be entered on project sales orders and item requirements through a new Financial tags tab.
- Financial tags will be available for all four project journals through a new Financial tags tab control on the header and a new field available within journal lines.
•	On-account
- Financial tags will be available on the free text invoice through a new Financial tags tab control on the header and a new field available within invoice lines.
•	Financial tags will be available on the Purchase Order and Vendor Invoice forms. 
•	The financial tags will be present in the financial voucher posting for the document. 
•	The financial tags will carry forward into the voucher for the project invoice. 
•	Post costs will carry the tag forward
•	Accrue Revenue will carry the tag forward


For resource/non-stocked based scenarios: the following enhancements will be available:

## Example scenario

Contoso is participating in an industry event and wants to track all  time and expenses related to this event. To accomplish this they create a new financial tag named IndustryEvent with a tag value of “2026 Event”. For any time or expenses related to this event the tag will be manually specified on the transaction line. After the event is over and all expenses are recorded, the financial tag will be removed and further use will not be allowed.
Timesheets and expenses are created and the financial tag is added on the line. When the lines are posted, the financial tag is applied to the transaction lines. Then when the transactions are invoiced, the financial tags carry forward into the voucher for the invoice as well. All transactions that use this tag can be viewed at once through the general ledger **voucher transactions** page or the **Accounting Source Explorer** page.
