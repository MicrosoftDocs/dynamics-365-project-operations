---
title: Copy project contracts
description: This article provides information about copying project contracts in Project Operations.
author: poojafandan
ms.date: 06/07/2024
ms.topic: how-to
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak
ms.author: poojafandan
---

# Copy project contracts

[!INCLUDE[banner](../../includes/banner.md)]

_**Applies To:** Core deployment - deal to proforma invoicing_

You can easily create new project contracts by making copies of existing contracts in one of two ways: 

  - On the **Project Contracts** list page, select a project contract and then select **Copy**.
  - On the **Project Contract** details page, select **Copy**.

A dialog page will open where you can select the parameters of the copied contract. The following fields are included on the dialog. Depending on the values you select in this dialog, the copy process may change.

| **Field** | **Description** | **Downstream impact** |
| --- | --- | --- |
| Topic | Enter the topic of the target contract. When the dialog page opens, the system will set this field to the name of the source contract with **copy** appended to it. | There's no downstream impact for this field. |
| Customer | Reference to the customer's company or account record. When the dialog opens, the system will set this field to the account on the source contract. | This field is the primary customer on the contract. |
| Contracting Unit | The Organization unit that is responsible for the delivery of the project(s) associated with this deal. When the dialog page opens, the system will set it to the contracting unit of the source contract. | The contracting unit is the division of the company that will be executing the projects after the deal is closed. Every contracting unit has a currency. This currency is used to report estimated and actual costs incurred during the project. |
| Currency | The currency that the deal is transacted in. When the dialog page opens, the system will set the field to the currency of the source contract. The currency can be changed. If it is, the **Copy Pricing** field is always set to **No** because the price lists on source contract are no longer relevant. | Currency is used for default price lists, for building financial estimates on the contract, and for invoicing the customer when the deal is won. |
| Requested Delivery Date | The delivery date requested by the customer. | This date is used as the end date when you create invoicing dates along a specific frequency. |
| Copy pricing | Indicates whether the pricing on the contract should be copied from the source contract. | If the field is set to **Yes**, project and product price list references are copied from the source to the target contract. If **No** is selected, price lists default based on the latest price lists on the account or project parameters. |

When you select **OK** on the dialog page, the system creates a copy of the contract based on the parameters selected. The new contract will open.

The following information isn't copied from the **Source** to the **Target Contract**:

  - Invoice schedules
  - Contract and contract line customers
  - Project reference on the project-based contract lines
  - Customer budget information

Because this information is specific to each contract, these fields and records aren't copied. Contract lines for projects and products, estimations on contract line details, and not-to-exceed values at the contract level are copied. Price and cost rate defaulting depend on the selection in the **Copy pricing** field on the **Copy Parameters** dialog page.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
