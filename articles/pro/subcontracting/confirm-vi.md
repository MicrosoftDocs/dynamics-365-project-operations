---
title: Confirm a project vendor invoice
description: Learn how to confirm a project vendor invoice in Microsoft Dynamics 365 Project Operations and understand its financial impact. Follow this step-by-step guide.
author: rumant
ms.date: 01/30/2026
ms.topic: how-to
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak
ms.author: rumant
---

# Confirm a project vendor invoice

[!INCLUDE[banner](../../includes/banner.md)]

_**Applies To:** Project Operations Core_

After you verify all the lines on a vendor invoice in Microsoft Dynamics 365 Project Operations, use the Confirm action to confirm the vendor invoice.

When you select **Confirm** on a vendor invoice, the following actions occur:

1. The state of the vendor invoice updates to **Confirmed**.
1. The confirmed vendor invoice and its related records become read-only. You can't edit or delete them.
1. If any cost actuals reference the vendor invoice line as part of the matching process, all cost actuals that are associated with the referenced vendor invoice line are reversed.
1. New cost actuals are created by using the information on the vendor invoice line.
1. After you confirm the vendor invoice, you can no longer create correction journals, process time entry recalls, or cancel approval of the original time, expense, or material actuals that were reversed.

> [!NOTE]
> If any line on a vendor invoice has a verification status other than **Complete**, you can't confirm the vendor invoice.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
