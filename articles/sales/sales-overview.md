---
title: Sales process overview
description: This article provides information about basic sales processes.  
author: poojafandan
ms.date: 02/25/2026
ms.topic: overview
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak
ms.author: poojafandan

---

# Sales process overview

_**Applies To:** Project Operations Integrated with ERP, Project Operations Core_

The sales processes that a project-based organization uses differ from the sales processes that a product-based organization uses. The sales cycles for project-based organizations are longer and require customized estimate techniques to analyze and create quotes for each deal. Dynamics 365 Project Operations uses some of the following functionality that is used in a sales process:

- A lead record tracks the sales process.
- Qualifying leads are tracked as opportunities.
- All related artifacts for an opportunity are accessible. These artifacts include the sales team, stakeholders, probability, rating, sales stages, and business processes.
- Multiple quotes are created for an opportunity.
- A quote is given the status, **Closed as Won** to create a sales order. In Project Operations, the sales order is customized and called a project contract.

## Estimate a sale

You can estimate the value of a sale based on projects that you previously delivered and the complexity of the projects. For projects that involve extensions to previous projects, or projects where the vendor's expertise is high and well-known work templates are used, you can use a simpler estimation process. More complex projects usually have a longer purchase process. Therefore, there are more stages in the sales estimation process. Early in the process, the sales team uses the input of account managers and subject matter experts (SMEs) to create a high-level estimate for each distinct component of work that is quoted. These components of work are represented by quote lines.

You can create a high-level estimate of the quote. Eventually, you replace this high-level estimate with a more detailed estimate that is based on a project plan that you create by using the standardized project templates. These templates help you build a schedule and determine monetary values on the quote and its components (quote lines).

You can create multiple quotes for a project and group them under a single opportunity record. Eventually, you mark one of the quotes **Closed as Won**, and create a project contract or statement of work (SOW). A project contract holds the contracted value for each component (contract line) that the customer accepts for delivery. An SOW is usually created as a Microsoft Word document. All invoices that you send to the customer over the course of the project's delivery reference the project contract or SOW.

You can also create alternate quotes under one opportunity record or set up the system so that a project contract is created when a quote is won. In this case, you can attach a Word document that represents the SOW to the project contract record.

## Configure the sales process

Use business process flows to configure your sales process. These flows provide a guided visual interface to move deals forward through the stages of the sales process.

For example, your company might have the following six stages in the sales process:

1. Qualify
1. Estimate
1. Internal review
1. Contract
1. Deliver
1. Close

Your organization might use different entities to represent the same deal as it evolves. Early in the sales process, a deal is represented by the Opportunity entity. As time passes and more details emerge, you might use high-level estimates to create one or more quotes. If internal and customer stakeholders review one of these quotes, the Quote entity represents the deal. After the customer accepts the quote, a project contract or SOW represents the deal. To support this behavior, BPFs are structured so that each stage in the process is linked to a different database table.

The **Qualify** stage in the sales process can be backed by an Opportunity entity. The **Estimate** and **Internal Review** stages can be backed by a Quote entity. The **Contract**, **Delivery**, and **Close** stages can be backed by a Project Contract entity.

As you move deals through the stages, the process prompts you to create the appropriate entity record. The stages can be conditional. For example, if you require an internal review of a quote only if the quote uses a custom price list, you can configure that condition in the appropriate stage of the business process. The **Internal Review** stage is then shown only for quotes that use a custom price list. For all other deals and quotes, the **Estimate** stage is followed by the **Contract** stage.

> [!NOTE]
> Project Operations has specific pages for Opportunity, Quote, Order, and Invoice entity records. You must create these records by using the project information pages for these entities. Otherwise, you won't be able to open the records from the **Project information** page. If you want to open a record from the **Project information** page, you must delete the record and recreate it by using the **Project information** page where the business logic for each of these entity types ensures that the **Type** field of the record is set correctly, and all of the mandatory concepts are properly initialized.

## Track revisions to quotes and project plans in the sales cycle

In Project Operations, you can't track revisions that you make to a quote. Instead, you must mark the existing quote **Closed as Lost** and then create a new quote. You can copy a quote or clone a project-based quote.

## Track comments and approvals of quotes and project contracts

You can manage the review and approval process for quotes and project contracts by using the record wall and posts. Your organization can create custom workflows and plug-ins to assign, redirect, escalate, and manage notifications for the review and approval of work items.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
