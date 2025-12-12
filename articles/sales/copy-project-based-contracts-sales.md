---
title: Copy project-based contracts
description: This article provides information about copying project contracts in Microsoft Dynamics 365 Project Operations.
author: poojafandan
ms.date: 03/01/2024
ms.topic: article
ms.reviewer: johnmichalak
ms.author: poojafandan
---

# Copy project-based contracts

_**Applies To:** Project Operations Integrated with ERP_

You can easily create new project contracts by copying existing contracts in one of two ways:

- On the **Project Contracts** list page, select a project contract, and then select **Copy**.
- On the **Project Contract** details page, select **Copy**.

In both cases, a dialog box appears, where you can set the parameters of the copied contract. The dialog box includes the following fields. Depending on the values that you select, the copy process might change.

| Field | Description | Downstream impact |
| --- | --- | --- |
| Topic | Enter the topic of the target contract. When the dialog box is opened, the system sets the field to the name of the source contract, but the word "copy" is appended to it. | There is no downstream impact for this field. |
| Owning Company | The company that is responsible for delivery of the projects that are associated with this deal. When the dialog box is opened, the system sets the field to the owning company of the source contract. You can change the owning company to an alternate company. | The owning company is the legal entity that will be executing the project after the deal is closed. The currency of the owning company must match the currency of the contracting unit. |
| Customer | Reference to the customer's company or account record. A valid customer to reference on the project contract must be set up as a customer in the owning company. | Customer that are set up in the owning company can be selected from the dropdown menu. |
| Contracting Unit | The organization unit that is responsible for delivery of the projects that are associated with this deal. When the dialog box is opened, the system sets the field to the contracting unit of the source contract. | The contracting unit is the division of the company that will be executing the projects after the deal is closed. Every contracting unit has a currency. This currency is used to report estimated and actual costs that are incurred during the project. |
| Currency | The currency that the deal is transacted in. When the dialog box is opened, the system sets the field to the currency of the source contract. The currency can be changed. If it is, the **Copy Pricing** field is always set to **No**, because the price lists on the source contract are no longer relevant. | This currency is used for default price lists, to generate financial estimates on the contract, and to invoice the customer when the deal is won. |
| Requested Delivery Date | The delivery date that is requested by the customer. | This date is used as the end date when you create invoicing dates at a specific frequency. |
| Copy pricing | A value that indicates whether the pricing on the contract should be copied from the source contract. | If the field is set to **Yes**, project and product price list references are copied from the source contract to the target contract. If it's set to **No**, default price lists are used, based on the latest price lists in the account or project parameters. If the target Owning company is different Owning company, the Copy pricing will be defaulted to **No**. |

When you select **OK** in the dialog box, the system creates a copy of the contract, based on the parameter values that you set. Then the new contract is opened.

The following information is **not** copied from the source contract to the target contract, because it's specific to each contract:

- Invoice schedules
- Contract and contract line customers
- Project reference on the project-based contract lines
- Customer budget information

Contract lines for projects and products, estimates in contract line details, and not-to-exceed values at the contract level are copied. Entry of default prices and cost rates depends on the selection in the **Copy pricing** field in the **Copy Parameters** dialog box.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
