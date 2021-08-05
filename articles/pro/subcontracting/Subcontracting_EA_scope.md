---
title: Subcontracting - October 2021 Release Early Access Scope
description: This topic provides an overview of the October 2021 Release Early Access Scope for Sucbontracting capabilities in Project Operations.
author: rumant
ms.date: 08/02/2021
ms.topic: article
ms.reviewer: kfend 
ms.author: rumant
---

# Subcontracting - October 2021 Release Early Access Scope

[!include [banner](../../includes/dataverse-preview.md)]

_**Applies To:** Lite deployment - deal to proforma invoicing_


The October 2021 early access release is lighting up portions of the subcontracting capabilities for Project Operations customers. However, this feature set is not ready for Production or live usage. Subcontracting feature set will remain in Preview mode until the full capability set is released. It is strongly advised to not use the Subcontracts capability set for live production scenarios until the Preview banner is removed. 

Below is the outlined scope for October 2021 Early Access:

1. The project manager creates a subcontract with a vendor. By default, the price lists that are attached to the vendor record are used for the subcontract. The vendor account has a relationship type of **Vendor** or **Supplier**.

2. The project manager can itemize all the purchases as line items on the subcontract. Subcontract lines can be for time, expenses, or products. The transaction class of the subcontract line determines what the line is for.

3. The vendor account manager and the project manager can iterate over the subcontract. Pricing can be adjusted in the purchase price lists that are attached to the subcontract.

4. At this point or later in the process, if the subcontract line is for time, the vendor account manager associates vendor contacts with each subcontract line. This association provides information to the project manager who is working on the subcontract. When a vendor contact is associated with a subcontract line, the system automatically creates a bookable resource from the contact, if a bookable resource doesn't already exist.

5. The billing method on each subcontract line can be **Fixed Price** or **Time and Material**. For fixed-price subcontract lines, a milestone-based invoice schedule is setup.

The rest of the steps in business process flow for Subcontracting is currently not available in the scope of October 2021 Early access. As new functionality is added, this page will be updated. 

The figure below represents the October 2021 Early Access scope figuratively as contrasted with the end-to-end business process outline in the Overview topic:

![Subcontracting process flow](../media/SubcontractingEAFlow.png)  


## Scope of Quantity-based and Work-based Subcontract lines for October 2021 Early Access
In the Early access scope of October 2021, only quantity-based subcontract lines are supported. This means that a subcontract line can be used to purchase Time, Expenses or Materials from a vendor but not a whole body of work. It also means that the quantity being purchased (units of time, expenses, or quantity of materials) on a subcontract line can be used on any project in the system. 


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
