---
title: Advances and retainer-based contracts
description: This article provides information about retainer-based contracting models and advances in Project Operations.
author: poojafandan
ms.date: 02/26/2026
ms.topic: concept-article
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak
ms.author: poojafandan
---

# Advances and retainer-based contracts

[!INCLUDE[banner](../../includes/banner.md)]

_**Applies To:** Project Operations Integrated with ERP, Project Operations Core_

Dynamics 365 Project Operations supports retainer-based contracts. A retainer-based contract is a negotiated set of equally distributed payments that the customer pays throughout the duration of a project. Typically, use this type of contract for time and material or consumption-based billing models when you need to give the customer a predictable invoice and payment schedule. Reconcile revenue actuals accrued each period against the payment received from the customer at the beginning of the period. In accordance with the concept of the Time and Material billing model, revenue values accrued in each period can vary with the costs incurred. If the revenue accrued is more than the amount received at the beginning of the period, the project delivery company can:

- Invoice the customer for only the excess amount 
- Defer the reconciliation of the revenue to the next invoicing period and do one final bill at the end of the project for any remaining unreconciled revenue

The main difference between a retainer-based contracting model and a fixed price contract model in Project Operations is that in the fixed price contract model, the invoice amount isn't linked or tied to costs incurred. Invoicing follows a milestone-based approach that is aligned to the costs incurred for that period. In a retainer-based contract, record revenue that you can invoice based on the billing method on the contract line. When the billing method is time and material, the invoiceable revenue is tied to costs incurred in any given period and can vary from period to period. However, the customer is only invoiced for the amount on the periodic retainer. The system uses another invoice at the end of the period to reconcile the invoiceable revenue recorded during the period against the amount that the customer was invoiced for at the start of the period.

The advantage of this method is that the customer's costs become predictable in the retainer schedule unlike in a typical time and material model. The organization delivering the project also has some room to cover the risk of recovering the costs incurred due to any increases in scope that a fixed price model wouldn't have allowed them.

In addition to a periodic retainer-based schedule, Project Operations can record a one-time advance from a customer and reconcile that against the different project cost components.

The retainer in Project Operations isn't available for use until you invoice it to the customer. This condition is indicated by the following fields on the subgrid for advances and retainers.

| Field | Description | Downstream impact |
| --- | --- | --- |
| Available Amount | The amount that is available to be used on the retainer or advance record. | Until you invoice the advance or retainer, it isn't available to be used which means the available amount is zero. |
| Used Amount | The amount that is already used on the retainer or advance. | An advance or retainer can be partially reconciled on an invoice with actual costs. Mark some part as already used or consumed. The rest of the advance or retainer amount is available to reconcile on a future invoice with actual costs. |


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
