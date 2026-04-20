---
title: Concepts unique to Project Contracts
description: This article provides information about the key concepts of project contracts.
author: poojafandan
ms.author: poojafandan
ms.date: 02/26/2026
ms.topic: concept-article
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak

---

# Concepts unique to Project Contracts

[!INCLUDE[banner](../../includes/banner.md)]

_**Applies To:** Project Operations Core_



This article provides the key concepts to be aware of before you begin using Project contracts in Dynamics 365 Project Operations:

## Contracting Unit

The contracting unit represents the division or practice that owns the delivery of the project. You can set up resource costs for each contracting unit. When you specify the resource cost for a resource, you can also set up different cost rates for resources. This contracting unit borrows these resources from other divisions or practices within the enterprise. The cost rates for the resources are referred to as transfer prices, resource borrowing, or exchange prices. When you set up the cost rates to borrow resources from other divisions, use the currency of the lending division.

## Cost Currency

Cost currency is the currency in which costs are reported on screen. This currency comes from the currency attached to the **Contracting Unit** field on the contract and the project. You can log costs in any currency against a project. However, currency conversion happens from the currency you recorded the costs in to the cost currency of the project when shown on the screen.

Because the exchange rates in the Common Data Service (CDS) platform aren't date effective, the on-screen totals for cost might change over time if you update the currency exchange rates. However, costs as recorded in the database remain unchanged because the amounts are stored in the currency that you incurred.

## Sales Currency

Sales currency in Project Operations is the currency in which the estimated and actual sales amounts are recorded and shown. Sales currency is also the currency in which the customer is invoiced for the deal. On a project contract, the sales currency defaults from the customer or account record and can be changed during the contract creation. When you create a contract by closing a quote as won, the currency on the contract is defaulted from the currency on the quote.

When you create a project contract from scratch, you can't edit the **Sales Currency** field. Product and project price lists default based on this currency on the contract.

Unlike costs, you can only record sales values in the sales currency.

## Billing method

Typically, projects use two types of contracting models: fixed fee and consumption-based. Project Operations represents these models as billing methods with two possible values:

- Time and Material: A consumption-based contracting model where each incurred cost is backed by corresponding revenue. As you estimate or incur more costs, the corresponding estimated and actual sales also increase. Specify not-to-exceed limits on contract lines that have this billing method that caps off the actual revenue. Estimated revenue isn't impacted by not-to-exceed limits.
- Fixed Price: A fixed fee contracting model that indicates the sales values are independent of the costs incurred. The sales value is fixed and doesn't change as you estimate or incur more costs.

## Project price lists

Use project price lists to set default prices, not cost rates, for time, expense, and other project-related components. You can have multiple project price lists. Each price list has its own date effectivity for each project contract. Project Operations doesn't support overlapping date-effectivity on project price lists.

When you create a project contract by winning a project quote, you copy project price lists with the contract name and date included. Copying this information creates custom pricing for project components on this project contract.

## Product price lists

Use product price lists to set default prices, not cost rates, for product-based lines on contract. Each contract has only one product price list.

## Transaction classes

Project Operations supports four types of transaction classes:

- Time
- Expense
- Material
- Fee

You can estimate and incur cost and sales values on Time, Expense, and Material transaction classes. Fee is a revenue-only transaction class.

## Work entities and billing entities

Entities that represent work are projects and tasks. Entities that represent billing aspects are contract lines. You can tie different work entities to billing options by tying them to contract lines.

## Multi-customer deals

Multi-customer deals have more than one customer to invoice on a deal. Common examples include:

- OEM Enterprises and their partners: Partners and resellers sell a product with some value-added services, typically involving a particular deal with a customer. The OEM offers to finance a portion of the project. 

- Public sector projects: Multiple departments of a local government agree to fund a project and are invoiced according to a previously agreed split. For example, a school district and the local government agree to fund the building of a swimming pool.

## Invoice schedules

Invoice schedules are specific to each contract line and are required for automatic invoicing to work. Create invoice schedules based on certain start and finish dates and invoice frequency. Use the schedules in the contract stage when you configure the automatic invoice creation process. When you create a project contract from a quote, the invoice schedule is copied to the project contract from the quote.

## Changes from the Dynamics 365 Sales contract

Project Operations contracts are built on Dynamics 365 Sales contracts. However, be aware of some important deviations and differences in functionality:

- Project Operations contracts have two different types of lines, one for projects and one for products.
- Project Operations contracts have their own form and UI elements, business rules, business logic in plug-ins, and client-side scripts that make them unique from Sales contracts.

For these reasons, don't use a Sales contract and Project contract interchangeably.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
