---
title: Manage multiple customers on project contract lines
description:  This article provides information about managing multiple customers on project-based contract lines.
author: poojafandan
ms.author: poojafandan
ms.date: 02/26/2026
ms.topic: concept-article
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak

---

# Manage multiple customers on project contract lines

[!INCLUDE[banner](../../includes/banner.md)]

_**Applies To:** Project Operations Core_

Project-based contract lines can include a list of customers that are responsible for payment. This list of customers on the project-based contract line can be the same as the list of customers on the contract but isn't required. When you win a project quote and create a project contract, you copy the customer list on the quote line to the corresponding contract line. You copy customers on the quote to the contract.

When you invoice the project contract, the customer list on project-based contract line takes priority over the customer list on the contract. The customer list on the project contract is only used to default new contract lines.

All contract customers on the **Customers** tab of the project contract default as contract line customers on any new contract lines created for the project contract. Any existing contract lines don't inherit the new contract customer records.

## Create, update, or delete a contract line customer record

You can create, update, or delete a contract line customer from the Contract Line Customers tab on the Project-based Contract Line page. When you add a new customer on the project-based contract line, you also add them on the overall contract as a contract customer with a default billing split percentage of zero percent. You copy the billing split percentage on the overall contract to new contract lines and to the eventual project contract. However, when invoicing from the contract, use the billing split percentage at the contract line level and not the billing split percentage at the overall contract level.

Keep the following fields in mind as you work with the **Contract** line customer record of a project-based contract line:

| Field | Location | Description | Downstream impact |
| --- | --- | --- | --- |
| **Account** | Editable grid on the **Contract Customers** tab and the **Main** and **Quick Create** forms for a contract customer. | All active accounts. This field is locked after the record is created. To update the field, delete the record, and create a new record. If you record any actuals, you can't delete the record. However, you can mark the billing split percentage as zero for that account. When you mark the record as zero, any future cost and revenue actuals that you attribute or split to this customer are impacted. | When you pick an account from the master list of accounts to add and save them, you also add the contract line customer as a contract customer. Use contract line customers when generating invoices. |
| **Billing Split Percent** | Editable grid on the **Contract Customers** tab and the **Main** and **Quick Create** forms for a contract customer. | This field represents the percentage of each unbilled sales transaction that you attribute to this contract line customer. | Use contract line customers and billing split percentages when you create actuals after approval and when you generate the invoice. |
| **Not-to-Exceed Limit** | Editable grid on the **Contract Customers** tab and the **Main** and **Quick Create** forms for a contract customer. | Indicates if there's a negotiated limit or cap to the overall amount that you invoice to this customer for the contract line. | Use the not-to-exceed limit for the contract line customer when you create actuals and generate the invoices. |
| **Is Rounding** | Editable grid on **Contract Customers** tab and **Main** and **Quick Create** forms for a contract line customer. | This field indicates if this customer is a default rounding customer for this project-based contract line. | When you generate an actual according to the billing split percentage, there might be some rounding differences. Attribute these rounding differences to this customer. |

## Edit billing split percentages

Edit billing split percentages in the grid. If the billing split percentages don't total 100 percent, an error occurs. After you edit the billing split percentages, refresh the page to remove the error.

Select **Evenly Distribute** on the contract line customer subgrid to evenly allocate billing splits to all contract line customers. If there's any rounding factor, the process adds it to the rounding customer. One contract line customer is always tagged as the **Rounding** customer with the **Rounding** flag set to **Yes**.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
