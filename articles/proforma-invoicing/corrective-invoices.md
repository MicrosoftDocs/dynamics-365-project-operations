---
# required metadata

title: Corrected invoices
description: This topic provides information about corrected invoices. 
author: rumant
manager: AnnBe
ms.date: 09/18/2020
ms.topic: article
ms.prod: 
ms.service: dynamics-project-operations
ms.technology: 

# optional metadata

# ms.search.form: 
# ROBOTS: 
audience: Application User
# ms.devlang: 
ms.reviewer: kfend
ms.search.scope: 
# ms.tgt_pltfrm: 
ms.custom: 
ms.assetid: 
ms.search.region: Global
ms.search.industry: Service industries
ms.author: suvaidya
ms.dyn365.ops.version: 
ms.search.validFrom: 2020-10-01
---

# Corrected invoices

_**Applies To:** Project Operations for resource/non-stocked based scenarios, Lite deployment - deal to proforma invoicing_

Confirmed invoices can be edited. When you edit a confirmed invoice, a draft of the corrected invoice is created. Because the assumption is that you want to reverse all the transactions and quantities from the original invoice, the corrected invoice includes all the transactions from the original invoice, and all the quantities on it are zero (0).

When transactions don't require correction, you can remove them from the draft corrective invoice. To reverse or return only a partial quantity, you can edit the Quantity field on the line detail. If you open the invoice line detail, you can see the original invoice quantity. You can then edit the current invoice quantity so that it's less than or more than the original invoice quantity.

When you confirm a corrective invoice, the original billed sales actual is reversed, and a new billed sales actual is created. If the quantity was reduced, the difference will cause a new unbilled sales actual to be created too. For example, if the original billed sale was for eight hours, and the corrected invoice line detail has a reduced quantity of six hours, the original billed sales line is revered and two new actuals are created:

- A billed sales actual for six hours.
- An unbilled sales actual for the remaining two hours. This transaction can either be billed later or marked as non-chargeable, depending on the negotiations with the customer.
