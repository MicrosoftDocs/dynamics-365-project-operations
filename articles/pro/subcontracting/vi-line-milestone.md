---
title: Vendor invoice lines for milestones
description: This article explains how to create vendor invoice lines for milestones on a subcontract.
author: rumant
ms.date: 12/15/2023
ms.topic: how-to
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak
ms.author: rumant
---

# Vendor invoice lines for milestones

[!INCLUDE[banner](../../includes/banner.md)]

_**Applies To:** Core deployment - deal to proforma invoicing_

A vendor invoice in Microsoft Dynamics 365 Project Operations can have vendor invoice lines for milestones that are defined on a subcontract line. Project managers can use vendor invoice lines for milestones to record the costs of services that are procured as milestone-based costs that are incurred on services or products that are procured for the project.

Vendor invoice lines for milestones must always reference a subcontract line that has a Fixed price billing method. When a vendor invoice line for milestones references a subcontract line, project managers will be able to match and verify the underlying costs of time, expenses, or materials that reference that subcontract line against the milestone that is being invoiced by the vendor.

The following table provides information about the fields on vendor invoice lines for milestones.

| Field | Description | Functional impact |
| --- | --- | --- |
| Name | The name of the vendor invoice line, to help with identification. | This name will be shown as the first column in all lookups that are based on vendor invoice lines. |
| Description | A brief description of services that are being invoiced by the vendor on the vendor invoice line. | None |
| Subcontract | The subcontract that the services were originally ordered on. | When a subcontract is selected for the vendor invoice, all lines on the vendor invoice will inherit that selection. A vendor invoice can't have vendor invoice lines that reference different subcontracts. |
| Subcontract line | The subcontract line that the services were ordered on. The list of subcontract lines that can be selected is limited to the lines on the selected subcontract. | When a subcontract line is selected on a vendor invoice line for milestones, the **Role** and **Transaction category** fields, and product-related fields, are irrelevant and unavailable. The **Quantity**, **Unit**, and **Unit group** fields also aren't relevant for milestone-based vendor invoice lines. |
| Transaction date | The date when the cost actual of the vendor invoice line will be recorded on the project. | None |
| Transaction class | Select **Milestone** to record a vendor invoice for a completed milestone that was defined on a subcontract line. | None |
| Milestone | Select the milestone that is defined on the related subcontract line that is marked as **Ready to Invoice**. | Subcontract line milestones that have a status of **Ready to invoice** can be selected on a vendor invoice line. |
| Project | The name of the project that the services that are being invoiced were used on. | This field is required and can't be left blank. |
| Task | The name of the project task that the services that are being invoiced were used on. This field is available only if a project is selected. Selection of a project task is optional. | If this field is left blank, the project manager can match the vendor invoice line to the class of transactions on the related subcontract line that is recorded on any task of the project. If the vendor invoice line doesn't reference a subcontract line, and this field is left blank, the cost actual that is created by the vendor invoice line won't be linked to any unbilled sales actuals. In this case, if task-based billing is set up, the costs might not be able to be invoiced to the end customer. |
| Milestone amount | Enter the value of the milestone that is defined on the subcontract line that is ready to be invoiced. | None |
| Sales tax | Enter the sales tax amount. | None |
| Total amount | The total amount of the vendor invoice line, including taxes. This field is calculated as *Milestone amount* + *Sales tax*. | None |

> [!NOTE]
> When a vendor invoice line that references a subcontract line milestone is created, the status of the subcontract milestone is updated to **Vendor invoice created**. Then, when that vendor invoice is confirmed, status of the subcontract line milestone is updated to **Vendor invoice confirmed**.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
