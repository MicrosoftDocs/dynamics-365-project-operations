---
title: Vendor invoice line milestones
description: This topic explains how to create vendor invoice line for milestones on a subcontract.
author: rumant
ms.date: 03/15/2022
ms.topic: article
ms.reviewer: tonyafehr 
ms.author: rumant
---

#  Vendor invoice line milestones

[!include [banner](../../includes/dataverse-preview.md)]

_**Applies To:** Lite deployment - deal to proforma invoicing_

A vendor invoice in Dynamics 365 Project Operations can have a vendor invoice lines for against milestones defined on the Subcontract line. Vendor Invoice lines for milestones allow a Project Manager to record the costs of services procured as milestone – based costs incurred on services or products procured for the project.

Vendor Invoice lines for milestones must always reference a subcontract line that has a Fixed Price Billing method. When a vendor invoice line for milestones references a subcontract line, Project managers will be able to match and verify the underlying costs of time, expense or materials that reference the same subcontract line towards the milestone being invoiced by the vendor.

The following table provides information about the fields on the  **Vendor Invoice line**  for milestone.

| **Field** | **Description** | **Functional impact** |
| --- | --- | --- |
| Name | Name of the vendor invoice line to help with identification. | This will be shown as the first column in all lookups based on vendor invoice lines. |
| Description | A brief description of services that are being invoiced by the vendor on the vendor invoice line. | None |
| Subcontract | The subcontract on which the services were originally ordered | When the vendor invoice has a subcontract selected, all lines on the vendor invoice will also inherit this selection. A vendor invoice cannot have vendor invoice lines that reference different subcontracts. |
| Subcontract Line | The subcontract line on which the services were ordered.The list of subcontract lines that can be selected is limited to the lines on the subcontract selected | When a subcontract line is selected on a vendor invoice line for milestone, the fields Role, Transaction category and Product-related fields are irrelevant and not available. Quantity, Unit and Unit group fields are also not relevant for Milestone based Vendor invoice lines. |
| Transaction Date | Date on which the cost actual of this vendor invoice line will be recorded on the project | None |
| Transaction Class | Select **Milestone** to record a vendor invoice for completed milestone that was defined on the Subcontract line | None |
| Milestone | Select the milestone defined on the related subcontract line that is marked as **Ready to Invoice** | Subcontract line milestones that are in status **Ready to invoice** can be selected on a vendor invoice line |
| Project | Name of the project on which these services being invoiced were used | Project is a required field and cannot be left empty. |
| Task | Name of the project task on which these services being invoiced were used. Project task field becomes available only when a project is selected. Selecting a project task is optional. | When left empty, the project manager can match this vendor invoice line to the class of transactions on the related subcontract line recorded on any task of the project. If the vendor invoice line does not reference a subcontract line, leaving the project task field empty will result in the cost actual created by vendor invoice line to not be linked to any unbilled sales actuals. When task-based billing is setup, this could mean that these costs cannot be invoiced to the end customer as well. |
| Milestone Amount | Enter the value of the milestone defined on the subcontract line that is ready to invoice. | None |
| Sales Tax | Enter the sales tax amount. | None |
| Total Amount | The total amount of the vendor invoice line including taxes. This field is calculated as Milestone amount + Sales tax. | None |

>[!Note]
>When a vendor invoice line that is referencing a subcontract line milestone is created, the subcontract milestone is moved to status **Vendor Invoice created**. When that vendor invoice is confirmed, the subcontract line milestone is moved to status &quot;Vendor invoice confirmed&quot;


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
