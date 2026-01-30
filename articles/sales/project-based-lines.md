---
title: Project-based opportunity lines
description: This article provides information about working with project-based opportunity lines.
author: poojafandan
ms.author: poojafandan
ms.date: 06/10/2024
ms.topic: concept-article
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak

---

# Project-based opportunity lines

_**Applies To:** Project Operations Integrated with ERP_


Project-based opportunity lines are only available in project-based opportunities. Project-based opportunity records have the **Type** field value set to **Work-based**.

Project-based opportunity lines are the line items that will be delivered to the customer using a project. However, a project can't be tied to a project-based opportunity line. Projects can be tied to line items from the **Quote** stage onwards because typically the opportunity occurs in an early stage of a deal. The determination of how many projects will be used to deliver the work for the customer is a decision that is made later in the sales phase. Use the opportunity phase to identify the discrete delivery components for the customer. The decisions surrounding the actual number of projects used to deliver these components can be pushed out until more information is known about the work itself.

Below are the fields on a project-based opportunity line:

| **Field** | **Location** | **Description** | **Downstream impact** |
| --- | --- | --- | --- |
| Product Type | General tab (hidden) | This is an option set field. If you have Dynamics 365 Operations installed, one the available options is, **Project-based service**.  | The value of this field is set to **Project-based service** when you create the project-based opportunity line from the project-based lines grid on the Opportunity. <br> If you change or override this value, the project functionality won't be enabled on your project-based line items. |
| Opportunity | General tab | This field is read-only and references the parent Opportunity record to which this line item belongs. | There is no downstream impact of this field. |
| Name | General tab | This is an editable text field that can be used to give a short identity to this line item | This value is carried over to the quote line when you create a quote from this opportunity |
| Customer Budget | General tab | This editable currency field can be used to track the amount that the customer is willing to spend for this line item. | This value is carried over to the corresponding field on the quote line when you create a quote from this opportunity |
| Billing Method | General tab | This editable field has the following values:</br>- Time and Material</br>- Fixed Price | This value is carried over to the corresponding field on the quote line when you create a quote from this opportunity. After the quote line is created, the field is locked and can't be changed. Assign this field value as accurately as possible. If you need to change the value of this field on the quote line, delete and re-create the quote line. |


[!INCLUDE[footer-include](../includes/footer-banner.md)]
