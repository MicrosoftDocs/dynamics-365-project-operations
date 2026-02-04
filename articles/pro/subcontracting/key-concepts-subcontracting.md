---
title: Key concepts in subcontracting
description: Learn key concepts in subcontracting for Microsoft Dynamics 365 Project Operations, including contracting units, purchase currency, and billing methods.
author: rumant
ms.date: 02/04/2026
ms.topic: concept-article
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak
ms.author: rumant
---

# Key concepts in subcontracting

[!INCLUDE[banner](../../includes/banner.md)]

_**Applies To:** Project Operations Integrated with ERP, Project Operations Core_

This article explains some key concepts that you should be aware of before you start to use the subcontracting functionality in Microsoft Dynamics 365 Project Operations.

## Contracting unit on the subcontract

The contracting unit represents the division or practice that owns the delivery of the eventual project. The contracting unit is also the division that enters into the contract relationship with the vendor.

## Purchase currency

In Project Operations, the purchase currency is the currency that you create the subcontract in. It's also the currency that you record subcontractor costs on a project in. The purchase currency can differ from the project currency, and the project currency can, in turn, differ from the sales currency.

## Billing methods on subcontract lines

For projects, there are typically fixed-fee and consumption-based contracting models. Project Operations supports these billing methods in the sales and purchase contexts. For a purchase, billing methods work in the following way:

- **Time and Material** – When a subcontract line uses the **Time and Material** billing method, the cost of time is recorded on the project as subcontractors work on that project and record time. These cost transactions from subcontractors are then matched with the line items on vendor invoices. In this model, project managers who use Project Operations can match and verify vendor invoice lines with subcontractor time that is recorded and approved. After the verification is completed, previous cost actuals that were recorded after approval are reversed, and new cost actuals that are based on the vendor invoice are created on the project.
- **Fixed Price** – In this fixed-fee contracting model, vendor invoices are based on fixed milestones. However, subcontractor resources can also report time. The time is then reviewed and approved by the project manager. When it's approved, Project Operations creates temporary cost actuals on the project. After the vendor sends an invoice for a milestone, the project manager can match previously recorded cost actuals against the milestone. When the verification is completed, the cost actuals are reversed, and the milestone-based cost is recorded.


    > [!IMPORTANT]
    > **Fixed Price** subcontracts aren't currently supported for _resource/non-stocked based scenarios_ in Project Operations. 

## Project price lists on subcontracts

Project price lists are price lists that you use to set up purchase prices for time, expense, and other project-related components. You can have multiple price lists, and each price list can have its own date-effective subcontract in Project Operations. Project Operations doesn't support overlapping effective dates on project price lists for a subcontract.

## Transaction classes on subcontracts

Project Operations supports four types of transaction classes:

- Time
- Expense
- Material
- Fee

You can estimate and incur purchase costs only on **Time**, **Expense**, and **Material** transaction classes. **Fee** is a revenue-only transaction class and isn't available in the context of purchasing.

## Purchase pricing dimensions

Pricing dimensions let you decide what attributes to use for purchase price setup and defaulting on time transactions. In relation to purchasing, Project Operations supports only fixed dimension sets for purchase price setup and defaulting. For purchase price setup and defaulting on subcontract lines and subcontract time transactions, the attributes are **Role** and **Bookable Resource**.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
