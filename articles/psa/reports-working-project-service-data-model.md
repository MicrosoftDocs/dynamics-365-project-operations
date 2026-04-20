---
title: Working with the Project Service Automation data model
description: This article provides information about how to work with the data model.
author: tulsij
ms.author: dishantpopli
ms.custom: 
  - dyn365-projectservice
  - bap-template
  - evergreen
ms.date: 01/23/2026
ms.update-cycle: 1095-days
ms.topic: how-to
ms.reviewer: johnmichalak
---

# Working with the Project Service Automation data model

[!include [banner](../includes/psa-now-project-operations.md)]

[!INCLUDE[cc-applies-to-psa-app-3.x](../includes/cc-applies-to-psa-app-3x.md)]


Dynamics 365 Project Service Automation extends other app entities and introduces its own entities in the Common Data Service data model. This article describes some of the entities that you encounter in typical PSA reporting scenarios.

## Reporting on opportunities

Project Service Automation extends the Dynamics 365 Sales **Opportunity** entity by adding fields that enable project-based scenarios. These fields use a schema name that's prefixed with **msdyn\_**. One new field that's important for reporting on PSA opportunities is **Order Type**. A value of **Work Based** for this field indicates that the opportunity is a PSA opportunity. Other fields that the extension adds to the entity include **Contracting Organization**, which captures the organization that holds the opportunity, and **Account Manager**, which captures the name of the account manager who's responsible for the opportunity.

The **Opportunity Line** entity also includes fields that are related to Project Service. **Billing Method** indicates whether the opportunity line should be billed on a time-and-materials basis or a fixed-price basis, and **Project** captures the name of the project that backs the opportunity. Other fields that you can report on capture costs and customer budget amounts for the line item.

## Reporting on quotes

PSA extends the Sales **Quote** entity by adding project-related fields. **Order Type** distinguishes PSA quotes from non-PSA quotes. A value of **Work Based** for this field indicates that the quote is a PSA quote. Other fields that can be relevant to reporting on PSA quotes include amount fields, such as **Chargeable Costs**, **Non-chargeable Costs**, **Gross Margin**, **Estimates**, and **Budget**. Other useful fields indicate whether the quote is profitable, whether it will be completed on schedule, and whether it meets the customer's budget expectations.

PSA also extends the Sales **Quote Line** entity. One field that PSA adds is **Billing Method**, which indicates how the quote line is billed (time and materials or fixed price). Other fields that PSA adds to the entity capture the related project that backs the quote line, invoicing, cost, and budget.

PSA also adds new quote-related entities to the Dynamics 365 data model. Here are some examples:

- **Quote Line Detail** – This entity contains the project estimate details of the quote line. It has two records for each quote line. One record stores the cost and cost details of the quote line, and the other record stores the sales amount and sales details of the quote line.
- **Quote Line Invoice Schedule** – This entity contains the billing schedule for the quote line. This schedule is generated based on the invoicing frequency that is assigned to the quote line.
- **Quote Line Milestone** – This entity contains the billing milestones for fixed-price quote lines.
- **Quote Line Analytics Breakdown** – This entity contains financial details of the quote line. These details can be useful for reporting quoted sales and estimated cost amounts by various dimensions.

Other entities that PSA adds to quotes are **Quote Line Project Price List**, **Quote Line Resource Category**, and **Quote Line Transaction Category**.

:::image type="content" source="media/PS-Reporting-image2.png" alt-text="Diagram showing quote, quote line, and project relationships.":::

## Reporting on project contracts

PSA extends the Sales **Order** entity that you use when you record project contracts. It adds an important new field, **Order Type**, that identifies the contract as a PSA project contract instead of a sales order. A value of **Work Based** for this field indicates that the order is a PSA project contract. Other new fields that PSA adds to the **Order** entity capture details about costs, PSA contract status, and the organization that owns the contract.

PSA also extends the **Sales Order Line** entity. Among the fields that it adds are fields that capture the billing method (time and materials or fixed price), customer budget amounts, and the underlying project.

PSA also adds new entities that are designed for project contracts. Here are some examples:

- **Project Contract Line Detail** – This entity contains the line-level details that roll up to the contract line amount. These details can be as detailed as line items that are generated from a project schedule at the task level.
- **Contract Line Invoice Schedule** – This entity contains the billing schedule that is generated based on the invoice frequency that you assign to the contract line.
- **Contract Milestone** – This entity contains the billing milestones for contract lines that have a fixed-price billing term.

Other entities that PSA adds to contracts are **Project Contract Line Project Price List**, **Project Contract Line Resource Category**, and **Project Contract Line Transaction Category**.

:::image type="content" source="media/PS-Reporting-image3.png" alt-text="Diagram showing order, order line, and project relationships.":::

## Reporting on projects

The **Projects** entity and its related entities are exclusive to PSA. **Project** is the top-level entity that you use to capture the work and cost side of operations. Here's a list of the related entities:

- **Project team member** – This entity contains details about the bookable resources that are assigned to the project. Those resources can be generic bookable resources, or they can be named bookable resources that are either entered by the project manager or generated from the project schedule.
- **Project Task** – This entity contains the tasks that make up the project plan or schedule.
- **Resource Assignment** – This entity contains the task assignment for the bookable resource.
- **Resource Requirement** – This entity contains the requirements for any generic resource team members.
- **Estimate** and **Estimate line** – These entities have a header/line relationship and contain expense estimates for the project. Task estimates are stored on the **Resource Estimate** entity.

:::image type="content" source="media/PS-Reporting-image4.png" alt-text="Diagram showing resource requirement and project relationships.":::

## Reporting on resources

Project resources use the **Bookable Resource** entities from Universal Resource Scheduling (URS) that are shared with other apps, such as Microsoft Dynamics 365 Field Service. Here's a list of the entities that you might need to use when you report on project resources:

- **Bookable Resource** – This entity represents the user, contact, generic resource, account, group, or equipment that the project team uses.
- **Bookable Resource Characteristics** – This entity includes the skills, certifications, or education of the resource. The characteristics can have rating values that the rating model defines.
- **Bookable Resource Category** – This entity represents the role of the bookable resource.
- **Bookable resource bookings** – This entity represents the time that the resource books on projects. Each booking has both a header entity and line entities. Each line has a status that represents the status of the booking.

:::image type="content" source="media/PS-Reporting-image5.png" alt-text="Diagram showing bookable resource characteristics relationships.":::

## Reporting on actual transactions

When you approve a timesheet or expense, or invoice a contract in PSA, the business transaction is captured in the **Actual** entity. This entity can serve as the basis for almost all finance-related reports in PSA. The **Actual** entity captures the cost and sales transactions for the business event. It also captures many relevant attributes.

When you work with the **Actual** entity, it's important that you understand what transaction or transactions the entity records, and when it records the transactions. Here's the typical flow when you work with time entries (the flow for expense entries is similar):

1. When you save the time entry, the **Actual** entity isn't updated.
1. When you submit the time entry, the **Actual** entity isn't updated.
1. When you approve the time entry, the **Actual** entity is updated with one or two records. The first record stores the cost of the time entry. The second record stores the unbilled sales amount of the time entry. The second record depends on the project either having a customer, a quote, or a contract line assigned to it.

    | Document date | Transaction type | Transaction class | Customer         | Contract   | Resource     | Resource role | Billing type | Quantity | Unit price | Amount |
    |---------------|------------------|-------------------|------------------|------------|--------------|---------------|--------------|----------|------------|--------|
    | 2/3/18        | Cost             | Time              | Alpine ski house | Alpine CRM | Ashley Chinn | Project Mgr   | Chargeable   | 8.0      | 50.00      | 400.00 |
    | 2/3/18        | Unbilled sales   | Time              | Alpine ski house | Alpine CRM | Ashley Chinn | Project Mgr   | Chargeable   | 8.0      | 100.00     | 800.00 |

    These two records are separate but related records. They're neither debits nor credits.

1. If a contract is associated with the project, when you invoice the time entry, the **Actual** entity is updated with two more records. First, a negative amount for the unbilled sales record. This record essentially reverses the unbilled sale. Second, a transaction for the billed sale. Once again, these records are separate but related records, not debits and credits.

    | Document date | Transaction type | Transaction class | Customer         | Contract   | Resource     | Resource role | Billing type | Quantity | Unit price | Amount   |
    |---------------|------------------|-------------------|------------------|------------|--------------|---------------|--------------|----------|------------|----------|
    | 2/4/18        | Unbilled sales   | Time              | Alpine ski house | Alpine CRM | Ashley Chinn | Project Mgr   | Chargeable   | - 8.0    | 100.00     | - 800.00 |
    | 2/4/18        | Billed sales     | Time              | Alpine ski house | Alpine CRM | Ashley Chinn | Project Mgr   | Chargeable   | 8.0      | 100.00     | 800.00   |

The **Transaction Origin** entity records the origin of the **Actual** record, and the **Transaction Connection** entity records the related records for the **Actual** record. Additionally, the **Actual** record contains references the project, project contract (order), bookable resource, and customer.

:::image type="content" source="media/PS-Reporting-image6.png" alt-text="Diagram showing transaction connection, origin and actual relationships.":::


[!INCLUDE[footer-include](../includes/footer-banner.md)]
