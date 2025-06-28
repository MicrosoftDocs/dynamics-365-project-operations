---
title: Confirm a project contract
description: This article provides information how to confirm a contract in Project Operations.
author: poojafandan
ms.author: poojafandan
ms.date: 06/10/2024
ms.topic: how-to
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak

---

# Confirm a project contract

[!INCLUDE[banner](../../includes/banner.md)]

_**Applies To:** Project Operations Integrated with ERP, Core deployment - deal to proforma invoicing_

A project contract in Dynamics 365 Project Operations can be active with a reason of **Confirmed**, or closed with a reason of **Lost**. When you confirm a project contract, the status updates from **Draft** to **Active** and the status reason is **Confirmed**. An active or closed contract can't be edited or reopened. 

### Financial impact of confirming a project contract

After a project contract is confirmed, the application recalculates the costs by reversing the older cost actuals and creating new cost actuals. The new cost actuals are then processed based on the billing method of the associated project contract line. If the cost actuals reference a Time and Material contract line, the application automatically re-creates corresponding unbilled sales actuals. If the cost actuals reference a Fixed Price contract line, the application stops reprocessing the cost actuals.

Not-to-exceed limits, chargeability setup, and pricing and costing on the actuals is evaluated and then updated as part of the confirmations process.

## Close a project contract as lost

When you close a project contract as lost, the contract status is updated to **Closed** and the status reason is **Lost**. The project contract becomes read-only. A confirmation dialog is provided before the changes are complete because you can't reopen a closed project contract.

If the project contract that is closed as lost references a project on its lines, that project is also marked as closed. Any resource bookings from that day forward are canceled. Any unbilled sales actuals on the project contract that aren't already on an invoice, will be reversed.

> [!NOTE]
> In Dynamics 365 Project Operations, closing a project contract as lost will not impact that status of the associated opportunity. The opportunity will remain open and must be manually closed.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
