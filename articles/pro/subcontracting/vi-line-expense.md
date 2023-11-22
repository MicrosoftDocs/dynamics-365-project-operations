---
title: Vendor invoice lines for expense categories
description: This article explains how to record vendor invoice lines for expense categories.
author: rumant
ms.date: 03/25/2022
ms.topic: hot-to
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak
ms.author: rumant
---

# Vendor invoice lines for expense categories

[!INCLUDE[banner](../../includes/banner.md)]

_**Applies To:** Lite deployment - deal to proforma invoicing_

A vendor invoice in Microsoft Dynamics 365 Project Operations can have vendor invoice lines for expense categories. Project managers can use vendor invoice lines for expense categories to record the costs of services that are procured as expense categories.

Vendor invoice lines for expense categories might or might not reference a subcontract line for expense categories. If a vendor invoice line for expense categories references a subcontract, project managers will be able to match and verify the expenses that are being invoiced by the vendor invoice line against expenses that are recorded on these expense categories and approved by project managers on the project.

The following table provides information about the fields on vendor invoice lines for expense categories.

| Field | Description | Functional impact |
| --- | --- | --- |
| Name | The name of the vendor invoice line, to help with identification. | This name will be shown as the first column in all lookups that are based on vendor invoice lines. |
| Description | A brief description of the services that are being invoiced by the vendor on the vendor invoice line. | None |
| Subcontract | The subcontract that the services were originally ordered on. | When a subcontract is selected for the vendor invoice, all lines on the vendor invoice will inherit that selection. A vendor invoice can't have vendor invoice lines that reference different subcontracts. |
| Subcontract line | The subcontract line that the services were ordered on. The list of subcontract lines that can be selected is limited to the lines on the selected subcontract. | When a subcontract line is selected on a vendor invoice line for expense categories, default values for the **Project**, **Task**, and **Transaction category** fields are entered from the corresponding fields on the subcontract line. If the selected subcontract line has values in the **Project**, **Project task**, and **Transaction category** fields, the values of the corresponding fields on the vendor invoice line can't differ from those values. |
| Transaction date | The date when the cost actual of the vendor invoice line will be recorded on the project. |None |
| Transaction class | Select **Expense** to record a vendor invoice for an expense category. | The value **Expense** indicates that the vendor invoice line is being used to record the invoice amount for services that were procured as expense categories. |
| Project | The name of the project that the services that are being invoiced were used on. | This field is required and can't be left blank. |
| Task | The name of the project task that the services that are being invoiced were used on. This field is available only if a project is selected. Selection of a project task is optional. | If this field is left blank, the project manager can match the vendor invoice line to expenses that are recorded on any task of the project. If the vendor invoice line doesn't reference a subcontract line, and this field is left blank, the cost actual that is created by the vendor invoice line won't be linked to any unbilled sales actuals. In this case, if task-based billing is set up, the costs might not be able to be invoiced to the end customer. |
| Transaction category | The transaction category that is being invoiced. A corresponding expense category must be created for the selected transaction category. | The combination of **Transaction category** and **Unit** values will be used as the default or computed value for the **Unit price** field on the vendor invoice line. |
| Quantity | Enter the quantity that is being invoiced by the vendor on the invoice line. |None|
| Unit group | A default value is entered based on the unit group of the selected transaction category. | None |
| Unit | The default value is the base unit of the unit group that is selected. You can change this value to buy in any unit of the unit group. | The combination of **Transaction category** and **Unit** values will be used as the default or computed value for the **Unit price** field on the vendor invoice line. |
| Unit price | The default unit price uses the combination of **Transaction category** and **Unit** values from the project price list that is applicable to the transaction date of the vendor invoice line. | If the price for the applicable project price list is set up in a unit that differs from the unit on the vendor invoice line, the system uses the unit conversion to calculate the per-unit price. |
| Subtotal | This read-only field is calculated as *Quantity* &times; *Unit price*, if values are entered in both the **Quantity** field and the **Unit price** field. If one or both those fields are blank, you can enter a value in this field.| None |
| Sales tax | Enter the sales tax amount. | None |
| Total amount | The total amount of the vendor invoice line, including taxes. This field is calculated as *Subtotal* + *Sales tax*. | None |

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
