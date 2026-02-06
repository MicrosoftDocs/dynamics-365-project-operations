---
title: Subcontract lines for time
description: Learn how to create subcontract lines for time in Dynamics 365 Project Operations. Follow step-by-step instructions to record vendor resource time purchases.
author: rumant
ms.date: 02/04/2026
ms.topic: how-to
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak
ms.author: rumant
---

# Subcontract lines for time

[!INCLUDE[banner](../../includes/banner.md)]

_**Applies To:** Project Operations Integrated with ERP, Project Operations Core_

A subcontract in Dynamics 365 Project Operations can have a subcontract line for time. Subcontract lines for time allow a Project Manager to buy vendor resource time to staff project tasks and resource requirements.

To create a subcontract line for time in Project Operations, complete the following steps.

1. In the navigation pane, select **Subcontracts** and open a subcontract.
1. On the **Subcontract Lines** tab, select **New** to create a new subcontract line.
1. On the **Quick Create** page, in the **Transaction Class** field, select **Time**.
1. Enter the remaining field information and then select **Save**.

  The following table provides information about the fields on the **Subcontract line** page and the **Quick Create** page.

| **Field** | **Description** | **Functional impact** |
| --- | --- | --- |
| Name | Name of the subcontract line to help with identification. | This name appears as the first column in all lookups based on subcontract lines. |
| Description | A brief description of services that you're purchasing on the subcontract line. |None |
| Line Type |  This field has a default value of **Quantity-based**.| None |
| Billing Method | This is an option set that represents the two main contracting models supported by Project Operations: **Fixed Price** and **Time and Material**. | Based on the billing method you select, a milestone-based invoice schedule is available for subcontract lines with the Fixed Price billing method. |
| Transaction Class | The default value is **Time**. | This value indicates that the subcontract line records a purchase of subcontractor time. |
| Role | Select the role of the subcontract resources whose time you're purchasing. | The role that the subcontract resources perform determines the cost of the purchase. |
| Requested Start | Enter the date when the subcontractor resources start working. | This date picks a project price list from the project price lists attached to the subcontract. The cost of the role on the subcontract line comes from that price list. |
| Requested End | Enter the date when the subcontractor resource's assignment ends. | This date shows warnings when a project manager is drawing from the capacity for resource requirements occurring after this date. |
| Quantity Ordered | Enter the number of hours of the role being purchased from the vendor. | This value shows warnings when a project manager is over-drawing from this capacity for resource requirements. |
| Unit Group | The default value is **Time unit group**, which you can't change. | None|
| Unit | The default for this field is the base unit of hours from the **Time unit group**. You can change this value to buy any unit of the **Time unit group**, such as day or week. | The combination of **Role** and **Unit** is the default or computed unit price for the subcontract line. |
| Unit Price | The default unit price uses the combination of **Role** and **Unit** from the project price list applicable for the **Requested Start** date of the subcontract line. | When the applicable project price list has the price set up in a different unit than the unit on the subcontract line, the system uses the unit conversion to calculate the per unit price. |
| Subtotal |  This is a read-only field that is calculated as Quantity x Unit price, if both the quantity and unit price values are entered. If either quantity, unit price, or both are blank, you can enter a value in the field. | None|
| Sales Tax |  Enter the sales tax amount. |None |
| Total Amount | The total amount of the subcontract line including taxes. This field is calculated as Subtotal + Sales tax.|None |

> [!IMPORTANT]
> **Fixed Price** subcontracts currently don't support _resource/non-stocked based scenarios_ in Project Operations.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
