---
title: Recording time, expenses, and material usage for subcontracted components
description: This article explains how time, expense, and material usage recorded on projects from subcontracted components is tracked by Microsoft Dynamics 365 Project Operations.
author: rumant
ms.date: 12/15/2023
ms.topic: concept-article
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak
ms.author: rumant
---

# Recording time, expenses, and material usage on projects for subcontracted components

[!INCLUDE[banner](../../includes/banner.md)]

_**Applies To:** Project Operations Integrated with ERP,Project Operations Core_

This article explains how time, expense, and material usage recorded on projects from subcontracted components is tracked by Microsoft Dynamics 365 Project Operations.

## Costing for subcontractor time on projects
In Project Operations, contract workers can record time on projects in a similar manner as employees. When entering time on projects and/or project tasks, a contract worker can select a specific subcontract and subcontract line.

When the time submitted by contract workers is approved, the project cost is recorded using the unit cost rate that is set up for that contract worker resource in the **Role prices** section of the purchase price list on the subcontract.

## Costing for subcontracted expenses on projects
When entering expenses incurred on projects, you can select a subcontract and subcontract line on the expense entry. 

When this expense entry is submitted and approved, the expense cost is recorded on the project based on the unit cost that is set up for that transaction category in the **Category prices** section of the purchase price list on the subcontract.

## Costing for subcontracted materials on projects
When entering material usage on projects, you can select a subcontract and subcontract line on the material usage log. When the material usage log is submitted and approved, the material cost is recorded on the project based on the unit cost that is set up for that product in the **Price list items** section of subcontract price list.

Material usage can also be recorded for write–in products on projects. This type of material usage can also be linked to a subcontract and subcontract line. When recording material usage for write-in products, you need to enter the per unit cost of the write-in product. 


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
