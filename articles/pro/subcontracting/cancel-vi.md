---
title: Cancel a project vendor invoice
description: This article explains how to cancel a project vendor invoice in Microsoft Dynamics 365 Project Operations and the financial impact of canceling a project vendor invoice.
author: rumant
ms.date: 12/15/2023
ms.topic: how-to
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak
ms.author: rumant
---

# Cancel a project vendor invoice

[!INCLUDE[banner](../../includes/banner.md)]

_**Applies To:** Project Operations Core_

After a vendor invoice is confirmed, it can't be edited or deleted. If there was an error on a vendor invoice that was confirmed, you can use the Cancel action to reverse the impact of the vendor invoice and create a new vendor invoice.

When you select **Cancel** on a vendor invoice, the following behavior occurs:

1. The state of the vendor invoice is updated to **Canceled**.
2. The canceled vendor invoice and its related records become read-only, and can't be edited or deleted.
3. Any cost actuals that were created based on vendor invoice lines as part of the confirmation of the vendor invoice are reversed.
4. If any cost actuals were linked to the vendor invoice lines as part of the matching process, the original vendor invoice confirmation reversed them. During vendor invoice cancellation, those cost actuals are re-created. The origins point to the time, expense, or material usage entries.
5. After the vendor invoice is canceled, you can once again create correction journals, process time entry recalls, and cancel approval of the original time, expense, or material actuals.

> [!NOTE]
> Only confirmed project vendor invoices can be canceled. Vendor invoices in other states can't be canceled.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
