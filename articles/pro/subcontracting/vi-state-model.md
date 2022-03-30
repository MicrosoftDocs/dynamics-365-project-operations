---
title: State transitions on a vendor invoice
description: This topic explains the state transitions on a vendor invoice in Microsoft Dynamics 365 Project Operations.
author: rumant
ms.date: 03/30/2022
ms.topic: article
ms.reviewer: tonyafehr 
ms.author: rumant
---

# State transitions on a vendor invoice

[!include [banner](../../includes/dataverse-preview.md)]

_**Applies To:** Lite deployment - deal to proforma invoicing_

This topic explains the state transitions on a vendor invoice in Microsoft Dynamics 365 Project Operations. Each state is represented as either Draft, In review, On hold, confirmed, or canceled. The following image represents the state transitions.
The following image represents the state transitions.

![Subcontract state model](../media/SubconStates.png)  

The following table provides a description of what each state represents in the lifecycle of a vendor invoice in Project Operations.

| **State** | **Description** | **Allowed transitions** |
| --- | --- | --- |
| Draft | This represents the initial state of a vendor invoice. The lines and pricing are subject to modifications. A vendor invoice in this state can be edited and deleted. | In process |
| In review | This represents the processing state of a vendor invoice. At least one vendor invoice line is in verification status **In progress** | Confirmed, On hold |
| Confirmed | This represents a stage in the Vendor invoice when the application has created cost actuals for each vendor invoice line. A linked cost actuals that were matched with the vendor invoice lines have been reversed and replaced with the cost actuals from the vendor invoice line. A vendor invoice in this state cannot be edited or deleted. The  **Cancel**  button allows you to cancel a confirmed vendor invoice. This will reverse the impact of the **Confirm** action. | Canceled |
| On hold | This represents the stage of a vendor invoice when the vendor invoice cannot move in the lifecycle due to an issue with the invoice or with the vendor&#39;s status. A vendor invoice in this state cannot be confirmed, canceled, edited, or deleted. Use the Re-open action to move the Vendor invoice to Draft or to **In review** status. When at least one line on the vendor invoice is in **In progress** or **Complete** verification status, the vendor invoice will be re-opened in **In review** status. When all lines on the vendor invoice are verification status **Not started** , the vendor invoice will be re-opened in **Draft** status. | Draft, In Review |
| Canceled | This represents the stage of a subcontract when actual delivery of materials and/or work by subcontracted resources is no longer needed. A subcontract in this state cannot be used to estimate and staff project requirements for resources and materials nor can it be referenced on time, expense, and material usage on a project. A subcontract in this state cannot be edited or deleted. | None |


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
