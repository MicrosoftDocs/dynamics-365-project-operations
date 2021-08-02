---
title: Key concepts in subcontracting 
description: This topic provides some of key concepts that apply to subcontracting in Project Operations.
author: rumant
ms.date: 08/02/2021
ms.topic: article
ms.reviewer: kfend 
ms.author: rumant
---

# Key concepts in subcontracting

_**Applies To:** Lite deployment - deal to proforma invoicing_

The topic explains the key concepts that you should be aware of before you begin using the subcontracting functionality in Dynamics 365 Project Operations,

## Contracting unit on the subcontract

The contracting unit represents the division or practice that owns the delivery of the eventual project. The contracting unit is also the division that enters into the contract relationship with the vendor.

## Purchase currency

Purchase currency in Project Operations is the currency in which the subcontract is created. This is also the currency in which subcontractor costs are recorded on a project. The purchase currency can be different from the project currency which in turn can be different from the sales currency.

## Billing methods on subcontract lines

For projects, there are typically fixed fee and consumption-based contracting models. Project Operations supports these billing methods in the sales and purchase context. For a purchase, billing methods work as follows:

  - **Time and Material**: When a subcontract line has a Time and Material billing method, the cost of time is recorded on the project as subcontractors work on the project and record time. These cost transactions from subcontractors are then matched with the Vendor invoice lines items. In this model, Project Managers using Project Operations can match and verify Vendor invoice Lines with Subcontractor time that is recorded and approved. After the verification is complete, previous cost actuals that were recorded on approval are reversed, and new cost actuals that are based on the vendor invoice are created on the project.
- **Fixed Price**: This is a fixed fee contracting model where vendor invoices are based on fixed milestones. However, subcontractor resources can also report time. The time is then reviewed and approved by the project manager. On approval, Project Operations creates temporary cost actuals on the project. After the vendor sends an invoice for a milestone, the Project Manager can match previously recorded cost actuals against the milestone. When the verification is complete, the cost actuals are reversed and the milestone-based cost is recorded.

## Project price lists on subcontracts

Project price lists are price lists that are used to purchase prices for time, expense, and other project related components. There can be multiple prices lists and each price list can have its own date effective subcontract in Project Operations. Overlapping effective dates on project price lists for a subcontract aren't supported in Project Operations.

## Transaction classes on subcontracts

Project Operations supports 4 types of transaction classes:

  - Time
  - Expense
  - Material
  - Fee

Purchase costs can be estimated and incurred only on Time, Expense, and Material transaction classes. Fee is a revenue only class of transactions and isn't available in the content of purchasing.

## Purchase pricing dimensions

Pricing dimensions allow you to decide what attributes are used for price setup and default on Time transactions. As they relate to purchasing, the application supports only fixed dimension sets for purchase price setup and defaulting. The attributes for purchase price setup and defaulting on subcontract lines and subcontract time transactions are **Role** and **Bookable Resource**.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]

