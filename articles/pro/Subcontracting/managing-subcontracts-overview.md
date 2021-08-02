---
title: Managing subcontracts in Project Operations
description: This topic provides overview about end-to-end management of Subcontracts in Project Operations.
author: rumant
ms.date: 08/02/2021
ms.topic: article
ms.reviewer: kfend 
ms.author: rumant
---

# Managing subcontracts in Project Operations

_**Applies To:** Lite deployment - deal to proforma invoicing_

Subcontracting in in Dynamics 365 Project Operations supports the following business process flow.

> ![Subcontracting Process Flow](../media/SubcontractingProcessFlow.png)
  
The following is a step-by-step description of the subcontracting process in Project Operations.

1. The Project Manager creates a subcontract with a vendor. Price lists on the subcontract default from the price lists attached to the vendor record. The vendor account includes a relationship type of **Vendor** or **Supplier**.
2. The Project Manager can itemize all of the purchases as line items on the subcontract. Subcontract lines can be for **Time**, **Expense**, or **Products**, which is determined by the transaction class selected on the subcontract line.
3. The Vendor Account Manager and the Project Manager can iterate over the subcontract. Pricing can be adjusted in the purchase price lists that are attached to the subcontract. 
4. At this stage, or later in the process, if the subcontract line is for time, the Vendor Account Manager associates contacts to each subcontract line. This association provides information to the Project Manager working on the subcontract. When a contact is associated with the subcontract line, the system automatically create a bookable resource from a contact if it doesn't already exist. 
5. The billing method on the subcontract line can be Fixed Price or Time and Material. For Fixed Price subcontract lines, you can set up a milestone-based invoice schedule. 



[!INCLUDE[footer-include](../../includes/footer-banner.md)]

