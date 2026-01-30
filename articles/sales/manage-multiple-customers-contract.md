---
title: Manage multiple customers on project-based contracts
description: Learn about how to manage multiple customers on project-based contracts in Dynamics 365. Discover tips for handling billing splits, primary customers, and more.
author: rumant
ms.date: 01/30/2026
ms.topic: concept-article
ms.reviewer: johnmichalak
ms.author: rumant
---

# Manage multiple customers on project-based contracts

[!INCLUDE[banner](includes/banner.md)]

This article provides information about how to manage multiple customers on a project contract. Use a project contract when you need a contractual agreement for multiple customers to fund a deal. On the **Project Contract** page, the **Summary** tab includes information about the primary customer for a deal. Add other customers that participate in the deal to the **Customers** tab.

All contract customers on the **Customers** tab of the project contract default as contract line customers on any new project-based contract lines you create for the project contract. Any existing project-based contract lines don't inherit new contract customers records that you create later.

You can add, update, or delete contract and contract line customers anytime before the contract is won. Set up a customer on the project contract as a customer in the owning company or legal entity on the **Customers** page. Set up legal entities in the **Project management and accounting** module of Dynamics 365 Project Operations. These legal entities are available as companies in the **Project Sales** and **Delivery** modules of Project Operations.

## Primary customers

The potential customer on the **Summary** tab of the project contract is the primary customer of the contract. You can't update the primary customer from the contract customer's list. If you try to delete the primary customer from a customer list on contract, an error occurs that says a primary customer record on a contract can't be deleted. Instead, change the customer in the **Potential Customer** field on the **Summary** tab of the project contract. When you update this field, the newly selected customer is added as a new contract customer with the **Primary** flag set to **Yes**. The previous primary customer is still a customer on the contract, but they're no longer the primary customer.

## Create, update, or delete a contract customer record

You can create, update, or delete a contract customer from the **Contract Customers** tab on the **Contract** page. The following fields are included on the contract customer record of a project contract.

| **Field** | **Location** | **Description** | 
| --- | --- | --- | 
| Account | Editable grid on the **Contract Customers** tab and the main and quick create pages for a contract customer. | Lists all the active accounts. This field is locked after the record is created. To update the record, you must delete it and then re-create it. If you recorded any actuals, or if the contract customer record is a primary customer, you can't delete the record. When you create a contract line, you copy contract customers as contract line customers. |
| Billing Split Percent | Editable grid on **Contract Customers** tab and the main and quick create pages for a contract customer. | Represents the percentage of each unbilled sales transaction attributed to the contract customer. When you create new project contract lines, you copy the billing split percent to new contract lines and to project contract line customers. |
| Bill to Contact Name | Editable grid on the **Contract Customers** tab and the main and quick create pages for a contract customer. | Use this text field to identify the invoice contact person for the customer. The related account record provides the default value. You copy the contact name to **Bill to Contract Name** on the invoice generated for the customer. |
| Bill To Name | Editable grid on the **Contract Customers** tab and the main and quick create pages for a contract customer. | Use this field to identify the invoice contact person for the customer. The related account record provides the default value. You copy the name to the **Bill to Contract Name** field on the invoice generated for the customer. |
| Payment Terms | Editable grid on the **Contract Customers** tab and main and quick create pages for a contract customer. | The related account record provides the default value. You copy the terms over to **Bill to Contract Name** on the invoice generated for the customer. |
| Owning Company | Editable grid on the **Project Contract Customers** tab and the main and quick create pages for a project contract customer. | The legal entity in which you set up the customer in the **Project management and accounting** module. This field is read-only and set to the owning company of the project contract.</br> The list of customers to add in the **Account** field is already filtered to the list from the owning company in the **Project management and accounting** module of Project Operations. The owning company is equal to the legal entity in the **Project management and accounting** module of Project Operations. All costs and revenue accruing from the project are accounted for in the general ledger of the owning company. |
| Is Rounding | Editable grid on the **Contract Customers** tab and the main and quick create pages for a contract customer. | Indicates if the customer is a default rounding customer for the deal. There can only be one rounding customer on a project contract. When cost and unbilled sales split on quantity and lead to a rounding difference, that difference is applied to the actual that maps to the customer. |
| Not-to-exceed Limit | Editable grid on the **Contract Customers** tab and the main and quick create pages for a contract customer. | Indicates if there's a negotiated limit or cap to the overall amount that you invoice to the customer for the engagement. The not-to-exceed limit that you set up at the contract customer level is evaluated based on unbilled sales actuals that reference the contract customer. |

## Edit billing split percentages

You can edit billing split percentages directly in the grid. If the billing split percentages don't total 100 percent, an error occurs. After you edit a billing split percentage, refresh the **Project Contract** page to remove the error.

You can also select **Evenly Distribute** on the project contract customers subgrid. This action evenly allocates billing splits to all of the customers on the project contract. If there's any rounding factor, the factor goes to the rounding customer. One of the contract customers always has the **Rounding** flag set to **Yes**. That customer is the rounding customer. Typically, the rounding customer is also the primary customer of the contract, but it isn't required.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
