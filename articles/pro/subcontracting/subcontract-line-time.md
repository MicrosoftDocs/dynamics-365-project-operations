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

| **Field** | **Description** |
| --- | --- |
| Name | The name of the subcontract line. |
| Description | A brief description of services that are being purchased on the subcontract line. | 
| Line Type | This field is a default value.  |
| Billing Method | Select the billing method. Based on the billing method of the referenced subcontract line, a milestone-based invoice schedule is made available for Fixed Price billing method. |
| Transaction Class | This field is a default value, which indicates that the subcontract line is being used to record a purchase of subcontractor time. |
| Role | The role of the subcontract resources whose time is being purchased. The role assigned to the subcontract resources determines the cost of the purchase. |
| Requested Start | The date when the subcontractor resources are required to start working. The requested start is used to pick a project price list from the project price lists attached to the subcontract. The cost of the role on the subcontract line then defaults from that price list. |
| Requested end | The date when the subcontractor resources' assignment ends. This date is used to show warnings when a Project Manager is drawing from this capacity for resource requirements occurring after this date. |
| Quantity Ordered | The number of Role hours being purchased from the vendor. This value is used to show warnings when a Project Manager is over-drawing from this capacity for resource requirements. |
| Unit Group | This field value defaults to the Time unit group and can't be changed.  |
| Unit | This field defaults to the base unit of hours from the Time unit group. You can change this value to buy any unit of the Time unit group, such as day or week. The combination of Role and Unit is used to default or calculate the unit price for the subcontract line. |
| Unit Price | The unit price defaults from the combination of Role and Unit from the project price list that is applicable for the requested start date of the subcontract line. When the applicable project price list has the price setup in a different unit than the unit on the subcontract line, the system uses the unit conversion to calculate the per unit price. |
| Subtotal | This is a read-only field that is automatically calculated as **Quantity x Unit price** if both the quantity and unit price values are entered. If either quantity, unit price, or both are blank, you can enter a value in the field. |
| Sales Tax |  Enter the sales tax amount. |
| Total Amount | The total amount of the subcontract line after taxes are included. |


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
