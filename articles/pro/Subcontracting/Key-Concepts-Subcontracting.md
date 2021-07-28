---
title: Key concepts in Subcontracting 
description: This topic provides some of key concepts as they apply to Subcontracting in Project Operations.
author: rumant
ms.date: 07/28/2021
ms.topic: article
ms.reviewer: kfend 
ms.author: rumant
---

# Key concepts in Subcontracting

_**Applies To:** Lite deployment - deal to proforma invoicing_

# Key Concepts of subcontracting in Project Operations:

The following are key concepts to be aware of before you begin using Subcontracting experiences in Project Operations:

## Contracting Unit on the subcontract

Contracting unit represents the division or practice that owns the delivery of the eventual project. This is also the division that is entering into the contract relationship with the vendor

## Purchase Currency

Purchase currency in Project Operations is the currency in which the subcontract is created. This is also the currency in which subcontractor costs are recorded on a project. Purchase currency can be different from the Project currency which in turn can be different from the sales currency.

## Billing Methods on Subcontract Lines

In the world of projects, there are typically fixed fee and consumption-based contracting models. Project Operations supports these billing methods in the Sales and Purchase context. In the purchase context, the following is how Billing Methods work:

- Time and Material: When a subcontract line has a Time and Material billing method, as subcontractors work on projects and record time, the cost of that time is recorded on the project. These cost transactions from subcontractors are then matched with the Vendor Invoice lines items. In this model, Project Managers using Project Operations will be able to match and verify Vendor Invoice Lines with Subcontractor Time that is recorded and approved and the original subcontracted line. Once is verification is complete, previous cost actuals that were recorded on approval are reversed and new cost actuals based vendor invoice are created on the project.
- Fixed Price: This is a fixed fee contracting model where the vendor invoices based fixed milestones. However, subcontractor resources can also report time which is reviewed and approved by the project manager. On approval, Project Operations creates &quot;temporary cost actuals&quot; on the project. Once the vendor sends an invoice for a milestone, the system allows the Project Manager to match previously recorded cost actuals against the milestone. Once the verification is complete, the cost actuals are reversed and the milestone – based cost is recorded in the system.

## Project Price lists on Subcontracts

Project price lists are price lists that will used to purchase prices for time, expense and other project related components. There can be multiple prices lists each with its own date effectivity a Subcontract in Project Operations. Overlapping date – effectivities on project price lists on a Subcontract are not supported in Project Operations.

## Transaction Classes on Subcontracts

Project Operations supports 4 types of transaction classes:

1. Time
2. Expense
3. Material
4. Fee

Purchase costs can be estimated and incurred ONLY on Time, Expense and Material transaction classes. Fee is a revenue only class of transactions and is not available in the Purchase context

## Purchase pricing dimensions

Pricing dimensions are a concept in Project Operations that allow a customer to decide what attributes will used for price setup and defaulting on Time transactions. In the purchase context, the application supports only fixed dimension sets for purchase price setup and defaulting. The attributes for purchase price setup (definition) and defaulting on Subcontract lines and Subcontract Time transactions are Role and Bookable Resource.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]

