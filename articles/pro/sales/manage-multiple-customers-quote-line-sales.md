---
title: Manage multiple customers on project quote lines
description: Learn how to manage multiple customers on project quote lines, including creating, updating, and deleting customer records, and editing billing splits.
author: poojafandan
ms.author: poojafandan
ms.date: 01/30/2026
ms.topic: concept-article
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak

---

# Manage multiple customers on project quote lines

[!INCLUDE[banner](../../includes/banner.md)]

_**Applies To:** Project Operations Core_

Project quote lines support scenarios where each quote line has a list of customers that pay for it. This list of customers on the project-based quote line can be the same as the list of customers on the quote. You can also change the list of customers to be different. When you win a project quote, the customer list on the project-based quote line is copied to the corresponding project–based contract line to create the eventual project contract. Customers on the project-based quote are copied to the project contract.

When you invoice the eventual project contract, the customer list on the project-based contract line takes priority over the list on the project contract. The customer list on the project contract is only used for defaults on new project contract lines.

All quote customers on the **Customers** tab of the project quote default as quote line customers on any new project-based quote lines created for the project quote. Any existing project-based quote lines don't inherit new quote customer records created after them.

## Create, update, or delete a quote line customer record

You can create, update, or delete a quote line customer on the **Quote line customers** tab on the **Project-based quote line** page. When you add a new customer on the project-based quote line, you also add the customer to the overall quote as a quote customer, with a default billing split percentage on the overall quote of 0%. You copy the billing split percentage on the overall quote to new quote lines and to the eventual project contract. However, when invoicing from the contract, use the billing split percentage at the quote line level, not the billing split percentage at the overall contract level.

The following table shows the fields on the quote line customer record of a project-based quote line.

| Field | Location | Description and guidance | Downstream impact |
| --- | --- | --- | --- |
| **Account** | An editable grid on the **Quote line customers** tab, the main form, and the quick create forms for a quote line customer. | Lists all active accounts. This field is locked after the record is created. To update the field, delete and recreate the record. If you recorded any actuals, you can't delete the record. | When you pick an account from the master list of accounts to add, you also add the quote line customer as a quote customer when you save it. When you win a quote, the system copies quote line customers to the project contract line customers. |
| **Billing split percent** | An editable grid on the **Quote line customers** tab, the main form, and the quick create forms for a quote line customer. | Represents the percentage of each unbilled sales transaction that you attribute to this quote line customer. | You copy this value over to project contract line customers. |
| **Not-to-exceed limit** | An editable grid on the **Quote line customers** tab, the main form, and the quick create forms for a quote line customer. | Indicates whether there's a negotiated limit or cap to the overall amount that you invoice to this customer for this quoted line. | You copy this value over to project contract line customers when a quote is won. |
| **Is rounding** | An editable grid on the **Quote line customers** tab, the main form, and the quick create forms for a quote line customer. | Indicates whether this customer is a default rounding customer for this project-based quote line. | You copy this value over to project contract customers when a quote is won. |

## Edit billing split percentages

You can edit billing split percentages inline. When the billing split percentages don't total 100%, an error occurs. After you edit the billing split percentages, refresh the quote line page to remove the error.

Use the **evenly distribute** action on the **quote line customers** subgrid to allocate billing splits to all quote line customers. If there's a rounding factor, the action adds that factor to the rounding customer. One of the quote line customers is always tagged as the rounding customer, which means that quote line customer record has the rounding flag set to **Yes**.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
