---
title: Manage project opportunities
description: This article provides information about how to work with opportunities that are related to projects.
author: suvaidya
ms.author: nshrivastava
ms.date: 01/23/2026
ms.topic: how-to
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak

---

# Manage project opportunities

_**Applies To:** Project Operations Integrated with ERP, Project Operations Core_

Project-based companies typically spread their operations for delivery across multiple countries, regions, and geographies. The cost of project execution and delivery varies depending on which geography or division manages the delivery. This variation impacts the margins of the deal. Delivery of project-based services typically involves large quantities of human resource time, considerable expenses for travel, material costs, and other expenses.

Project-based opportunities in Dynamics 365 Project Operations are designed as extensions to Dynamics 365 Sales. This article provides details about the different fields and business logic included in the additional functionality that project-based companies need to manage project-based opportunities.

## View all project-based opportunities

You can see a list of all the project-based opportunities from the **Opportunity** list page.

1. Go to **Sales** > **Opportunities**.
1. Use the **View switcher** to select other filtered views of the opportunities. You can create your own views with custom filter criteria to configure these views and navigation options.

You can create or delete project opportunities from this list page or the detail page.

## Business process flow for project-based deals

Project Operations supports the following business process flows for project-based deals:

- Lead to Opportunity business process
- Opportunity sales process

### Lead to opportunity business process

The lead to opportunity business process supports the following stages:

| Stage | Mapped entity | Functionality |
| --- | --- | --- |
| Qualify | Lead | Qualify the lead to create an account, contact, and an opportunity. |
| Develop | Opportunity | Develop the opportunity to add more information on the work involved, key stakeholders, and competition. |
| Propose | Opportunity | Develop the proposal and get approval from the internal review team. |
| Close | Opportunity | Win the opportunity to close the deal. |

### Opportunity sales process

The Opportunity sales process in Project Operations extends the Opportunity sales process business flow in the Sales application. This business process supports the following stages in a project-based opportunity.

| Stage | Mapped entity | Functionality |
| --- | --- | --- |
| Qualify | Opportunity | Qualify the lead to create an account, contact, and an opportunity. |
| Propose | Quote | Develop the proposal using project quotes and get approval from the internal review team. |
| Contract | Project Contract | Win the quote to create the contract and begin execution and delivery on the project. |
| Close | Project Contract | Finish the work successfully and close the project contract. |

> [!NOTE]
> If your project-based deal starts with a Lead, the Lead to Opportunity business process takes precedence.
>
> If your project-based deal starts with an Opportunity, the Opportunity sales process takes precedence.

You can edit the product business process flow or create your own business process flows to track your sales process. For more information about business process flows, see [Business process flows overview](/dynamics365/customerengagement/on-premises/customize/business-process-flows-overview).

[!INCLUDE[footer-include](../includes/footer-banner.md)]
