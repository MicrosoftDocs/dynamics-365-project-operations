---
title: Manage multiple customers on project Contracts
description: This topic provides information about how to manage mulitple customers on a project contract.
author: rumant
manager: Annbe
ms.date: 11/15/2020
ms.topic: article
ms.service: project-operations
ms.reviewer: kfend 
ms.author: rumant
---

# Manage multiple customers on project contracts

You can use a project contract when a contractual agreement when multiple customers are involved in funding the deal. The **Summary** tab of the **Project Contract** page includes information about the primary customer of the deal. Other customers participating in the deal can be added to the **Customers** tab.

All contract customers on the **Customers** tab of the project contract default as contract line customers on any **new** project-based contract lines created for the project contract. Any existing project-based contract lines don't inherit new contract customers records created at a later time.

You can add, update, or delete contract and contract line customers any time before the contract is won. A customer on the project contract must be set up as a customer in the owning company or legal entity on the **Customers** page. Legal entities are set up in the **Project management and accounting** module of Dynamics 365 Project Operations and are available as companies in the **Project Sales** and **Delivery** modules of Project Operations.

## Primary customers

The potential customer on the **Summary** tab of the project contract is the primary customer of the contract. When you try to delete the primary customer from customers list on contract, an error will occur that says a primary customer record on a contract can't be deleted.

Don't update the primary customer from the contract customers list. Instead, change the customer in the **Potential Customer** field on the **Summary** tab of the project contract. When you update this field, the newly selected customer is added as a new contract customer with the **Primary** flag set to **Yes**. The previous primary customer is still be a customer on the contract, however they are no longer the primary customer.

## Create, update, or delete a contract customer record

You can create, update, or delete a contract customer from the **Contract Customers** tab on the **Contract** page. The following fields are included on the contract customer record of a project contract.

| **Field** | **Location** | **Description** | 
| --- | --- | --- | 
| Account | Editable grid on the **Contract Customers** tab and the main and quick create pages for a contract customer. | Lists all the active accounts. This field is locked after the record is created. To update the record, you have to delete and then re-create it. If you have recorded any actuals, or if the contract customer record is a primary customer, you can't delete the record. When a contract line is created, contract customers are copied as contract line customers. |
| Billing Split Percent | Editable grid on the **Contract Customers** tab and the main and quick create pages for a contract customer. | Represents the percentage of each unbilled sales transaction attributed to this contract customer. When new project contract lines are created, the billing split percent is copied to new any ontract lines created and to project contract line customers. |
| Bill to Contact Name | Editable grid on the **Contract Customers** tab and the main and quick create pages for a contract customer. | This text field should be used to identify the invoice contact person for this customer which defaults from the related account record. The contact name is copied to the **Bill to Contract Name** field on the invoice generated for this customer. |
| Bill To Name | Editable grid on the **Contract Customers** tab and the main and quick create pages for a contract customer. | Use this field to identify the invoice contact person for this customer which defaults from the related account record. The name is copied to the **Bill to Contract Name** field on the invoice generated for this customer |
| Payment Terms | Editable grid on the **Contract Customers** tab and main and quick create pages for a contract customer. | The values in this field default from the related account record. The terms are copied over to the **Bill to Contract Name** field on the invoice generated for this customer. |
| Owning Company | Editable grid on the **Project Contract Customers** tab and the main and quick create pages for a project contract customer. | The legal entity in which this customer is set up in the **Project management and accounting** module. This field is read-only and set to the owning company of the project contract.</br>The list of customers to add in the **Account** field is already filtered to the list from this owning company in the **Project management and accounting** module of Project Operations. The owning company is equal to the legal entity in the **Project management and accounting** module of Project Operations. All costs and revenue accruing from this project is accounted for in the general ledger of the owning company. |
| Is Rounding | Editable grid on the **Contract Customers** tab and the main and quick create pages for a contract customer. | Indicates if the customer is a default rounding customer for this deal. There can only be one rounding customer on a project contract. When cost and unbilled sales split on quantity and lead to a rounding difference, that difference is applied to the actual that maps to this customer. |
| Not-to-exceed Limit | Editable grid on the **Contract Customers** tab and the main and quick create pages for a contract customer. | Indicates if there is a negotiated limit or cap to the overall amount that will be invoiced to this customer for this engagement. The not-to-exceed limit set up at the contract customer level is evaluated on unbilled sales actuals that reference this contract customer. |

## Edit billing split percentages

You can edit billing split percentages by editing in the grid. When billing split percentages don't total 100 percent, an error occurs. After you edit the billing split percentages, refresh the **Project Contract** page to remove the error.

You can also select **Evenly Distribute** on the project contract customers sub-grid. Billing splits are evenly allocated to all of the customers on the project contract. If there is any rounding factor, the factor will be added to the rounding customer. One of the contract customers always has the **Rounding** flag set to **Yes** and that customer is the rounding customer. Typically, this is the primary customer of the contract, but that isn't required.
