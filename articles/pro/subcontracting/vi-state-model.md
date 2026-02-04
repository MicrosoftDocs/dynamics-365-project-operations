---
title: State transitions on a vendor invoice
description: Learn how to manage state transitions on vendor invoices in Microsoft Dynamics 365 Project Operations. Understand key states like Draft, Confirmed, and Canceled.
author: rumant
ms.date: 02/04/2026
ms.topic: concept-article
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak
ms.author: rumant
---

# State transitions on a vendor invoice

[!INCLUDE[banner](../../includes/banner.md)]

_**Applies To:** Project Operations Core_

This article explains the state transitions on a vendor invoice in Microsoft Dynamics 365 Project Operations. The following states are used: **Draft**, **In review**, **Confirmed**, **On hold**, and **Canceled**.

The following illustration shows the state transitions.

:::image type="content" source="../media/VI_State_Model.jpg" alt-text="Screenshot of the vendor invoice state transition model showing Draft, In review, Confirmed, On hold, and Canceled states.":::

The following table explains what each state represents in the lifecycle of a vendor invoice in Project Operations.

| State | Description | Allowed transitions |
| --- | --- | --- |
| Draft | This state is the initial state of a vendor invoice. You can modify the lines and pricing. You can edit and delete a vendor invoice in this state. | In process |
| In review | This state represents the processing state of a vendor invoice. At least one vendor invoice line has a verification status of **In progress**. | Confirmed, On hold |
| Confirmed | This state represents the stage of a vendor invoice where the application creates cost actuals for each vendor invoice line. The application reverses any linked cost actuals that it matched to the vendor invoice lines and replaces them with the cost actuals from those vendor invoice lines. You can't edit or delete a vendor invoice in this state. You can use the **Cancel** button to cancel a confirmed vendor invoice. The Cancel action reverses the impact of the Confirm action. | Canceled |
| On hold | <p>This state represents a stage of a vendor invoice where the vendor invoice can't move because of an issue with the invoice or the vendor's status. You can't confirm, cancel, edit, or delete a vendor invoice in this state.</p><p>You can use the Re-open action to move the vendor invoice to the **Draft** or **In review** state. If at least one line on the vendor invoice has a verification status of **In progress** or **Complete**, the vendor invoice reopens in the **In review** state. If all the lines on the vendor invoice have a verification status of **Not started**, the vendor invoice reopens in the **Draft** state.</p> | Draft, In review |
| Canceled | This state represents the stage of a subcontract where actual delivery of materials and work by subcontracted resources is no longer required. A subcontract in this state can't estimate and staff project requirements for resources and materials. You can't reference it on time, expense, and material usage on a project. You can't edit or delete a subcontract in this state. | None |

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
