---
title: Concepts unique to Project Contracts
description: This article provides information about the key concepts of project contracts.
author: poojafandan
ms.author: poojafandan
ms.date: 06/07/2024
ms.topic: concept-article
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak

---

# Concepts unique to Project Contracts

[!INCLUDE[banner](../../includes/banner.md)]

_**Applies To:** Core deployment - deal to proforma invoicing_



This article provides the key concepts to be aware of before you begin using Project contracts in Dynamics 365 Project Operations:

## Contracting Unit

The contracting unit represents the division or practice that owns the delivery of the project. You can set up resource costs for each contracting unit. When you specify the resource cost for a resource, you will also be able to set up different cost rates for resources. This contracting unit borrows these resources from other division or practices within the enterprise. The cost rates for the resources are referred to as transfer prices, resource borrowing, or exchange prices. When you set up the cost rates to borrow resources from other divisions, use the currency of the lending division.

## Cost Currency

Cost currency is the currency in which costs are reported on screen. This currency is derived from the currency attached to the **Contracting Unit** field on the contract and the project. Costs can be logged in any currency against a project. However, there is currency conversion from the currency the costs were recorded in, to the cost currency of the project when shown on the screen.

Because the exchange rates in the Common Data Service (CDS) platform can't be date effective, the on-screen totals for cost may change over time if you update the currency exchange rates. However, costs as recorded in the database remain unchanged because the amounts are stored in the currency that were incurred in.

## Sales Currency

Sales currency in Project Operations is the currency in which the estimated and actual sales amounts are recorded and shown. Sales currency is also the currency in which the customer is invoiced for the deal. On a project contract, the sales currency defaults from the customer or account record and can be changed during when the contract is created. When a contract is created by closing a quote as won, the currency on the contract is defaulted from the currency on the quote.

When you create a project contract from scratch, the **Sales Currency** field can't be edited. Product and project price lists default based on this currency on the contract.

Unlike costs, sales values can only be recorded in the sales currency.

## Billing Method

There are typically two types of contracting models for projects, fixed fee and consumption-based. These models are represented in Project Operations as billing methods with two possible values:

- Time and Material: A consumption-based contracting model where each incurred cost is backed by corresponding revenue. As you estimate or incur more costs, the corresponding estimated and actual sales also increase. Specify not-to-exceed limits on contract lines that have this billing method that caps off the actual revenue. Estimated revenue isn't impacted by not-to-exceed limits.
- Fixed Price: A fixed fee contracting model that indicates the sales values will be independent of the costs incurred. The sales value is fixed and doesn't change as you estimate or incur more costs.

## Project Price lists

Project price lists are used to default prices, not cost rates, for time, expense, and other project-related components. There can be multiple prices lists. Each price list has its own date effectivity for each project contract. Overlapping date-effectivity on project price lists isn't supported in Project Operations.

When a project contract is created by winning a project quote, project price lists are copied with the contract name and date included. Copying this information constitutes custom pricing for project components on this project contract.

## Product price lists

Product price lists are used to default prices, not cost rates, for product-based lines on contract. There is only one product price list per contract.

## Transaction Classes

Project Operations supports four types of transaction classes:

- Time
- Expense
- Material
- Fee

Cost and sales values can be estimated and incurred on Time, Expense, and Material transaction classes. Fee is a revenue-only transaction class.

## Work entities and Billing entities

Entities that represent work are projects and tasks. Entities that represent billing aspects are contract lines. You can tie different work entities to billing options by tying them to contract lines.

## Multi-customer deals

Multi- customer deals have more than one customer to invoice on a deal. Common examples include:

- OEM Enterprises and their partners: Partners and resellers sell a product with some value-added services, typically involving a particular deal with a customer. The OEM offers to finance a portion of the project. 

- Public sector projects: Multiple departments of a local government agree to fund a project and are invoiced according to a previously agreed split. For example, s school district and the local government agree to fund the building of a swimming pool.

## Invoice Schedules

Invoice schedules are specific to each contract line and are required for automatic invoicing to work. Invoice schedules are created based on certain start and finish dates and invoice frequency. The schedules are used in the contract stage when the automatic invoice creation process is configured. When a project contract is created from a quote, the invoice schedule is copied to the project contract from the quote.

## Changes from the Dynamics 365 Sales contract

Project Operations contracts are built on Dynamics 365 Sales contracts. However, there are some important deviations and differences in functionality that you should be aware of:

- Project Operations contracts have two different types of lines, one for projects and one for products.
- Project Operations contracts have their own form and UI elements, business rules, business logic in plug-ins, and client-side scripts that make them unique from Sales contracts.

For these reasons, you shouldn't use a Sales contract and Project contract interchangeably.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
