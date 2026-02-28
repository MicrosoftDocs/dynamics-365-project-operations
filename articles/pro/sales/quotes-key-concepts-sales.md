---
title: Concepts unique to Project quotes
description: This article provides information about using project quotes in Project Operations.
author: poojafandan
ms.date: 02/26/2026
ms.topic: concept-article
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak
ms.author: poojafandan
---

# Concepts unique to Project quotes

[!INCLUDE[banner](../../includes/banner.md)]

_**Applies To:** Project Operations Core_


Before you start using project quotes in Dynamics 365 Project Operations, be aware of the following key concepts:

## Contracting unit

The contracting unit represents the division or practice that owns the project delivery. You can set up resource costs for each contracting unit. When you specify resource cost for a resource in the contracting unit, you can also set up different cost rates for resources that this contracting unit borrows from, or other division or practices within the enterprise. These cost rates are referred to as transfer prices, resource borrowing, or exchange prices. When you set up the cost of borrowing resources from other divisions, you can also choose to set up those cost rates in the currency of the lending division.

## Cost currency

Cost currency in Project Operations is the currency in which costs are reported. This currency comes from the currency attached to the **Contracting unit** field on the quote, contract, and project. You can log costs in any currency against a project. However, the system converts currency from the currency you recorded costs in, to the cost currency of the project.

> [!NOTE]
> Because the CDS platform can't use date-effective exchange rates, the on-screen totals for cost might change over time if you update currency exchange rates. However, costs recorded in the database remain unchanged because the amounts are stored in the currency that they were incurred in.

## Sales currency

Sales currency in Project Operations is the currency in which the estimated and actual sales amounts are recorded and shown. It's also the currency in which you invoice the customer for the deal. On a project quote, the sales currency defaults from the customer or account record and can be changed when you create the quote. After you save the quote, you can't change the sales currency. Product and project price lists default based on the sales currency of the quote.

Unlike costs, you can only record sales values in the sales currency.

## Billing method

Projects typically use fixed fee and consumption-based contracting models. Project Operations represents these models as **Billing Method** with two values: time and material, and fixed price.

- **Time and material:** Use this consumption-based contract model where each cost incurred has corresponding revenue. When you estimate or incur more costs, the corresponding estimated and actual sales also increase. Specify not-to-exceed limits on quote lines that use this billing method. This limit caps the actual revenue. Estimated revenue isn't impacted by not-to-exceed limits.
- **Fixed price:** Use this fixed fee contract model to indicate that sales values are independent of the costs incurred. The sales value is fixed and doesn't change when you estimate or incur more costs.

## Project price lists

Project price lists default prices, not cost rates, for time, expense, and other project-related components. You can have multiple price lists, and each list can have its own date effectivity for each project quote. Project Operations doesn't support overlapping date effectivity on project price lists.

## Product price lists

Product price lists default prices, not cost rates, for product-based lines on a quote. Each quote has only one product price list.

## Transaction classes

Project Operations supports four types of transaction classes:

- Time
- Expense
- Material
- Fee

You can estimate and incur cost and sales values on Time, Expense, and Material transaction classes. Fee is a revenue-only class of transactions.

## Work entities and billing entities

Projects and Tasks represent work. Quote lines and Contract lines represent billing. You can link different work entities to billing options by associating them with Quote or Contract lines.

## Multi-customer deals

Multi-customer deals occur when there's more than one customer to invoice. Common examples of this type of deal include:

- **OEM Enterprises and their partners:** Partners and resellers sell a product with value-added services. Usually, during a particular deal with a customer, the OEM offers to finance a portion of the project. 

- **Public sector projects:** Multiple departments of a local government agree to fund a project and are invoiced according to a previously agreed split. For example, a school district and the city or local government department agree to fund the building of a swimming pool.

## Invoice schedules

Each quote line can have its own invoice schedule, but it's optional. You create invoice schedules based on certain start and finish dates and invoice frequency. You use invoice schedules in the contract stage when you configure the automatic invoice creation process. In the quote stage, the schedules are optional. When you create invoice schedules in the **Quote** stage, you copy them to the project contract that is created when a project quote is won.

## Changes from Dynamics 365 Sales quote

Project Operations quotes are built on the Dynamics 365 Sales quotes. However, there are some important differences in functionality that you should be aware of:


- Project Operations quotes have two different types of lines. One type is for projects and the other type is for products.
- Project Operations quotes have their own form and UI elements, business rules, business logic in plug-ins, and client-side scripts that make them unique from Sales quotes.
- Sales quotes allow you to attach multiple orders to a sales quote. In Project Operations, you can attach only one project contract to a project quote.
- When you win a sales quote, the related opportunity can remain open. After a project quote is won, the related opportunity is closed.
- A sales quote doesn't include some fields and concepts that are included on a project quote. The fields include **Contracting Unit**, **Account Manager**, and **Bill to Contact Name**.  
- **Type**: Sales and project quotes are also identified by the option set–based field, **Type**. For a sales quote, this field has the value **Item-based**. For a project quote, it has the value **Work-based**.

For these reasons, don't use a Sales quote and a Project Operations quote interchangeably.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
