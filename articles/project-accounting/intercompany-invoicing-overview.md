---
title: Intercompany invoicing overview
description: This article provides information and examples about intercompany invoicing for projects.
author:  ryansandness
ms.author: ryansandness
ms.date: 02/26/2026
ms.topic: overview
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak

---

# Intercompany invoicing overview

_**Applies To:** Project Operations Integrated with ERP_

Your organization might have multiple divisions, subsidiaries, and other legal entities that transfer products and services to each other for projects. The legal entity that provides the service or product is the *lending legal entity*. The legal entity that receives the service or product is the *borrowing legal entity*.

The following illustration shows a typical scenario where two legal entities, Contoso Robotics USA (the borrowing legal entity) and Contoso Robotics UK (the lending legal entity) share resources to deliver a project for the customer, Adventure works. For this scenario, Contoso Robotics USA is contracted to deliver the work to Adventure Works.

:::image type="content" source="./media/IntercompanyScenario.png" alt-text="Screenshot of intercompany invoicing scenario with two legal entities sharing resources to deliver a project.":::

Dynamics 365 Project Operations uses the following flow to process intercompany transactions:

1. Resources from the lending legal entity record intercompany time or expense transactions by booking time and expense against projects in the borrowing legal entity.
1. The lending company records time and expense costs by using the borrowing company's unit cost price list.
1. The lending company records intercompany unbilled sale transactions by using the borrowing company's unit cost price list.
1. The borrowing company records unbilled revenue using the project contract sales price list. The customer can be billed when unbilled revenue is recorded. The customer doesn't have to wait until intercompany invoice processing is complete.
1. The lending company creates intercompany customer invoices on a periodic basis. You can create the invoices manually or by using a periodic automated process. You can create a single invoice for each borrowing legal entity or create separate invoices by project.
1. When you post the intercompany customer invoice in the lending legal entity, you create the corresponding pending vendor invoice in the borrowing legal entity. The costs in the pending vendor invoice are recorded to the project subledger when you post the invoice.

The following diagram illustrates intercompany invoicing as it relates to accounting events and expected postings to the general ledger.

:::image type="content" source="./media/IntercompanyFlow.png" alt-text="Screenshot of intercompany flow diagram showing accounting events and expected postings to the general ledger.":::

## Additional resources

- [Configure intercompany invoicing](configure-intercompany-invoicing.md)
- [Record intercompany transactions](create-intercompany-transactions.md)
- [Create intercompany customer and vendor invoices](create-intercompany-customer-vendor-invoices.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
