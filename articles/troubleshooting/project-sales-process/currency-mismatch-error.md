---
title: Currency mismatch error 
description: This article provides troubleshooting information about a currency mismatch error that occurs when you save specific record types.
author: mukumarm
ms.author: mukumarm
ms.date: 05/22/2024
ms.topic: troubleshooting
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak

---

# Currency mismatch error 

_**Applies To:** Project Operations Integrated with ERP_

When you save a project, contract, quote, or bookable resource, you might receive the error, **Owning company currency does not match the contracting unit currency. Pick different owning company or contracting unit to continue**. This is because there is a currency mismatch between the contracting unit currency for the record and the owning company currency.


## Resolution

To work around this issue, do the following:
- Verify the currency of the contracting unit for this record. You can see the currency by opening the organizational unit record and verifying the value on the **General** tab in the **Currency** field.
- Verify the currency of the owning company. You can see the currency by going to **Related** > **Ledgers** in the company record. Double-click the ledger record that is associated with the company and verify the value on the **General** tab in the **Accounting currency** field.

If the currency set in the contracting unit and the ledger record do not match, adjust the configuration or select different values when you save the record. The system requires these records to match to ensure correct intercompany invoicing flows. For more information about the intercompany configurations, see [Create intercompany transactions](../../project-accounting/create-intercompany-transactions.md).

If the company record has no associated ledger record, this indicates that there is a missing configuration when setting up the environment. The configuration must be corrected by the system administrator. The system administrator must go to **Dual-write configurations** and stop and restart **Ledgers dual-write map** with the initial sync of this map and it's prerequisites. For more information, see [Project Operations dual-write map versions](../../environment/resource-dual-write-maps.md).
