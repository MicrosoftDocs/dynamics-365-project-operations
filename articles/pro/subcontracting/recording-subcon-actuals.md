---
title: Recording time, expenses, and material usage for subcontracted components
description: Learn how to track time, expenses, and material usage for subcontracted components in Microsoft Dynamics 365 Project Operations. Optimize project costing today!
author: rumant
ms.date: 01/30/2026
ms.topic: concept-article
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak
ms.author: rumant
---

# Recording time, expenses, and material usage on projects for subcontracted components

[!INCLUDE[banner](../../includes/banner.md)]

_**Applies To:** Project Operations Integrated with ERP,Project Operations Core_

This article explains how Microsoft Dynamics 365 Project Operations tracks time, expense, and material usage recorded on projects from subcontracted components.

## Costing for subcontractor time on projects

In Project Operations, contract workers can record time on projects in a similar manner as employees. When entering time on projects and project tasks, a contract worker can select a specific subcontract and subcontract line.

When project managers approve the time that contract workers submit, the system records the project cost by using the unit cost rate that you set up for that contract worker resource in the **Role prices** section of the purchase price list on the subcontract.

## Costing for subcontracted expenses on projects

When entering expenses incurred on projects, select a subcontract and subcontract line on the expense entry.

When project managers approve this expense entry, the system records the expense cost on the project based on the unit cost that you set up for that transaction category in the **Category prices** section of the purchase price list on the subcontract.

## Costing for subcontracted materials on projects

When entering material usage on projects, select a subcontract and subcontract line on the material usage log. When project managers approve the material usage log, the system records the material cost on the project based on the unit cost that you set up for that product in the **Price list items** section of subcontract price list.

You can also record material usage for write-in products on projects. You can link this type of material usage to a subcontract and subcontract line. When you record material usage for write-in products, enter the per unit cost of the write-in product.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
