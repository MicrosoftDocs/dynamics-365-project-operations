---
title: Concepts unique to Project-based Contracts
description: This article provides information about the key concepts of project contracts in Project Operations.
author: suvaidya
ms.date: 01/23/2026
ms.topic: concept-article
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak
ms.author: nshrivastava
---

# Concepts unique to Project-based Contracts

_**Applies To:** Project Operations Integrated with ERP_

Before you start using Project contracts in Dynamics 365 Project Operations, review these key concepts:

## Owning company

The **owning company** is the legal entity from the **Project management and accounting** module for Project Operations from Dynamics 365 Finance. The owning company represents the legal entity that accounts for the cost and revenue that accrues from a deal.

## Contracting unit

The **contracting unit** represents the division or practice that owns the delivery of the project. You can set up resource costs for each contracting unit. When you specify the resource cost for a resource, you can also set up different cost rates for resources. This contracting unit borrows these resources from other divisions or practices within the enterprise. The cost rates for the resources are referred to as transfer prices, resource borrowing, or exchange prices. When you set up the cost rates to borrow resources from other divisions, use the currency of the lending division.

## Cost currency

The **cost currency** is the currency in which costs are reported on screen. This currency comes from the currency attached to the **Contracting Unit** field on the contract and the project. You can log costs in any currency against a project. However, currency conversion happens from the currency you recorded the costs in to the cost currency of the project when shown on the screen.

Because the exchange rates in the Common Data Service (CDS) platform aren't date effective, the on-screen totals for cost might change over time if you update the currency exchange rates. However, costs as recorded in the database remain unchanged because the amounts are stored in the currency that you incurred.

## Sales currency

In Project Operations, the **sales currency** is the currency in which you record and show the estimated and actual sales amounts. The sales currency is also the currency in which you invoice the customer for the deal. On a project contract, the sales currency defaults from the customer or account record and can be changed during the contract creation. When you create a contract by closing a quote as won, the currency on the contract defaults from the currency on the quote.

When you create a project contract from scratch, you can't edit the **Sales Currency** field. Product and project price lists default based on this currency on the contract.

Unlike costs, you can only record sales values in the sales currency.

## Billing method

Typically, two types of contracting models exist for projects: fixed fee and consumption-based. Project Operations represents these models as billing methods with two possible values:

- Time and Material: A consumption-based contracting model where each incurred cost has corresponding revenue. As you estimate or incur more costs, the corresponding estimated and actual sales also increase. Specify not-to-exceed limits on contract lines that have this billing method, which caps the actual revenue. Estimated revenue isn't impacted by not-to-exceed limits.
- Fixed Price: A fixed fee contracting model that indicates the sales values are independent of the costs incurred. The sales value is fixed and doesn't change as you estimate or incur more costs.

## Project price lists

Use project price lists to default prices, not cost rates, for time, expense, and other project-related components. You can have multiple price lists. Each price list has its own date effectivity for each project contract. Project Operations doesn't support overlapping date-effectivity on project price lists.

When you create a project contract by winning a project quote, you copy project price lists with the contract name and date included. Copying this information constitutes custom pricing for project components on this project contract.

## Transaction classes

Project Operations supports four types of transaction classes:

- Time
- Expense
- Material
- Fee

You can estimate and incur cost and sales values on Time, Expense, and Material transaction classes. Fee is a revenue-only transaction class.

## Work entities and billing entities

Projects and tasks represent work entities. Contract lines represent billing entities. You can tie different work entities to billing options by tying them to contract lines.

## Multicustomer deals

Multicustomer deals have more than one customer to invoice on a deal. Common examples of this type of deal include the following examples:

- OEM Enterprises and their partners: Partners and resellers sell a product with some value-added services, typically involving a particular deal with a customer. The OEM offers to finance a portion of the project.

- Public sector projects: Multiple departments of a local government agree to fund a project and are invoiced according to a previously agreed split. For example, a school district and the local government agree to fund the building of a swimming pool.

## Invoice schedules

Each contract line requires an invoice schedule for automatic invoicing to work. Create invoice schedules based on certain start and finish dates and invoice frequency. Use the schedules in the contract stage when you configure the automatic invoice creation process. When you create a project contract from a quote, the invoice schedule is copied to the project contract from the quote.

## Changes from Dynamics 365 Sales Orders

Project Operations contracts are built on Dynamics 365 Sales orders. However, important deviations and differences in functionality exist. Contracts have their own form and UI elements, business rules, business logic in plug-ins, and client-side scripts that make them unique from orders. For these reasons, don't use a Sales order and Project Operations contract interchangeably.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
