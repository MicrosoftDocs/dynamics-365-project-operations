---
title: Manage multiple customers on project-based contracts
description: This article provides information about how to manage multiple customers on a project-based contract.
author: rumant
ms.date: 11/18/2020
ms.topic: article
ms.reviewer: johnmichalak
ms.author: rumant
---

# Manage multiple customers on project-based contracts

This article provides information about how to manage multiple customers on a project contract. You can use a project contract when a contractual agreement for multiple customers is needed for funding a deal. On the **Project Contract** page, the **Summary** tab includes information about the primary customer for a deal. Other customers that participate in the deal can be added to the **Customers** tab.

All contract customers on the **Customers** tab of the project contract default as contract line customers on any new project-based contract lines created for the project contract. Any existing project-based contract lines don't inherit new contract customers records that are created at a later time.

You can add, update, or delete contract and contract line customers anytime before the contract is won. A customer on the project contract must be set up as a customer in the owning company or legal entity on the **Customers** page. Legal entities are set up in the **Project management and accounting** module of Dynamics 365 Project Operations and are available as companies in the **Project Sales** and **Delivery** modules of Project Operations.

## Primary customers

The potential customer on the **Summary** tab of the project contract is the primary customer of the contract. You cannot update the primary customer from the contract customer's list. If you try to delete the primary customer from a customer list on contract, an error will occur that says a primary customer record on a contract can't be deleted. Instead, change the customer in the **Potential Customer** field on the **Summary** tab of the project contract. When you update this field, the newly selected customer is added as a new contract customer with the **Primary** flag set to **Yes**. The previous primary customer is still a customer on the contract, however they are no longer the primary customer.

## Create, update, or delete a contract customer record

You can create, update, or delete a contract customer from the **Contract Customers** tab on the **Contract** page. The following fields are included on the contract customer record of a project contract.

| **Field** | **Location** | **Description** | 
| --- | --- | --- | 
| Account | Editable grid on the **Contract Customers** tab and the main and quick create pages for a contract customer. | Lists all the active accounts. This field is locked after the record is created. To update the record, you have to delete it and then re-create it. If you have recorded any actuals, or if the contract customer record is a primary customer, you can't delete the record. When a contract line is created, contract customers are copied as contract line customers. |
| Billing Split Percent | Editable grid on the **Contract Customers** tab and the main and quick create pages for a contract customer. | Represents the percentage of each unbilled sales transaction attributed to the contract customer. When new project contract lines are created, the billing split percent is copied to new any contract lines created and to project contract line customers. |
| Bill to Contact Name | Editable grid on the **Contract Customers** tab and the main and quick create pages for a contract customer. | This text field should be used to identify the invoice contact person for the customer. The default value comes from the related account record. The contact name is copied to **Bill to Contract Name** on the invoice generated for the customer. |
| Bill To Name | Editable grid on the **Contract Customers** tab and the main and quick create pages for a contract customer. | Use this field to identify the invoice contact person for the customer. The default value comes from the related account record. The name is copied to the **Bill to Contract Name** field on the invoice generated for the customer. |
| Payment Terms | Editable grid on the **Contract Customers** tab and main and quick create pages for a contract customer. | The default value comes from the related account record. The terms are copied over to **Bill to Contract Name** on the invoice generated for the customer. |
| Owning Company | Editable grid on the **Project Contract Customers** tab and the main and quick create pages for a project contract customer. | The legal entity in which the customer is set up in the **Project management and accounting** module. This field is read-only and set to the owning company of the project contract.</br>The list of customers to add in the **Account** field is already filtered to the list from the owning company in the **Project management and accounting** module of Project Operations. The owning company is equal to the legal entity in the **Project management and accounting** module of Project Operations. All costs and revenue accruing from the project are accounted for in the general ledger of the owning company. |
| Is Rounding | Editable grid on the **Contract Customers** tab and the main and quick create pages for a contract customer. | Indicates if the customer is a default rounding customer for the deal. There can only be one rounding customer on a project contract. When cost and unbilled sales split on quantity and lead to a rounding difference, that difference is applied to the actual that maps to the customer. |
| Not-to-exceed Limit | Editable grid on the **Contract Customers** tab and the main and quick create pages for a contract customer. | Indicates if there is a negotiated limit or cap to the overall amount that will be invoiced to the customer for the engagement. The not-to-exceed limit set up at the contract customer level is evaluated based on unbilled sales actuals that reference the contract customer. |

## Edit billing split percentages

You can edit billing split percentages by editing in the grid. When billing split percentages don't total 100 percent, an error occurs. After you edit a billing split percentage, refresh the **Project Contract** page to remove the error.

You can also select **Evenly Distribute** on the project contract customers subgrid. Billing splits are evenly allocated to all of the customers on the project contract. If there is any rounding factor, the factor will be added to the rounding customer. One of the contract customers always has the **Rounding** flag set to **Yes**. That customer is the rounding customer. Typically, the rounding customer is also the primary customer of the contract, but that isn't required.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
