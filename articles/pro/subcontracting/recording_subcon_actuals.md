---
title: Recording time, expenses and material usage for subcontracted components
description: This topic explains how time, expense and material usage recorded on projects from subcontracted components is tracked by Dynamics 365 Project Operations.
author: rumant
ms.date: 12/03/2021
ms.topic: article
ms.reviewer: tonyafehr 
ms.author: rumant
---

# Recording time, expenses and material usage on projects for subcontracted components

[!include [banner](../../includes/dataverse-preview.md)]

_**Applies To:** Lite deployment - deal to proforma invoicing_

## Costing for Subcontractor time on projects
In Project Operations, contract workers can record time on projects just as employees are able to. When entering time on projects and or project tasks, a contract worker can select a specific subcontract and subcontract line. 

When the time submitted by contract workers is approved, the project cost is recorded using the unit cost rate setup for that contract worker resource in the **Role prices** section of the purchase price list on the subcontract.
## Costing for subcontracted expenses on projects
When entering expenses incurred on projects, you will be able to select a subcontract and subcontract line on the expense entry. 

When this expense entry is submitted and approved, the expense cost is recorded on the project based on the unit cost setup for that transaction category in the **Category prices** section of the purchase price list on the subcontract.
## Costing for subcontracted materials on projects
When entering material usage on projects, you will be able to select a subcontract and subcontract line on the material usage log. When this material usage log is submitted and approved, the material cost is recorded on the project based on the unit cost setup for that product in the **price list items** section of subcontract price list.

Material usage can also be recorded for **write – in** products on projects and this type of material usage can also be linked to a Subcontract and Subcontract line. When recording material usage for write in products, user will have to enter the per unit cost of the write in product. 

  
	

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
