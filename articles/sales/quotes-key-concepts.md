---
# required metadata

title: Concepts unique to project-based quotes
description: This article provides information about project quotes in Microsoft Dynamics 365 Project Operations.
author: rumant
ms.date: 12/02/2022
ms.topic: concept-article
 
#

# optional metadata

# ms.search.form: 
# ROBOTS: 
audience: Application User
# ms.devlang: 
ms.reviewer: johnmichalak
ms.search.scope: 
# ms.tgt_pltfrm: 
ms.custom: 
ms.assetid: 
ms.search.region: Global
ms.search.industry: Service industries
ms.author: rumant
ms.dyn365.ops.version: 
ms.search.validFrom: 2020-10-01
---

# Concepts unique to project-based quotes

_**Applies To:** Project Operations for resource/non-stocked based scenarios_

Before you start to use project quotes in Microsoft Dynamics 365 Project Operations, you should be aware of the following key concepts.

## Owning company

The owning company represents the legal entity that owns the project delivery. The customer on the quote should be a valid customer in that legal entity in finance and operations apps. The currency of the owning company and the currency of the contracting unit that's selected on a project-based quote must match.

## Contracting unit

A contracting unit represents the division or practice that owns the project delivery. You can set up resource costs for each contracting unit. When you specify resource costs for a resource in a contracting unit, you can set up different cost rates for resources that the contracting unit borrows from, or for other divisions or practices in the enterprise. These cost rates are referred to as transfer prices, resource borrowing, or exchange prices. When you set up the cost of borrowing resources from other divisions, you can set up the cost rates in the currency of the lending division.

## Cost currency

The cost currency in Project Operations is the currency that costs are reported in. This currency is derived from the currency that's attached to the **Contracting unit** field on the quote, contract, and project. Costs against a project can be recorded in any currency. However, there's currency conversion from the currency that the costs were recorded in to the cost currency of the project.

Because exchange rates on the Dataverse platform can't be date-effective, the on-screen totals for cost might change over time if you update currency exchange rates. However, costs that are recorded in the database remain unchanged, because the amounts are stored in the currency that they were incurred in.

## Sales currency

The sales currency in Project Operations is the currency that the estimated and actual sales amounts are recorded and shown in. It's also the currency that the customer is invoiced in for the deal. For a project quote, a default sales currency is set from the customer or account record, and it can be changed when the quote is created. However, the sales currency can't be changed after the quote is saved. Default product and project price lists are set based on the sales currency of the quote.

Unlike costs, sales values can be recorded **only** in the sales currency.

## Billing method

Projects typically have fixed-fee and consumption-based contracting models. In Project Operations, a project's contracting model is represented by the billing method. The billing method has two values: time and material and fixed price.

- **Time and material** – A consumption-based contracting model where each cost that's incurred is backed by corresponding revenue. As you estimate or incur more costs, the corresponding estimated and actual sales also increase. You can specify not-to-exceed limits on quote lines that have this billing method. In this way, you can cap the actual revenue. Estimated revenue isn't affected by not-to-exceed limits.
- **Fixed price** – A fixed-fee contracting model where sales values are independent of the costs that are incurred. The sales value is fixed and doesn't change as you estimate or incur more costs.

## Project price lists

Project price lists are price lists that are used to enter default prices, not cost rates, for time, expense, and other project-related components. There can be multiple prices lists, and each list can have its own date effectivity for each project quote. Project Operations doesn't support overlapping date effectivity for project price lists.

## Product price lists

Product price lists are price lists that are used to enter default prices, not cost rates, for product-based lines on a quote. There's only one product price list per quote.

## Transaction classes

Project Operations supports four types of transaction classes:

- Time
- Expense
- Material
- Fee

Cost and sales values can be estimated and incurred on **Time**, **Expense**, and **Material** transaction classes. **Fee** is a revenue-only transaction class.

## Work entities and billing entities

Projects and Tasks are entities that represent work. Quote lines and Contract lines are entities that represent billing. You can link different work entities to billing options by associating them with Quote lines or Contract lines.

## Multi-customer deals

Multi-customer deals occur when there's more than one customer per invoice. Here are some typical examples:

- **Original equipment manufacturer (OEM) enterprises and their partners** – Partners and resellers sell a product that includes value-added services. During a deal with a customer, the OEM usually offers to finance part of the project.
- **Public sector projects** – Multiple departments of a local government agree to fund a project and are invoiced according to a previously agreed-on split. For example, a school district and the city or local government department agree to fund the building of a swimming pool.

## Invoice schedules

Invoice schedules are specific to each quote line and are optional. Invoice schedules are created based on specific start and end dates and an invoice frequency. They're used during the contract stage, when the automatic invoice creation process is configured. During the quote stage, invoice schedules are optional. If they're created during the quote stage, they're copied to the project contract that's created when a project quote is won.

## Differences from Dynamics 365 Sales quotes

Project Operations quotes are built on Dynamics 365 Sales quotes. However, there are some important differences in functionality that you should be aware of:

- Project Operations quotes have two different types of lines: one for projects and one for products.
- Project Operations quotes have their own page and user interface (UI) elements, business rules, business logic in plug-ins, and client-side scripts that make them distinct from Sales quotes.
- In Sales, you can attach multiple orders to a single sales quote. In Project Operations, you can attach only one project contract to a project quote.
- When you win a sales quote, the related opportunity can remain open. After a project quote is won, the related opportunity is closed.
- A sales quote doesn't include some fields and concepts that a project quote includes. The fields include **Contracting Unit**, **Account Manager**, and **Bill to Contact Name**.
- Sales quotes and project quotes are identified by the option set–based **Type** field. For a sales quote, the value of this field is **Item-based**. For a project quote, the value is **Work-based**.

Because of these differences, we don't recommend that you use Sales quotes and Project Operations quotes interchangeably.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
