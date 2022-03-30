---
title: Cancel a project vendor invoice 
description: This topic explains how to cancel a project vendor invoice in Project Operations and the financial impact of canceling a vendor invoice.
author: rumant
ms.date: 03/30/2022
ms.topic: article
ms.reviewer: tonyafehr 
ms.author: rumant
---

# Cancel a project vendor invoice 

[!include [banner](../../includes/dataverse-preview.md)]

_**Applies To:** Lite deployment - deal to proforma invoicing_

Once a vendor invoice is confirmed, it cannot be edited or deleted. If there was an error on a vendor invoice that was confirmed, you can use the Cancel action to reverse the impact of the vendor invoice and create a new vendor invoice.

The following will be the behavior on clicking &quot;Cancel&quot; on a vendor invoice:

1. The status of the vendor invoice will be updated to &quot;Canceled&quot;.
2. A canceled vendor invoice and its related records will become read – only and cannot be edited or deleted.
3. Any cost actuals created as part of the confirmation of the vendor invoice based on vendor invoice lines will be reversed.
4. If there were any cost actuals that were linked to the VI Lines as part of the match process, the original vendor invoice confirmation would have reversed them. During vendor invoice cancellation, those cost actuals will be re-created with origins pointing to the time, expense or material usage entries.
5. Once a vendor invoice is cancelled, it will become possible to create Correction journals or process time entry recalls or cancel approval on the original time, expense or material actuals again.

>[!Note]
>Only confirmed project vendor invoices can be canceled. Vendor invoices in any other states cannot be canceled.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
