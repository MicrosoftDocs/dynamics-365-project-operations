---
title: Concepts unique to project-based quotes
description: Learn about project quotes in Microsoft Dynamics 365 Project Operations.
author: rumant
ms.date: 01/30/2026
ms.topic: concept-article
audience: Application User
ms.reviewer: johnmichalak
ms.search.region: Global
ms.search.industry: Service industries
ms.author: rumant
ms.dyn365.ops.version: 
ms.search.validFrom: 2020-10-01
---

# Concepts unique to project-based quotes

[!INCLUDE[banner](includes/banner.md)]

_**Applies To:** Project Operations Integrated with ERP_

Before you start using project quotes in Microsoft Dynamics 365 Project Operations, be aware of the following key concepts.

## Owning company

The owning company represents the legal entity that owns the project delivery. The customer on the quote should be a valid customer in that legal entity in finance and operations apps. The currency of the owning company and the currency of the contracting unit that you select on a project-based quote must match.

## Contracting unit

A contracting unit represents the division or practice that owns the project delivery. You can set up resource costs for each contracting unit. When you specify resource costs for a resource in a contracting unit, you can set up different cost rates for resources that the contracting unit borrows from, or for other divisions or practices in the enterprise. These cost rates are referred to as transfer prices, resource borrowing, or exchange prices. When you set up the cost of borrowing resources from other divisions, you set up the cost rates in the currency of the lending division.

## Cost currency

The cost currency in Project Operations is the currency that costs are reported in. This currency comes from the currency that you attach to the **Contracting unit** field on the quote, contract, and project. You can record costs against a project in any currency. However, there's currency conversion from the currency that you record the costs in to the cost currency of the project.

Because exchange rates on the Dataverse platform aren't date-effective, the on-screen totals for cost might change over time if you update currency exchange rates. However, costs that you record in the database remain unchanged, because you store the amounts in the currency that you incur them in.

## Sales currency

The sales currency in Project Operations is the currency that you record and show the estimated and actual sales amounts in. It's also the currency that you invoice the customer in for the deal. For a project quote, you set a default sales currency from the customer or account record, and you can change it when you create the quote. However, you can't change the sales currency after you save the quote. You set default product and project price lists based on the sales currency of the quote.

Unlike costs, you can record sales values **only** in the sales currency.

## Billing method

Projects typically use fixed-fee and consumption-based contracting models. In Project Operations, the billing method represents a project's contracting model. The billing method has two values: time and material, and fixed price.

- **Time and material** – A consumption-based contracting model where each cost that the project incurs has corresponding revenue. As you estimate or incur more costs, the corresponding estimated and actual sales also increase. You can specify not-to-exceed limits on quote lines that use this billing method. In this way, you can cap the actual revenue. Estimated revenue isn't affected by not-to-exceed limits.
- **Fixed price** – A fixed-fee contracting model where sales values are independent of the costs that the project incurs. The sales value is fixed and doesn't change as you estimate or incur more costs.

## Project price lists

Project price lists are price lists that you use to enter default prices, not cost rates, for time, expense, and other project-related components. You can have multiple price lists, and each list can have its own date effectivity for each project quote. Project Operations doesn't support overlapping date effectivity for project price lists.

## Product price lists

Product price lists are price lists that you use to enter default prices, not cost rates, for product-based lines on a quote. There's only one product price list per quote.

## Transaction classes

Project Operations supports four types of transaction classes:

- Time
- Expense
- Material
- Fee

You can estimate and incur cost and sales values on **Time**, **Expense**, and **Material** transaction classes. **Fee** is a revenue-only transaction class.

## Work entities and billing entities

Projects and Tasks are entities that represent work. Quote lines and Contract lines are entities that represent billing. You can link different work entities to billing options by associating them with Quote lines or Contract lines.

## Multi-customer deals

Multi-customer deals occur when there's more than one customer per invoice. Here are some typical examples:

- **Original equipment manufacturer (OEM) enterprises and their partners** – Partners and resellers sell a product that includes value-added services. During a deal with a customer, the OEM usually offers to finance part of the project.
- **Public sector projects** – Multiple departments of a local government agree to fund a project and are invoiced according to a previously agreed-on split. For example, a school district and the city or local government department agree to fund the building of a swimming pool.

## Invoice schedules

Invoice schedules are specific to each quote line and are optional. Create invoice schedules based on specific start and end dates and an invoice frequency. Use them during the contract stage, when you configure the automatic invoice creation process. During the quote stage, invoice schedules are optional. If you create them during the quote stage, they're copied to the project contract that's created when a project quote is won.

## Differences from Dynamics 365 Sales quotes

Project Operations quotes are built on Dynamics 365 Sales quotes. However, there are some important differences in functionality that you should be aware of:

- Project Operations quotes have two different types of lines: one for projects and one for products.
- Project Operations quotes have their own page and user interface (UI) elements, business rules, business logic in plug-ins, and client-side scripts that make them distinct from Sales quotes.
- In Sales, you can attach multiple orders to a single sales quote. In Project Operations, you can attach only one project contract to a project quote.
- When you win a sales quote, the related opportunity can remain open. After a project quote is won, the related opportunity is closed.
- A sales quote doesn't include some fields and concepts that a project quote includes. The fields include **Contracting Unit**, **Account Manager**, and **Bill to Contact Name**.
- Sales quotes and project quotes are identified by the option set–based **Type** field. For a sales quote, the value of this field is **Item-based**. For a project quote, the value is **Work-based**.

Because of these differences, don't use Sales quotes and Project Operations quotes interchangeably.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
