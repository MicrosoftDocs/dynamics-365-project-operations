---
title: Manage multiple customers on project contracts
description:  This article provides information about managing multiple customers on project contracts.
author: poojafandan
ms.author: poojafandan
ms.date: 06/07/2024
ms.topic: concept-article
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak

---

# Manage multiple customers on project contracts

[!INCLUDE[banner](../../includes/banner.md)]

_**Applies To:** Project Operations Core_

Project contracts in Dynamics 365 Project Operations support the scenario where a contractual agreement involves multiple customers who are funding a deal. The **Summary** tab on the **Project Contract** page includes the **Customer** field. This field identifies the primary customer of the deal. Other customers for the deal can be set up on the **Customers** tab of the **Project Contract** page.

All contract customers listed on the project contract default as contract line customers on any new project-based contract lines that are created for the project contract. Existing project-based contract lines don't inherit new contract customers as new records are created.

Product-based contract lines are automatically associated to the primary customer.

Contract customers and contract line customers can be added, updated, or deleted at any time before the contract is won.

## Primary customer

The customer listed on the **Summary** tab of the project contract as the potential customer is the primary customer of the contract. When you try to delete the primary customer from the customer list on the contract, you will receive an error message that a primary customer record on a contract can't be deleted.

The primary customer can't be updated from the contract customers list. Instead, change the potential customer on the **Summary** tab of the contract. When this field is updated on the **Contract Summary** page, the new customer is added as a new contract customer with the **Primary** flag set. The previous primary customer will still be a customer on the contract.

## Create, update, or delete a contract customer record

A contract customer can be created, updated, or deleted from the **Customers** tab on the **Project Contract** page. The fields in the following table are on the contract customer record of a project contract and should be kept in mind as you are working with the contract.

| Field | Location | Description | Downstream impact |
| --- | --- | --- | --- |
| **Account** | The grid can be edited on the **Contract Customers** tab and the **Main** and **Quick Create** forms for a contract customer. | Lists all the active accounts. This field is locked after the record is created. To update the account, delete the record and re-create it. If you have recorded any actuals, or if the contract customer record is a primary customer, you can't delete the record. | Contract customers are copied over as contract line customers when a contract line is created. |
| **Billing Split Percent** | The grid can be edited on the **Contract Customers** tab and the **Main** and **Quick Create** forms for a contract customer. | Represents the percentage of each unbilled sales transaction that is attributed to this contract customer. | Copied over to new contract lines and to project contract line customers on new project contract lines. |
| **Bill to Contact Name** | The grid can be edited on the **Contract Customers** tab and the **Main** and **Quick Create** forms for a contract customer. | This text field should be used to identify the invoice contact person for this customer. This field defaults from the related account record. | Copied over to the **Bill to Contract Name** field on the invoice that is generated for this customer. |
| **Bill To Name** | The grid can be edited on the **Contract Customers** tab and the **Main** and **Quick Create** forms for a contract customer | This text field should be used to identify the invoice contact person for this customer. This field defaults from the related account record. | Copied over to the **Bill to Contract Name** field on the invoice that is generated for this customer. |
| **Payment Terms** | The grid can be edited on the **Contract Customers** tab and the **Main** and **Quick Create** forms for a contract customer. | The values default from the related account record. | Copied over to the **Bill to Contract Name** field on the invoice that is generated for this customer. |
| **Is Rounding** | The grid can be edited on the **Contract Customers** tab and the **Main** and **Quick Create** forms for a contract customer. | Indicates if this customer is a default rounding customer for this deal. There can only be one rounding customer on a project contract. | When cost and unbilled sales splits on quantity lead to a rounding difference, that difference is applied to the actual that maps to this customer. |
| **Not-to-Exceed Limit** | The grid can be edited on the **Contract Customers** tab and the **Main** and **Quick Create** forms for a contract customer | Indicates if there is a negotiated limit or cap to the overall amount that will be invoiced to the customer for this engagement. | The **Not-to-Exceed Limit** set up at the contract customer level will be evaluated on **Unbilled Sales Actuals** that reference this contract customer. |

## Edit billing split percentages

Billing split percentages can be edited using the in-line grid edit experience. When the billing split percentages do not total to 100 percent, you will receive an error. After you edit the billing split percentages, refresh the page to dismiss the error.

You can also select **Evenly Distribute** on the **Contract Customers** subgrid to allocate billing splits evenly to all contract customers. If there is a rounding factor, it will be added to the rounding customer. One of the contract customers is always tagged as the **rounding** customer, which means that the contract customer record has the rounding flag set to **Yes**. Typically, this is the primary customer of the contract, but it can be changed as well.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
