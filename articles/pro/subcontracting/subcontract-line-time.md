---
title: Subcontract lines for time
description: This article explains how to record subcontract lines for time and record the purchase of time from vendors.
author: rumant
ms.date: 04/08/2024
ms.topic: how-to
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak
ms.author: rumant
---

# Subcontract lines for time

[!INCLUDE[banner](../../includes/banner.md)]

_**Applies To:** Project Operations Integrated with ERP, Core deployment - deal to proforma invoicing_

A subcontract in Dynamics 365 Project Operations can have a subcontract line for time. Subcontract lines for time allow a Project Manager to buy vendor resource time to staff project tasks and resource requirements.

To create a subcontract line for time in Project Operations, complete the following steps.

1. In the navigation pane, select **Subcontracts** and open a subcontract.
2. On the **Subcontract Lines** tab, select **New** to create a new subcontract line.
3. On the **Quick Create** page, in the **Transaction Class** field, select **Time**.
4. Enter the remaining field information and then select **Save**.

  The following table provides information about the fields on the **Subcontract line** page and the **Quick Create** page.

| **Field** | **Description** | **Functional impact** |
| --- | --- | --- |
| Name | Name of the subcontract line to help with identification. | This will be shown as the first column in all lookups based on subcontract lines. |
| Description | A brief description of services that are being purchased on the subcontract line. |None |
| Line Type | 	This field has a default value of **Quantity-based**.| None |
| Billing Method | This is an option set that represents the two main contracting models supported by Project Operations: **Fixed Price** and **Time and Material**. | Based on the billing method selected, a milestone-based invoice schedule is made available for subcontract lines with the Fixed Price billing method. |
| Transaction Class | The default value is **Time**. | This indicates that the subcontract line is being used to record a purchase of subcontractor time. |
| Role | Select the role of the subcontract resources whose time is being purchased. | Role performed by the subcontract resources determines the cost of the purchase. |
| Requested Start | Enter the date when the subcontractor resources are required to start working. | This is used to pick a project price list from the project price lists attached to the subcontract. The cost of the role on the subcontract line comes from that price list. |
| Requested End | Enter the date when the subcontractor resource's assignment ends. | This will be used to show warnings when a project manager is drawing from the capacity for resource requirements occurring after this date. |
| Quantity Ordered | Enter the number of hours of the role being purchased from the vendor. | This will be used to show warnings when a project manager is over-drawing from this capacity for resource requirements. |
| Unit Group | The default value is **Time unit group**, which can't be changed. | None|
| Unit | The default for this field is the base unit of hours from the **Time unit group**. You can change this value to buy any unit of the **Time unit group**, such as day or week. | The combination of **Role** and **Unit** will be used as the default or computed for the unit price for the subcontract line. |
| Unit Price | The default unit price uses the combination of **Role** and **Unit** from the project price list applicable for the **Requested Start** date of the subcontract line. | When the applicable project price list has the price set up in a different unit than the unit on the subcontract line, the system uses the unit conversion to calculate the per unit price. |
| Subtotal | 	This is a read-only field that is calculated as Quantity x Unit price, if both the quantity and unit price values are entered. If either quantity, unit price, or both are blank, you can enter a value in the field. | None|
| Sales Tax | 	Enter the sales tax amount. |None |
| Total Amount | The total amount of the subcontract line including taxes. This field is calculated as Subtotal + Sales tax.|None |



> [!IMPORTANT]
> **Fixed Price** subcontracts are currently not supported for _resource/non-stocked based scenarios_ in Project Operations. 

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
