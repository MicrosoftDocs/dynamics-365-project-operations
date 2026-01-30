---
title: Project opportunity lines
description: Learn about project opportunity lines in Dynamics 365 Project Operations. Understand their fields, usage, and downstream impacts to streamline your project-based opportunities.
author: rumant
ms.date: 01/30/2026
ms.topic: concept-article
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak
ms.author: rumant
---

# Project opportunity lines

[!INCLUDE[banner](../../includes/banner.md)]

_**Applies To:** Project Operations Core_

Project opportunity lines are only available in project-based opportunities. Set the **Type** field on the project-based opportunity record to **Work-based**.

Project opportunity lines are the line items that you deliver to the customer by using a project. However, you can't tie a project to a project-based opportunity line. You can tie projects to line items from the **Quote** stage and forward because typically the opportunity is at an early stage in the lifecycle of a deal. You use the opportunity phase to identify the discrete delivery components for the customer. You can push the decisions about the actual number of projects used to deliver these components until you know more about the work itself.

The following table describes the fields on a project opportunity line:

| **Field** | **Location** | **Description** | **Downstream impact** |
| --- | --- | --- | --- |
| Product Type | General tab (hidden) | Select one of the following options:</br>- Project-based service (available only when Dynamics 365 Project Operations is installed)</br>- Product (available only when Project Operations and Dynamics 365 Sales are installed) | Set this field to **Project-based service** when you create a project-based opportunity line from the project-based lines grid on the Opportunity. <br> If you change or override this value, the project functionality isn't enabled on your project-based line items. |
| Opportunity | General tab | This read-only field references the parent Opportunity record to which this line item belongs. | There is no downstream impact from this field. |
| Name | General tab | Use this editable text field to give a short identity to the line item. | This value is carried over to the quote line when you create a quote from this opportunity. |
| Customer Budget | General tab | Use this editable currency field to track the amount that the customer is willing to spend for this line item. | This value is carried over to the corresponding field on the quote line when you create a quote from this opportunity. |
| Billing Method | General tab | This editable field has the following values:</br>- Time and Material</br>- Fixed Price | This value is carried over to the corresponding field on the quote line when you create a quote from this opportunity. After you create the quote line, the field is locked and can't be changed. Assign this field value as accurately as possible. If you need to change the value of this field on the quote line, delete and re-create the quote line. |

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
