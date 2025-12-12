---
title: Confirm a project vendor invoice
description: This article explains how to confirm a project vendor invoice in Microsoft Dynamics 365 Project Operations and the financial impact of confirming a project vendor invoice.
author: rumant
ms.date: 12/15/2023
ms.topic: how-to
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak
ms.author: rumant
---

# Confirm a project vendor invoice

[!INCLUDE[banner](../../includes/banner.md)]

_**Applies To:** Project Operations Core_

After you've verified all the lines on a vendor invoice in Microsoft Dynamics 365 Project Operations, you can use the Confirm action to confirm the vendor invoice.

When you select **Confirm** on a vendor invoice, the following behavior occurs:

1. The state of the vendor invoice is updated to **Confirmed**.
2. The confirmed vendor invoice and its related records become read-only, and can't be edited or deleted.
3. If any cost actuals reference the vendor invoice line as part of the matching process, all cost actuals that are associated with the referenced vendor invoice line are reversed.
4. New cost actuals are created by using the information on the vendor invoice line.
5. After the vendor invoice is confirmed, you can no longer create correction journals, process time entry recalls, or cancel approval of the original time, expense, or material actuals that were reversed.

> [!NOTE]
> If any line on a vendor invoice has a verification status other than **Complete**, the vendor invoice can't be confirmed.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
