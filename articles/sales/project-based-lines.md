---
title: Project-based opportunity lines
description: This article provides information about working with project-based opportunity lines.
author: poojafandan
ms.author: poojafandan
ms.date: 02/25/2026
ms.topic: concept-article
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak

---

# Project-based opportunity lines

_**Applies To:** Project Operations Integrated with ERP_

Project-based opportunity lines are only available in project-based opportunities. Set the **Type** field value to **Work-based** for project-based opportunity records.

Project-based opportunity lines are the line items that you deliver to the customer by using a project. However, you can't tie a project to a project-based opportunity line. You can tie projects to line items from the **Quote** stage onwards, because an opportunity typically occurs in an early stage of a deal. The determination of how many projects you use to deliver the work for the customer is a decision that you make later in the sales phase. Use the opportunity phase to identify the discrete delivery components for the customer. You can push the decisions surrounding the actual number of projects used to deliver these components until you know more about the work itself.

The following table describes the fields on a project-based opportunity line:

| **Field** | **Location** | **Description** | **Downstream impact** |
| --- | --- | --- | --- |
| Product Type | General tab (hidden) | This field is an option set. If you have Dynamics 365 Operations installed, one of the available options is **Project-based service**.  | Set this field to **Project-based service** when you create the project-based opportunity line from the project-based lines grid on the Opportunity. <br> If you change or override this value, you don't enable the project functionality on your project-based line items. |
| Opportunity | General tab | This field is read-only and references the parent Opportunity record to which this line item belongs. | This field has no downstream impact. |
| Name | General tab | This editable text field can give a short identity to this line item | This value is carried over to the quote line when you create a quote from this opportunity |
| Customer Budget | General tab | This editable currency field can track the amount that the customer is willing to spend for this line item. | This value is carried over to the corresponding field on the quote line when you create a quote from this opportunity |
| Billing Method | General tab | This editable field has the following values:</br>- Time and Material</br>- Fixed Price | This value is carried over to the corresponding field on the quote line when you create a quote from this opportunity. After you create the quote line, the field is locked and can't be changed. Assign this field value as accurately as possible. If you need to change the value of this field on the quote line, delete and re-create the quote line. |

[!INCLUDE[footer-include](../includes/footer-banner.md)]
