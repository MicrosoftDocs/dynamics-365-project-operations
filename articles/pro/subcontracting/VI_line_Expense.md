---
title:  Vendor invoice lines for expense categories
description: This topic explains how to record vendor invoice lines for expense categories.
author: rumant
ms.date: 08/06/2021
ms.topic: article
ms.reviewer: kfend 
ms.author: rumant
---

#  Vendor invoice lines for expense categories

[!include [banner](../../includes/dataverse-preview.md)]

_**Applies To:** Lite deployment - deal to proforma invoicing_

A vendor invoice in Dynamics 365 Project Operations can have a vendor invoice lines for expense categories. Vendor Invoice lines for expense categories allow a Project Manager to record the costs of services procured as expense categories.

Vendor Invoice lines for expense categories may or may not reference a subcontract line for expense categories. When a vendor invoice line for expense categories references a subcontract, Project managers will be able to match and verify the expenses being invoiced by the vendor invoice line against expenses recorded on these expense categories and approved by project manager on the project.

The following table provides information about the fields on the  **Vendor Invoice line**  for expense categories.

| **Field** | **Description** | **Functional impact** |
| Name | Name of the vendor invoice line to help with identification. | This will be shown as the first column in all lookups based on vendor invoice lines. |
| --- | --- | --- |
| Description | A brief description of services that are being invoiced by the vendor on the vendor invoice line. | None |
| Subcontract | The subcontract on which the services were originally ordered | When the vendor invoice has a subcontract selected, all lines on the vendor invoice will also inherit this selection. A vendor invoice cannot have vendor invoice lines that reference different subcontracts. |
| Subcontract Line | The subcontract line on which the services were ordered.The list of subcontract lines that can be selected is limited to the lines on the subcontract selected | When a subcontract line is selected on a vendor invoice line for time, the fields Project, project task and Transaction category are defaulted from the corresponding values on the subcontract line. When the selected subcontract line has values in the Project, Project Task and Transaction Category fields, then the values of these fields on the vendor invoice line are not allowed to be different than those on the selected subcontract line. |
| Transaction Date | Date on which the cost actual of this vendor invoice line will be recorded on the project | |
| Transaction Class | Select **Expense** to record a vendor invoice for an Expense Category | This indicates that the vendor invoice line is being used to record invoice amount for services procured as Expense categories. |
| Project | Name of the project on which these services being invoiced were used | Project is a required field and cannot be left empty. |
| Task | Name of the project task on which these services being invoiced were used. Project task field becomes available only when a project is selected. Selecting a project task is optional. | When left empty, the project manager can match this vendor invoice line to expenses recorded on any task of the project. If the vendor invoice line does not reference a subcontract line, leaving the project task field empty will result in the cost actual created by vendor invoice line to not be linked to any unbilled sales actuals. When task-based billing is setup, this could mean that these costs cannot be invoiced to the end customer as well. |
| Transaction Category | Transaction category that is being invoiced. The transaction category selected must have a corresponding Expense category created | The combination of  **Transaction Category**  and  **Unit**  will be used as the default or computed for the unit price for the vendor invoice line. |
| Quantity | Enter the quantity being invoiced by the vendor on this invoice line. | |
| Unit Group | Defaulted based on the unit group of the selected Transaction category | None |
| Unit | The default for this field is the base unit of **unit group** selected. You can change this value to buy any unit of the  **unit group**. | The combination of  **Transaction Category**  and  **Unit**  will be used as the default or computed for the unit price for the vendor invoice line. |
| Unit Price | The default unit price uses the combination of  **Transaction Category** and  **Unit**  from the project price list applicable for the  **Transaction date**  of the vendor invoice line. | When the applicable project price list has the price set up in a different unit than the unit on the vendor invoice line, the system uses the unit conversion to calculate the per unit price. |
| Subtotal | This is a read-only field that is calculated as Quantity x Unit price, if both the quantity and unit price values are entered. If either quantity, unit price, or both are blank, you can enter a value in the field. | None |
| Sales Tax | Enter the sales tax amount. | None |
| Total Amount | The total amount of the vendor invoice line including taxes. This field is calculated as Subtotal + Sales tax. | None |

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
