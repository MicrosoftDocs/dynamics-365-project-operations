---
title: Confirm a project vendor invoice 
description: This topic explains how to confirm a project vendor invoice and the financial impact of confirming a project vendor invoice.
author: rumant
ms.date: 03/30/2022
ms.topic: article
ms.reviewer: tonyafehr 
ms.author: rumant
---

# Confirm a project vendor invoice

[!include [banner](../../includes/dataverse-preview.md)]

_**Applies To:** Lite deployment - deal to proforma invoicing_


Once you have verified all the lines on a vendor invoice in Project Operations, you can use the Confirm action to confirm the vendor invoice. The following will be the behavior on clicking &quot;Confirm&quot; on a vendor invoice:

1. The status of the vendor invoice will be updated to &quot;Confirmed&quot;.
2. A confirmed vendor invoice and its related records will become read – only and cannot be edited or deleted.
3. If there are cost actuals that reference this VI Line as part of the match process, all cost actuals associated with the vendor invoice line reference will be reversed.
4. New cost actuals will be created using the information on the vendor invoice line.
5. It will no longer be possible to create Correction journals or process time entry recalls or cancel approval on the original time, expense or material actuals that were reversed.

> [!Note]
> If any of the lines on a vendor invoice have verification status that is not Complete, then the vendor invoice cannot be confirmed.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
