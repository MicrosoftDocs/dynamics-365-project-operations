---
title: Manage multiple customers on project contracts
description:  This article provides information about managing multiple customers on project contracts.
author: poojafandan
ms.author: poojafandan
ms.date: 02/26/2026
ms.topic: concept-article
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak

---

# Manage multiple customers on project contracts

[!INCLUDE[banner](../../includes/banner.md)]

_**Applies To:** Project Operations Core_

Project contracts in Dynamics 365 Project Operations support the scenario where a contractual agreement involves multiple customers who fund a deal. The **Summary** tab on the **Project Contract** page includes the **Customer** field. This field identifies the primary customer of the deal. Set up other customers for the deal on the **Customers** tab of the **Project Contract** page.

All contract customers listed on the project contract default as contract line customers on any new project-based contract lines that you create for the project contract. Existing project-based contract lines don't inherit new contract customers.

You automatically associate product-based contract lines to the primary customer.

Add, update, or delete contract customers and contract line customers at any time before you win the contract.

## Primary customer

The customer that you list on the **Summary** tab of the project contract as the potential customer is the primary customer of the contract. If you try to delete the primary customer from the customer list on the contract, you receive an error message that you can't delete a primary customer record on a contract.

You can't update the primary customer from the contract customers list. Instead, change the potential customer on the **Summary** tab of the contract. When you update this field on the **Contract Summary** page, you add the new customer as a new contract customer with the **Primary** flag set. The previous primary customer remains a customer on the contract.

## Create, update, or delete a contract customer record

You can create, update, or delete a contract customer from the **Customers** tab on the **Project Contract** page. The fields in the following table are on the contract customer record of a project contract. Keep these fields in mind as you work with the contract.

| Field | Location | Description | Downstream impact |
| --- | --- | --- | --- |
| **Account** | Edit the grid on the **Contract Customers** tab. Edit the **Main** and **Quick Create** forms for a contract customer. | Lists all the active accounts. This field is locked after you create the record. To update the account, delete the record and re-create it. If you recorded any actuals, or if the contract customer record is a primary customer, you can't delete the record. | Contract customers are copied over as contract line customers when you create a contract line. |
| **Billing Split Percent** | Edit the grid on the **Contract Customers** tab. Edit the **Main** and **Quick Create** forms for a contract customer. | Represents the percentage of each unbilled sales transaction that you attribute to this contract customer. | Copied over to new contract lines and to project contract line customers on new project contract lines. |
| **Bill to Contact Name** | Edit the grid on the **Contract Customers** tab. Edit the **Main** and **Quick Create** forms for a contract customer. | Use this text field to identify the invoice contact person for this customer. This field defaults from the related account record. | Copied over to the **Bill to Contract Name** field on the invoice that is generated for this customer. |
| **Bill To Name** | Edit the grid on the **Contract Customers** tab. Edit the **Main** and **Quick Create** forms for a contract customer. | Use this text field to identify the invoice contact person for this customer. This field defaults from the related account record. | Copied over to the **Bill to Contract Name** field on the invoice that is generated for this customer. |
| **Payment Terms** | Edit the grid on the **Contract Customers** tab. Edit the **Main** and **Quick Create** forms for a contract customer. | The values default from the related account record. | Copied over to the **Bill to Contract Name** field on the invoice that is generated for this customer. |
| **Is Rounding** | Edit the grid on the **Contract Customers** tab. Edit the **Main** and **Quick Create** forms for a contract customer. | Indicates if this customer is a default rounding customer for this deal. There can only be one rounding customer on a project contract. | When cost and unbilled sales splits on quantity lead to a rounding difference, that difference is applied to the actual that maps to this customer. |
| **Not-to-Exceed Limit** | Edit the grid on the **Contract Customers** tab. Edit the **Main** and **Quick Create** forms for a contract customer. | Indicates if there's a negotiated limit or cap to the overall amount that you invoice to the customer for this engagement. | The **Not-to-Exceed Limit** set up at the contract customer level is evaluated on **Unbilled Sales Actuals** that reference this contract customer. |

## Edit billing split percentages

Edit billing split percentages by using the in-line grid edit experience. If the billing split percentages don't total 100 percent, you receive an error. After you edit the billing split percentages, refresh the page to dismiss the error.

You can also select **Evenly Distribute** on the **Contract Customers** subgrid to allocate billing splits evenly to all contract customers. If there's a rounding factor, the system adds it to the rounding customer. One of the contract customers is always tagged as the **rounding** customer, which means that the contract customer record has the rounding flag set to **Yes**. Typically, this customer is the primary customer of the contract, but you can change it.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
