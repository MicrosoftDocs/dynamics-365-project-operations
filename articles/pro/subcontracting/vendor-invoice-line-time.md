---
title: Vendor invoice lines for time
description: Learn how to fix and manage vendor invoice lines for subcontractor time costs in Dynamics 365. Ensure accurate project billing and cost tracking.
author: rumant
ms.date: 02/04/2026
ms.topic: how-to
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak
ms.author: rumant
---

# Vendor invoice lines for time

[!INCLUDE[banner](../../includes/banner.md)]

_**Applies To:** Project Operations Core_

A vendor invoice in Microsoft Dynamics 365 Project Operations can have vendor invoice lines for time. Project managers can use vendor invoice lines for time to record the costs of subcontractor time on projects.

Vendor invoice lines for time might or might not reference a subcontract line for time. If a vendor invoice line for time references a subcontract, project managers can match and verify the time that the vendor invoice line invoices against time that subcontractors record and project managers approve on the project.

The following table provides information about the fields on vendor invoice lines for time.

| Field | Description | Functional impact |
| --- | --- | --- |
| Name | The name of the vendor invoice line, to help with identification. | This name appears as the first column in all lookups that are based on vendor invoice lines. |
| Description | A brief description of the services that the vendor is invoicing on the vendor invoice line. | None |
| Subcontract | The subcontract that the services were originally ordered on. | When you select a subcontract for the vendor invoice, all lines on the vendor invoice inherit that selection. A vendor invoice can't have vendor invoice lines that reference different subcontracts. |
| Subcontract line | The subcontract line that the services were ordered on. The list of subcontract lines that you can select is limited to the lines on the selected subcontract. | When you select a subcontract line on a vendor invoice line for time, default values for the **Project**, **Role**, and **Bookable resource** fields enter from the corresponding fields on the subcontract line. If the selected subcontract line has values in the **Project**, **Role**, and **Bookable** fields, the values of the corresponding fields on the vendor invoice line can't differ from those values. |
| Transaction date | The date when the cost actual of the vendor invoice line records on the project. | None |
| Transaction class | The default value is **Time**. | The value **Time** indicates that the vendor invoice line records the invoice amount of subcontractor time. |
| Project | The name of the project that the services that the vendor is invoicing were used on. | This field is required and can't be left blank. |
| Task | The name of the project task that the services that the vendor is invoicing were used on. This field is available only if a project is selected. Selection of a project task is optional. | If you leave this field blank, the project manager can match the vendor invoice line to time that subcontractor resources record on any task of the project. If the vendor invoice line doesn't reference a subcontract line, and this field is left blank, the cost actual that the vendor invoice line creates isn't linked to any unbilled sales actuals. In this case, if you set up task-based billing, the costs might not be able to be invoiced to the end customer. |
| Role | The role of the subcontract resources whose time is being invoiced. | This field specifies the role that the subcontract resources perform whose time is invoiced on the vendor invoice. |
| Bookable resource | The name of the subcontractor whose time is being invoiced. Selection of a bookable resource is optional. | If you leave this field blank, the project manager can match the vendor invoice line to time that any resource that belongs to the vendor on the vendor invoice line records. |
| Quantity | Enter the number of hours of time that the vendor is invoicing by the vendor on the invoice line. |None |
| Unit group | The default value is **Time unit group** and can't be changed. | None |
| Unit | The default value is the base unit of hours from the time unit group. You can change this value to buy in any unit of the time unit group, such as day or week. | The combination of **Role** and **Unit** values is used as the default or computed value for the **Unit price** field on the vendor invoice line. |
| Unit price | The default unit price uses the combination of **Role** and **Unit** values from the project price list that's applicable to the transaction date of the vendor invoice line. | If the price for the applicable project price list is set up in a unit that differs from the unit on the vendor invoice line, the system uses the unit conversion to calculate the per-unit price. |
| Subtotal | This read-only field is calculated as *Quantity* &times; *Unit price*, if you enter values in both the **Quantity** field and the **Unit price** field. If one or both those fields are blank, you can enter a value in this field. | None |
| Sales tax | Enter the sales tax amount. | None |
| Total amount | The total amount of the vendor invoice line, including taxes. This field is calculated as *Subtotal* + *Sales tax*. | None |

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
