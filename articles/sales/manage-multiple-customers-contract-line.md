---
title: Manage multiple customers on project-based contract lines
description: This article provides information about working with contract lines and contracts that contain multiple customers.
author: poojafandan
ms.date: 06/07/2024
ms.topic: article
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak
ms.author: poojafandan
---

# Manage multiple customers on project-based contract lines

_**Applies To:** Project Operations Integrated with ERP, Core deployment - deal to proforma invoicing_

Project-based contract lines can include a list of customers that are responsible for payment. This list of customers on the project-based contract line can be same as the list of customers on the contract but that isn't required. When a project quote is won, and a project contract is created, the customer list on the quote line is copied to the corresponding contract line. Customers on the quote are copied to the contract.

When the project contract is invoiced, the customer list on project-based contract line takes priority over the customer list on the contract. The customer list on the project contract is only used to default new contract lines.

All contract customers on the **Customers** tab of the project contract default as contract line customers on any new contract lines created for the project contract. Any existing contract lines will not inherit the new contract customer records created after them.

## Create, update, or delete a contract line customer record

You can create, update, or delete a contract line customer from the **Contract Line Customers** tab on the **Project-based Contract Line** page. When a new customer is added on the project-based contract line, they are also added on the overall contract as a contract customer with a default billing split percentage of zero percent. The billing split percentage on the overall contract is copied to new contract lines and to the eventual project contract. However, when invoicing from the contract, it's the billing split percentage at the contract line level that is used and not the billing split percentage at the overall contract level. 

Below are the fields on the Contract line customer record of a project-based Contract line to keep in mind as you are working with it:

| Field | Location | Description | Downstream impact |
| --- | --- | --- | --- |
| Account | Editable grid on **Contract Line Customers** tab and Main and Quick Create forms for a contract line customer | All active accounts. This field is locked after the record is created. To update the field, delete the record, and create a new record. If you have recorded any actuals, you can't delete the record. However, you can mark the billing split percentage as zero for that account. When the record is marked as zero, any future cost and revenue actuals that are attributed or split to this customer are impacted. | When you pick an account from the master list of accounts to add and save them, the contract line customer is also added as a contract customer. Contract line customers are used when invoices are generated. |
| Billing split percent | Editable grid on **Contract Line Customers** tab and the Main and Quick Create forms for a contract line customer | This field represents the percentage of each unbilled sales transaction that will be attributed to this contract line customer. | Contract line customers and billing split percentages are used when actuals are created after approval and when the invoice is generated. |
| Not-to-exceed limit | Editable grid on **Contract Line Customers** tab and Main and Quick Create forms for a contract line customer | Indicates if there is a negotiated limit or cap to the overall amount that will be invoiced to this customer for the contract line. | The not-to-exceed limit for the contract line customer is used when actuals are created and the invoices are generated. |
| Owning Company | Editable grid on the **Quote Line Customers** tab and the Main and Quick Create forms for a quote line customer | The legal entity that this customer is set up in. This field is read-only and is set to the owning company of the quote. The list of customers to add in the **Account** field is already filtered to the list from this owning company. | The concept of an owning company equates to the concept of a legal entity. All costs and revenue accruing from this project are accounted for in the General ledger of the owning company. |
| Is Rounding | Editable grid on **Contract Line Customers** tab and Main and Quick Create forms for a contract line customer | This field indicates if this customer is a default rounding customer for this project-based contract line. | When you generate an actual according to the billing split percentage, there may be some rounding differences. This customer is attributed the rounding differences in this case. |

## Edit billing split percentages

Billing split percentages can be edited in the grid. When the billing split percentages don't total 100 percent, an error will occur. After you edit the billing split percentages, refresh the page to remove the error.

You can also try selecting **Evenly Distribute** on the contract line customer subgrid. This action evenly allocates billing splits to all contract line customers. If there is any rounding factor, it will be added to the rounding customer. One contract line customer is always tagged as the **Rounding** customer with the **Rounding** flag set to **Yes**.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
