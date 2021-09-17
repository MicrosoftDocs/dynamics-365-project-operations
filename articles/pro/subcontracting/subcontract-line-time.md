---
title: Subcontract lines for time
description: This topic explains how to record subcontract lines for time and record the purchase of time from vendors.
author: rumant
ms.date: 08/05/2021
ms.topic: article
ms.reviewer: kfend 
ms.author: rumant
---

# Subcontract lines for time

[!include [banner](../../includes/dataverse-preview.md)]

_**Applies To:** Lite deployment - deal to proforma invoicing_

A subcontract in Dynamics 365 Project Operations can have a subcontract line for time. Subcontract lines for time allow a Project Manager to buy vendor resource time to staff project tasks and resource requirements.

To create a subcontract line for time in Project Operations, complete the following steps.

1. In the navigation pane, select **Subcontracts** and open a subcontract.
2. On the **Subcontract Lines** tab, select **New** to create a new subcontract line.
3. On the **Quick Create** page, in the **Transaction Class** field, select **Time**.
4. Enter the remaining field information and then select **Save**.

  The following table provides information about the fields on the **Subcontract line** page and the **Quick Create** page.

| **Field** | **Description** | **Downstream impact** |
| --- | --- | --- |
| Name | Name of the subcontract line to help with identification | This will be shown as the first column in all look ups based on Subcontract lines |
| Description | Description of services that are being ordered/purchased on the Subcontract line |None |
| Line Type | Defaulted to Quantity-based|None |
| Billing Method | This is an option set that represents the two main contracting models supported by Project Operations: </br>  **Fixed Price** </br>  **Time and Material** |Based on the billing method of the referenced subcontract line, a milestone – based invoice schedule is made available for Subcontract lines with Fixed Price billing method. |
| Transaction Class | Defaulted to Time. | This indicates that the subcontract line is being used to record a purchase of subcontractor time |
| Role | Role of the subcontract resources whose time is being purchased. | Role performed by the subcontract resources determines the cost of the purchase |
| Requested Start | Date when the subcontractor resources are required to start working. | Requested start is used to pick a project price list from the project price lists attached to the subcontract. Cost of the role on the subcontract line is then defaulted from that price list |
| Requested end | Date when the subcontractor resources&#39; assignment ends | This will be used to show warnings when a project manager is drawing from this capacity for resource requirements occurring after this date. |
| Quantity Ordered | Number of hours of the Role being purchased from the vendor | This will be used to show warnings when a project manager is over-drawing from this capacity for resource requirements |
| Unit Group | Defaulted and locked to the &#39;Time&#39; unit group | None|
| Unit | Defaulted to the base unit of &#39;Hour&#39; from the &#39;Time&#39; unit group.User may change this to buy in any unit of the Time unit group like Day or Week etc. | The combination of Role and Unit will be used to default or compute the unit price for the Subcontract line. |
| Unit Price | Unit price is defaulted using the combination of Role and Unit from the project price list applicable for the Requested start date of the Subcontract line | When the applicable project price list has the price setup in a different unit than the unit on the subcontract line, the system uses the unit conversion to compute the per unit price. |
| Subtotal | Read only field that is automatically computed as Quantity \* Unit price if both Quantity and Unit price values are entered. If either quantity or unit price or both are left empty, then this field is available for entering a value. | None|
| Sales Tax | Editable field that is available for the user to enter a value. |None |
| Total Amount | This is a calculated field that is denotes the total amount of the subcontract line after including taxes. Calculated as Subtotal +Tax |None |

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
