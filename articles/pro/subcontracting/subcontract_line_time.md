---
title: Subcontract lines for Time
description: This topic provides information that will help you record Subcontract lines for Time and how to use the various fields to record the purchase of time from vendors.
author: rumant
ms.date: 08/02/2021
ms.topic: article
ms.reviewer: kfend 
ms.author: rumant
---

# Subcontract lines for Time

[!include [banner](../../includes/dataverse-preview.md)]

_**Applies To:** Lite deployment - deal to proforma invoicing_

A subcontract in Project Operations can have Subcontract line for Time. Subcontract lines for Time allow a project manager to buy vendor resources time that they can, then, use to staff project tasks and resource requirements.

To create a subcontract line for Time in Project Operations, follow these steps:

- Open a Subcontract and navigate to Subcontract Lines tab.
- On the Subcontract Line tan select + New to create a new Subcontract Line
- On the Quick Create for Subcontract Line, make sure to select Transaction Class as &#39;Time&#39;, fill in the required fields and save the subcontract line.

The following table provides information about the fields on the Subcontract line details page and the quick create page as they are relevant for purchasing Subcontractor Time.

| **Field** | **Location** | **Relevance, purpose, and guidance** | **Downstream impact** |
| --- | --- | --- | --- |
| Name | Quick Create page and General tab of the Subcontract line details page | Name of the subcontract line to help with identification | This will be shown as the first column in all look ups based on Subcontract lines |
| Description | Quick Create page and General tab of the Subcontract line details page | Description of services that are being ordered/purchased on the Subcontract line | 
| Line Type | Quick Create page and General tab of the Subcontract line details page | Defaulted to &#39;Quantity-based&#39;* | |
| Billing Method | Quick Create page and General tab of the Subcontract line details page | This is an option set that represents the two main contracting models supported by Project Operations:<br> -  **Fixed Price** <br> -  **Time and Material** | Based on the billing method of the referenced subcontract line, a milestone – based invoice schedule is made available for Fixed Price billing method. |
| Transaction Class | Quick Create page and General tab of the Subcontract line details page | Defaulted to Time. | This indicates that the subcontract line is being used to record a purchase of subcontractor time |
| Role | Quick Create page and General tab of the Subcontract line details page | Role of the subcontract resources whose time is being purchased. | Role performed by the subcontract resources determines the cost of the purchase |
| Requested Start | Quick Create page and General tab of the Subcontract line details page | Date when the subcontractor resources are required to start working. | Requested start is used to pick a project price list from the project price lists attached to the subcontract. Cost of the role on the subcontract line is then defaulted from that price list |
| Requested end | Quick Create page and General tab of the Subcontract line details page | Date when the subcontractor resources&#39; assignment ends | This will be used to show warnings when a project manager is drawing from this capacity for resource requirements occurring after this date. |
| Quantity Ordered | Quick Create page and General tab of the Subcontract line details page | Number of hours of the Role being purchased from the vendor | This will be used to show warnings when a project manager is over-drawing from this capacity for resource requirements |
| Unit Group | Quick Create page and General tab of the Subcontract line details page | Defaulted and locked to the &#39;Time&#39; unit group | |
| Unit | Quick Create page and General tab of the Subcontract line details page | Defaulted to the base unit of &#39;Hour&#39; from the &#39;Time&#39; unit group.User may change this to buy in any unit of the Time unit group like Day or Week etc. | The combination of Role and Unit will be used to default or compute the unit price for the Subcontract line. |
| Unit Price | Quick Create page and General tab of the Subcontract line details page | Unit price is defaulted using the combination of Role and Unit from the project price list applicable for the Requested start date of the Subcontract line | When the applicable project price list has the price setup in a different unit than the unit on the subcontract line, the system uses the unit conversion to compute the per unit price. |
| Subtotal | Quick Create page and General tab of the Subcontract line details page | Read only field that is automatically computed as Quantity* Unit price if both Quantity and Unit price values are entered. If either quantity or unit price or both are left empty, then this field is available for entering a value. | |
| Sales Tax | Quick Create page and General tab of the Subcontract line details page | Editable field that is available for the user to enter a value. | |
| Total Amount | Quick Create page and General tab of the Subcontract line details page | This is a calculated field that is denotes the total amount of the subcontract line after including taxes. Calculated as Subtotal +Tax | |

*See Subcontracting in Project Operations - Early Access Scope

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
