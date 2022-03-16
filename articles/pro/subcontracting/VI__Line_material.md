---
title: Vendor Invoice lines for products
description: This topic explains how to record vendor invoice lines for products and use the various fields to record product purchases from vendors.
author: rumant
ms.date: 03/15/2022
ms.topic: article
ms.reviewer: tonyafehr 
ms.author: rumant
---

# Vendor Invoice lines for products

[!include [banner](../../includes/dataverse-preview.md)]

_**Applies To:** Lite deployment - deal to proforma invoicing_

A vendor invoice in Dynamics 365 Project Operations can have a vendor invoice lines for materials, also called as products. Vendor Invoice lines for material allow a Project Manager to record the costs of materials that were purchased on the project.

Vendor Invoice lines for material may or may not reference a subcontract line for material. When a vendor invoice line for material references a subcontract, Project managers will be able to match and verify the materials being invoiced by the vendor invoice line with the usage of purchased material recorded and approved by project manager.

The following table provides information about the fields on the  **Vendor Invoice line**  for material.

| **Field** | **Description** | **Functional impact** |
| --- | --- | --- |
| Name | Name of the vendor invoice line to help with identification. | This will be shown as the first column in all lookups based on vendor invoice lines. |
| Description | A brief description of the products that are being invoiced by the vendor on the vendor invoice line. | None |
| Subcontract | The subcontract on which the products were originally ordered | When the vendor invoice has a subcontract selected, all lines on the vendor invoice will also inherit this selection. A vendor invoice cannot have vendor invoice lines that reference different subcontracts. |
| Subcontract Line | The subcontract line on which the products were ordered.The list of subcontract lines that can be selected is limited to the lines on the subcontract selected | When a subcontract line is selected on a vendor invoice line for material, the fields Project, Project task and Product are defaulted from the corresponding values on the subcontract line. When the selected subcontract line has values in the Project, Task and Product fields, then the values of these fields on the vendor invoice line are not allowed to be different than those on the selected subcontract line. |
| Transaction Date | Date on which the cost actual of this vendor invoice line will be recorded on the project |
 |
| Transaction Class | When invoicing products, this field should be set to **Material**. | This indicates that the vendor invoice line is being used to record invoice amount ofor materials purchased. |
| Project | Name of the project on which these products being invoiced were used | Project is a required field and cannot be left empty. |
| Task | Name of the project task on which these products being invoiced were used. Project task field becomes available only when a project is selected. Selecting a project task is optional. | When left empty, the project manager can match this vendor invoice line to the purchased product used on any task of the project. If the vendor invoice line does not reference a subcontract line, leaving the project task field empty will result in the cost actual created by vendor invoice line to not be linked to any unbilled sales actuals. When task-based billing is setup, this could mean that these costs cannot be invoiced to the end customer as well. |
| Select product | Select whether the product being invoiced is an **existing** product from the catalog or if it is a **Write – In** product | Defaulted from the subcontract line when the subcontract line is selected. |
| Product | Select the product from the catalog. When the product is a Write-In product, type the name of the product | Product field is used to default purchase prices for existing products |
| Quantity | Enter the quantity of material being invoiced by the vendor on this invoice line. | None |
| Unit Group | Select the unit group of the unit in which the quantity being invoiced is expressed | None |
| Unit | The default for this field is the base unit of **unit group** selected. You can change this value to pay in any unit of the selected **unit group** | The combination of  **Product**  and  **Unit**  will be used as the default or computed for the unit price for the vendor invoice line. |
| Unit Price | The default unit price uses the combination of  **Product**  and  **Unit**  from the project price list applicable for the  **Transaction date** of the vendor invoice line. | None |
| Subtotal | This is a read-only field that is calculated as Quantity x Unit price, if both the quantity and unit price values are entered. If either quantity, unit price, or both are blank, you can enter a value in the field. | None |
| Sales Tax | Enter the sales tax amount. | None |
| Total Amount | The total amount of the vendor invoice line including taxes. This field is calculated as Subtotal + Sales tax. | None |

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
