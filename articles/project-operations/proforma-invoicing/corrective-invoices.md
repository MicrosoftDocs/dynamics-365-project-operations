---
# required metadata

title: Corrective invoices
description:  
author: rumant
manager: AnnBe
ms.date: 08/17/2020
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

# Corrective invoices

Confirmed invoices in Project operations can be edited (corrected). When you correct a confirmed invoice, a new draft corrective invoice is created. Because the assumption is that you want to reverse all the transactions and quantities from the original invoice, this corrective invoice includes all the transactions from the original invoice, and all the quantities on it are zero (0).

If any transactions don't require correction, you can remove them from the draft corrective invoice. If you want to reverse or return only a partial quantity, you can edit the Quantity field on the line detail. If you open the invoice line detail, you can see the original invoice quantity. You can then edit the current invoice quantity so that it's less than or more than the original invoice quantity.

When you confirm a corrective invoice, the original billed sales actual is reversed, and a new billed sales actual is created. If the quantity was reduced, the difference will cause a new unbilled sales actual to be created too. For example, if the original billed sales was for eight hours, and the corrective invoice line detail has a reduced quantity of six hours, PSA reverses the original billed sales line and creates two new actuals:

A billed sales actual for six hours.
An unbilled sales actual for the remaining two hours. This transaction can either be billed later or marked as non-chargeable, depending on the negotiations with the customer.
