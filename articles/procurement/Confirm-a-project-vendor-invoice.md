---
title: Confirm a project vendor invoice
description: This article explains how to confirm a project vendor invoice in Microsoft Dynamics 365 Project Operations and the financial impact of confirming a project vendor invoice.
author: suvaidya
ms.date: 8/25/2022
ms.topic: article
ms.reviewer: johnmichalak
ms.author: suvaidya
---

# Confirm a project vendor invoice

_**Applies To:** Project Operations for resource/non-stocked based scenarios

When the **Manual confirmation by PM is required** parameter is enabled, the vendor invoice is created in Microsoft Dataverse with a draft status. Vendor invoices created in this way must be reviewed and confirmed manually.When the **Manual confirmation by PM is required**parameter is disabled, vendor invoices are created in Dataverse are auto-confirmed and no further action is needed. 

After you have verified all the lines on a vendor invoice in Microsoft Dynamics 365 Project Operations, select **Confirm** to confirm the vendor invoice.

When you select **Confirm** on a vendor invoice, the following behavior occurs:

1. The state of the vendor invoice is updated to **Confirmed**.
1. The confirmed vendor invoice and its related records become read-only, and can't be edited or deleted.
1. If any cost actuals reference the vendor invoice line as part of the matching process, all cost actuals that are associated with the referenced vendor invoice line are reversed.
1. New cost actuals are created by using the information on the vendor invoice line.
1. After the vendor invoice is confirmed, you can no longer create correction journals, process time entry recalls, cancel approval of the original time, expense, or material actuals that were reversed.
1. **Project cost** is updated in Finance using the **Project integration journal** and the **Procurement integration account** gets **reversed** once the **project integration journal** is posted.


> [!NOTE]
> If any line on a vendor invoice has a verification status other than **Complete**, the vendor invoice can't be confirmed.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
