---
title: Confirm project vendor invoices
description: This article explains how to confirm a project vendor invoice in Microsoft Dynamics 365 Project Operations and describes the financial impact of confirming a project vendor invoice.
author: mukumarm
ms.author: mukumarm
ms.date: 05/24/2024
ms.topic: how-to
ms.reviewer: johnmichalak

---

# Confirm project vendor invoices

_**Applies To:** Project Operations for resource/non-stocked based scenarios

When the **Manual confirmation by PM is required** parameter is enabled, vendor invoices that are created in Microsoft Dataverse have **Draft** status. Vendor invoices that are created in this way must be reviewed and manually confirmed. When the **Manual confirmation by PM is required** parameter is disabled, vendor invoices that are created in Dataverse are automatically confirmed. No further action is required. 

After you've verified all the lines on a vendor invoice in Dynamics 365 Project Operations, select **Confirm** to confirm the vendor invoice.

When you select **Confirm** on a vendor invoice, the following behavior occurs:

1. The status of the vendor invoice is updated to **Confirmed**.
1. The confirmed vendor invoice and its related records become read-only, and can't be edited or deleted.
1. If any cost actuals reference the vendor invoice line as part of the matching process, all cost actuals that are associated with the referenced vendor invoice line are reversed.
1. New cost actuals are created by using the information on the vendor invoice line.
1. You can no longer create correction journals, process recalls of time entries, or cancel the approval of original time, expense, or material actuals that were reversed.
1. In Dynamics 365 Finance, the **Project cost** value is updated by using the Project integration journal, and the Procurement integration account is *reversed* after the Project integration journal is posted.

> [!NOTE]
> If any line on a vendor invoice has a verification status other than **Complete**, the vendor invoice can't be confirmed.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
