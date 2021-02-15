---
title: Resource estimates
description: This topic provides information about how resource estimates are calculated in Project Operations.
author: ruhercul
manager: Annbe
ms.date: 10/01/2020
ms.topic: article
ms.service: project-operations
ms.reviewer: kfend 
ms.author: ruhercul
---

# Resource estimates

_**Applies To:** Project Operations for resource/non-stocked based scenarios, Lite deployment - deal to proforma invoicing_

Resource estimates come from time-phased effort that is defined in the work breakdown structure along with applicable pricing dimensions. Typically, the calculation is **rate/hr for each role x hours.** The time-phased effort for each resource is stored in the resource assignment record. The pricing is stored in a pre-defined price list. Unit conversion is applied based on the applicable price list.

![Resource Estimates](./media/navigation12.png)

## Default cost price and cost currency

Cost prices are defaulted from the Organizational Unit.

## Default bill rate and sales currency

Sales prices are applied once per deal. The hierarchy for sale price list defaulting is as follows:

1. Organization
2. Customer
3. Quote/contract


[!INCLUDE[footer-include](../includes/footer-banner.md)]