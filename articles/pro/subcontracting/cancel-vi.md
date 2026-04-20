---
title: Cancel a project vendor invoice
description: Learn how to cancel a project vendor invoice in Microsoft Dynamics 365 Project Operations and understand the financial impact of reversing confirmed invoices.
author: rumant
ms.date: 01/30/2026
ms.topic: how-to
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak
ms.author: rumant
---

# Cancel a project vendor invoice

[!INCLUDE[banner](../../includes/banner.md)]

_**Applies To:** Project Operations Core_

After you confirm a vendor invoice, you can't edit or delete it. If you find an error on a confirmed vendor invoice, use the **Cancel** action to reverse the impact of the vendor invoice and create a new vendor invoice.

When you select **Cancel** on a vendor invoice, the following behavior occurs:

1. The state of the vendor invoice updates to **Canceled**.
1. The canceled vendor invoice and its related records become read-only. You can't edit or delete them.
1. The system reverses any cost actuals that the vendor invoice lines created during the confirmation of the vendor invoice.
1. If the matching process links any cost actuals to the vendor invoice lines, the original vendor invoice confirmation reverses them. During vendor invoice cancellation, the system re-creates those cost actuals. The origins point to the time, expense, or material usage entries.
1. After you cancel the vendor invoice, you can once again create correction journals, process time entry recalls, and cancel approval of the original time, expense, or material actuals.

> [!NOTE]
> You can only cancel confirmed project vendor invoices. You can't cancel vendor invoices in other states.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
