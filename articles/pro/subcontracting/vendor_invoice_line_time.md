---
title: Vendor Invoice Lines for Time 
description: This topic explains how to record vendor invoice lines for time costs that subcontractors put in.
author: rumant
ms.date: 03/15/2022
ms.topic: article
ms.reviewer: tonyafehr 
ms.author: rumant
---

# Vendor Invoice Lines for Time  

[!include [banner](../../includes/dataverse-preview.md)]

_**Applies To:** Lite deployment - deal to proforma invoicing_

A vendor invoice in Dynamics 365 Project Operations can have a vendor invoice lines for time. Vendor Invoice lines for time allow a Project Manager to record the costs of subcontractor time on projects.

Vendor Invoice lines for time may or may not reference a subcontract line for time. When a vendor invoice line for time references a subcontract, Project managers will be able to match and verify the time being invoiced by the vendor invoice line against time recorded by subcontractors and approved by project manager on the project.

The following table provides information about the fields on the  **Vendor Invoice line**  for time.

| **Field** | **Description** | **Functional impact** |
| --- | --- | --- |
| Name | Name of the vendor invoice line to help with identification. | This will be shown as the first column in all lookups based on vendor invoice lines. |
| Description | A brief description of services that are being invoiced by the vendor on the vendor invoice line. | None |
| Subcontract | The subcontract on which the services were originally ordered | When the vendor invoice has a subcontract selected, all lines on the vendor invoice will also inherit this selection. A vendor invoice cannot have vendor invoice lines that reference different subcontracts. |
| Subcontract Line | The subcontract line on which the services were ordered.The list of subcontract lines that can be selected is limited to the lines on the subcontract selected | When a subcontract line is selected on a vendor invoice line for time, the fields Project, Role and Bookable Resource are defaulted from the corresponding values on the subcontract line. When the selected subcontract line has values in the Project, Role and Bookable fields, then the values of these fields on the vendor invoice line are not allowed to be different than those on the selected subcontract line. |
| Transaction Date | Date on which the cost actual of this vendor invoice line will be recorded on the project | |
| Transaction Class | The default value is  **Time**. | This indicates that the vendor invoice line is being used to record invoice amount of subcontractor time. |
| Project | Name of the project on which these services being invoiced were used | Project is a required field and cannot be left empty. |
| Task | Name of the project task on which these services being invoiced were used. Project task field becomes available only when a project is selected. Selecting a project task is optional. | When left empty, the project manager can match this vendor invoice line to time recorded by subcontractor resources on any task of the project. If the vendor invoice line does not reference a subcontract line, leaving the project task field empty will result in the cost actual created by vendor invoice line to not be linked to any unbilled sales actuals. When task-based billing is setup, this could mean that these costs cannot be invoiced to the end customer as well. |
| Role | Role of the subcontract resources whose time is being invoiced. | Role played by the subcontract resources whose time is invoiced on this vendor invoice. |
| Bookable Resource | Name of the subcontractor whose time is being invoiced. Selecting a bookable resource is optional. | When left empty, the project manager can match this vendor invoice line to time recorded by any resource that belongs to the vendor on this vendor invoice line. |
| Quantity | Enter the number of hours of time that are being invoiced by the vendor on this invoice line. | |
| Unit Group | The default value is  **Time unit group** , which can&#39;t be changed. | None |
| Unit | The default for this field is the base unit of hours from the  **Time unit group**. You can change this value to buy any unit of the  **Time unit group** , such as day or week. | The combination of  **Role**  and  **Unit**  will be used as the default or computed for the unit price for the vendor invoice line. |
| Unit Price | The default unit price uses the combination of  **Role**  and  **Unit**  from the project price list applicable for the  **Transaction date**  of the vendor invoice line. | When the applicable project price list has the price set up in a different unit than the unit on the vendor invoice line, the system uses the unit conversion to calculate the per unit price. |
| Subtotal | This is a read-only field that is calculated as Quantity x Unit price, if both the quantity and unit price values are entered. If either quantity, unit price, or both are blank, you can enter a value in the field. | None |
| Sales Tax | Enter the sales tax amount. | None |
| Total Amount | The total amount of the vendor invoice line including taxes. This field is calculated as Subtotal + Sales tax. | None |

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
