---
title: Opportunity header/summary
description: This article provides information about project-based deals and the project-based opportunity lines.
author: rumant
ms.date: 10/01/2020
ms.topic: article
ms.reviewer: johnmichalak
ms.author: rumant
---

# Header details for project-based opportunities

_**Applies To:** Project Operations for resource/non-stocked based scenarios_


The Opportunity header, or summary, captures the overall information about a project-based deal that applies to all the lines on a project-based opportunity.

Project-based opportunities in Dynamics 365 Project Operations are extensions of opportunities in Dynamics 365 Sales. These extensions provide additional functionality that is specific to and required for project-based opportunities. These extensions can include new fields and ribbon actions available in project-based opportunities. You may find some fields, functionality, and defaulting logic that is available in Sales isn't available in Project Operations.

The following table includes the fields in a project-based opportunity that are either unique to Project Operations or have some important changes in behavior from the Opportunities in Sales.

| **Field** | **Location** | **Description** | **Downstream impact** |
| --- | --- | --- | --- |
| Type | General tab (hidden) | This option set field has the following options:</br>- Work-based (available only with Project Operations)</br>- Item-based (available only when Project Operations and Sales are installed)</br>- Service maintenance-based (available when Field Service is installed) | When you use Project Operations, this field value is automatically set to **Work-based** which classifies the Opportunity as project-based. An Opportunity should be project-based to enable all project-specific extensions and functionality in the downstream sales process for this deal. |
| Owning Company | General tab | This is the company or legal entity that will deliver the project for the customer. | This field information will be copied to the corresponding field on the Project quote that is created from this Opportunity. |
| Contact | General tab | Reference to the customer's primary contact for this deal. | |
| Account | General tab | Reference to the customer's company or account record. | |
| Account Manager | General tab | The name of the Account manager for this project-based opportunity. | The Account manager is responsible for managing the relationship with the customer through the completion of this project. Based on the bookable resource record tied to the Account manager, the contracting unit is defaulted. |
| Contracting Unit | General tab | The Organization unit that is responsible for the delivery of the project or projects associated with this deal. | The contracting unit is the division of the company that will complete the project(s) after the deal is closed. Every contracting unit has a currency, and this currency is used to report estimated and actual costs incurred during the project. |

For all the other fields and sections on the **Summary** tab of the opportunity, see [Create or edit opportunities (Sales and Sales hub)](/dynamics365/sales-enterprise/create-edit-opportunity-sales).


[!INCLUDE[footer-include](../includes/footer-banner.md)]
