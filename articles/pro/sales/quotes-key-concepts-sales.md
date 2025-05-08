---
title: Concepts unique to Project quotes
description: This article provides information about using project quotes in Project Operations.
author: poojafandan
ms.date: 06/07/2024
ms.topic: concept-article
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak
ms.author: poojafandan
---

# Concepts unique to Project quotes

[!INCLUDE[banner](../../includes/banner.md)]

_**Applies To:** Lite deployment - deal to proforma invoicing_


The following are key concepts to be aware of before you begin using project quotes in Dynamics 365 Project Operations:

## Contracting unit

The contracting unit represents the division or practice that owns the project delivery. You can set up resource costs for each contracting unit. When you specify resource cost for a resource in the contracting unit, you will also be able to set up different cost rates for resources that this contracting unit borrows from, or other division or practices within the enterprise. These are referred to as transfer prices, resource borrowing, or exchange prices. When you set up the cost of borrowing resources from other divisions, you can also choose to set up those cost rates in the currency of the lending division.

## Cost currency

Cost currency in Project Operations is the currency in which costs are reported. This currency is derived from the currency attached to the **Contracting unit** field on the quote, contract, and project. Costs can be logged in any currency against a project. However, there is currency conversion from the currency costs were recorded in, to the cost currency of the project.

Because of the exchange rates in the CDS platform can't be date-effective, the on-screen totals for cost may change over time if you update currency exchange rates. However, costs recorded in the database remain unchanged because the amounts are stored in the currency that they were incurred in.

## Sales currency

Sales currency in Project Operations is the currency in which the estimated and actual sales amounts are recorded and shown. It is also the currency in which the customer is invoiced for the deal. On a project quote, the sales currency defaults from the customer or account record and can be changed when the quote is created. After the quote is saved, the sales currency can't be changed. Product and project price lists default based on the sales currency of the quote.

Unlike costs, sales values can only be recorded in the Sales currency.

## Billing method

Projects typically have fixed fee and consumption-based contracting models. This is represented in Project Operations as **Billing Method** and has two values, time and material and fixed price.

- **Time and material:** This is a consumption-based contract model where each cost incurred is backed by corresponding revenue. As you estimate or incur more costs, the corresponding estimated and actual sales will also increase. You can specify not-to-exceed limits on quote lines that have this billing method. This will cap off the actual revenue. Estimated revenue is not impacted by not-to-exceed limits.
- **Fixed price:** This is a fixed fee contract model that indicates the sales values will be independent of the costs incurred. The sales value is fixed and does not change as you estimate or incur more costs.

## Project price lists

Project price lists are price lists that are used to default prices, not cost rates, for time, expense, and other project-related components. There can be multiple prices lists, and each list can have its own date effectivity for each project quote. Overlapping date effectivity on project price lists is not supported in Project Operations.

## Product price lists

Product price lists are price lists that are used to default prices, not cost rates, for product-based lines on a quote. There is only one product price list per quote.

## Transaction classes

Project Operations supports four types of transaction classes:

- Time
- Expense
- Material
- Fee

Cost and sales values can be estimated and incurred on Time, Expense, and Material transaction classes. Fee is a revenue only class of transactions.

## Work entities and billing entities

Entities that represent work are Projects and Tasks. Entities that represent billing are Quote lines and Contract lines. You can link different work entities to billing options by associating them with Quote or Contract lines.

## Multi-customer deals

Multi-customer deals occur are when there is more than one customer to invoice. Common examples of this include:

- **OEM Enterprises and their partners:** Partners and resellers sell a product with value-added services. This is usually a scenario where during a particular deal with a customer, the OEM offers to finance a portion of the project. 

- **Public sector projects:** Multiple departments of a local government agree to fund a project and are invoiced according to a previously agreed split. For example, a school district and the city or local government department agree to fund the building of a swimming pool.

## Invoice schedules

Invoice schedules are specific to each quote line and are also optional. Invoice schedules are created based on certain start and finish dates and invoice frequency. Invoice schedules are used in the contract stage when the automatic invoice creation process is configured. In the quote stage, the schedules are optional. When invoice schedules are created in the **Quote** stage, they are copied to the project contract that is created when a project quote is won.

## Changes from Dynamics 365 Sales quote:

Project Operations quotes are built on the Dynamics 365 Sales quotes. However, there are some important differences in functionality that you should be aware of:


- Project Operations quotes have two different types of lines. One is for projects and the other is for products.
- Project Operations quotes have their own form and UI elements, business rules, business logic in plug-ins, and client-side scripts that make them unique from Sales quotes.
- Sales quotes allow you to attach multiple orders to a sales quote. In Project Operations, only one project contract can be attached to a project quote.
- When you win a sales quote, the related opportunity can remain open. After a project quote is won, the related opportunity is closed.
- A sales quote doesn't include some fields and concepts that are included on a project quote. The fields include **Contracting Unit**, **Account Manager**, and **Bill to Contact Name**.  
- **Type**: Sales and project quotes are also identified by the option set–based field, **Type**. For a sales quote, this field has the value **Item-based**. For a project quote, it has the value **Work-based**.

For these reasons, it is not recommended to use a Sales quote and a Project Operations quote interchangeably.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
