---
title: Project opportunity lines 
description: This article provides information about project-based opportunity lines. (Pro)
author: rumant
ms.date: 12/03/2022
ms.topic: article
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak
ms.author: rumant
---

# Project opportunity lines 

[!INCLUDE[banner](../../includes/banner.md)]

_**Applies To:** Lite deployment - deal to proforma invoicing_

Project opportunity lines are only available in project-based opportunities. Project-based opportunity records have the **Type** field value set to **Work-based**.

Project opportunity lines are the line items that will be delivered to the customer using a project. However, a project can't be tied to a project-based opportunity line. Projects can be tied to line items from the **Quote** stage and forward because typically the opportunity is at an early stage in the lifecycle of a deal. The determination of how many projects will be used to deliver the work for the customer is a decision that is made later in the sales phase. You can use the opportunity phase to identify the discrete delivery components for the customer. The decisions surrounding the actual number of projects used to deliver these components can be pushed out until more information is known about the work itself.

Below are the fields on a project opportunity line:

| **Field** | **Location** | **Description** | **Downstream impact** |
| --- | --- | --- | --- |
| Product Type | General tab (hidden) | You can select one of the following options:</br>- Project-based service (available only when Dynamics 365 Project Operations is installed)</br>- Product (available only when Project Operations and Dynamics 365 Sales are installed) | The value of this field is set to **Project-based service** when you create a project-based opportunity line from the project-based lines grid on the Opportunity. <br> If you change or override this value, the project functionality won't be enabled on your project-based line items. |
| Opportunity | General tab | This field is read-only and references parent Opportunity record to which this line item belongs. | There is no downstream impact from this field. |
| Name | General tab | This editable text field can be used to give a short identity to the line item. | This value is carried over to the quote line when you create a quote from this opportunity. |
| Customer Budget | General tab | This editable currency field can be used to track the amount that the customer is willing to spend for this line item. | This value is carried over to the corresponding field on the quote line when you create a quote from this opportunity. |
| Billing Method | General tab | This editable field has the following values:</br>- Time and Material</br>- Fixed Price | This value is carried over to the corresponding field on the quote line when you create a quote from this opportunity. After the quote line is created, the field is locked and can't be changed. Assign this field value as accurately as possible. If you need to change the value of this field on the quote line, delete and re-create the quote line. |


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
