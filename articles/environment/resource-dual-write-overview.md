---
title: Project Operations dual-write integration
description: Learn how Project Operations dual-write integration synchronizes data between Microsoft Dataverse and Dynamics 365 Finance to streamline your workflows.
author: mukumarm
ms.author: mukumarm
ms.date: 02/05/2026
ms.topic: overview
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak

---

# Project Operations dual-write integration overview

[!INCLUDE[banner](../includes/banner.md)]

_**Applies To:** Project Operations Integrated with ERP_

Project Operations uses [dual-write capabilities](/dynamics365/fin-ops-core/dev-itpro/data-entities/dual-write/dual-write-home-page) to synchronize data across Microsoft Dataverse and Dynamics 365 Finance.

The following illustration shows how data is synchronized as part of this integration between Dataverse and Finance.

:::image type="content" source="./media/ProjectOperationsFlows.jpg" alt-text="Screenshot of Project Operations data flows showing synchronization between Dataverse and Finance.":::

Project Operations on Dataverse provides a modern user interface (UI) and easy no-code/low-code extensibility using Power Platform capabilities. Project managers, resource managers, project team members, and other front-office personas perform their activities in Project Operations on Dataverse.

Project Operations in Finance provides project accounting and revenue recognition support. Project Operations plugs in to the financial framework in Finance for sales tax calculation, currency exchange rates, financial dimension reporting, and more. The project accountant experiences are mostly based in Finance.

Project Operations integration consists of the following component integration:

- [Project Operations setup and configuration data integration](resource-dual-write-setup-integration.md) 
- [Project estimates and actuals](resource-dual-write-estimates-actuals.md)
- [Project invoices](resource-dual-write-project-invoice.md)
- [Expense management](resource-dual-write-expense.md)
- [Subcontract purchase orders](../pro/subcontracting/SubconPurchaseorders.md)
- [Vendor invoice](resource-dual-write-vendor-invoice.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
