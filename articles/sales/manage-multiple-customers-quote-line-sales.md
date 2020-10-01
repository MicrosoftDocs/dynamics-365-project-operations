---
title: Managing multiple customers on project-based quote lines
description: This topic describes how to manage multiple customers on project-based quote lines.
author: rumant
manager: Annbe
ms.date: 10/01/2020
ms.topic: article
ms.service: dynamics-365-customerservice
ms.reviewer: kfend 
ms.author: rumant
---

# Managing multiple customers on project-based quote lines

Project-based quote lines support scenarios where each quote line has a list of customers that are paying for it. This list of customers on the project-based quote line can be same as the list of customers on the quote. You can also change the list of customers to be different. When a project quote is won to create the eventual project contract, the customer list on project-based quote line is copied to the corresponding project–based contract line. Customers on the project-based quote are copied to the project contract.

When invoicing the eventual project contract, the customer list on the project-based contract line takes priority over the one on the project contract. The customer list on the project contract is only used for defaulting on new project contract lines.

All quote customers on the **Customers** tab of the project quote default as quote line customers on any new project-based quote lines created for the project quote. Any existing project-based quote lines don't inherit new quote customer records created after them.

## Create, update, or delete a quote line customer record

You can create, update, or delete a quote line customer on the **Quote line customers** tab on the **Project-based quote line** page. When you add a new customer on the project-based quote line, the customer is also added to the overall quote as a quote customer, with a default billing split percentage on the overall quote of 0%. The billing split percentage on the overall quote is copied to new quote lines and to the eventual project contract. However, when invoicing from the contract, the billing split percentage at the quote line level is used, not the billing split percentage at the overall contract level. 

The following table shows the fields on the quote line customer record of a project-based quote line.

| Field | Location | Description and guidance | Downstream impact |
| --- | --- | --- | --- |
| Field | Location | Description and guidance | Downstream impact |
| --- | --- | --- | --- |
| **Account** | Editable grid on the **Quote line customers** tab and the main and quick create forms for a quote line customer | Lists all active accounts. This field is locked after the record is created. If you need to update it, delete the record, and then re-create it. If you recorded any actuals, then you can't delete the record. | When you pick an account from the master list of accounts to add, the Quote line customer is also added as a Quote customer when you save it. Quote line customers are copied over to the project contract line customers when a quote is won. |
| **Billing split percent** | Editable grid on the **Quote line customers** tab and the main and quick create forms for a quote line customer | Represents the percentage of each unbilled sales transaction that will be attributed to this quote line customer. | Copied over to project contract line customers. |
| **Not-to-exceed limit** | Editable grid on the **Quote line customers** tab and the main and quick create forms for a quote line customer | Indicates whether there is a negotiated limit or cap to the overall amount that will be invoiced to this customer for this quoted line. | Copied over to project contract line customers when a quote is won. |
| **Is rounding** | Editable grid on the **Quote line customers** tab and the main and quick create forms for a quote line customer | Indicates whether this customer is a default rounding customer for this project-based quote line. | Copied over to project contract customers when a quote is won. |

## Editing billing split percentages

You can edit billing split percentages in the in-line grid. When the billing split percentages don't total 100%, an error displays. After editing the billing split percentages, you must refresh the quote line page to make the error disappear.

You can also use the evenly distribute action on the quote line customers subgrid. This action can allocate billing splits to all quote line customers. If there's a rounding factor, that will be added to the rounding customer. One of the quote line customers is always tagged as the rounding customer, which means that quote line customer record has the rounding flag set to **Yes**. 