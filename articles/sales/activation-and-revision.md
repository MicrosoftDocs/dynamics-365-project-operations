---
title: Activate and revise a project quote
description: This article provides information about activating and revising quotes in Microsoft Dynamics 365 Project Operations.
author: poojafandan
ms.author: poojafandan
ms.date: 02/25/2026
ms.topic: concept-article
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak

---

# Activate and revise a project quote

_**Applies To:** Project Operations Integrated with ERP, Project Operations Core_

Activation and revision capabilities help you keep track of versioning for project-based quotes during the estimation and negotiation phases. When you activate a draft quote, it becomes read-only.

By using the activation and revision capabilities, you can:

- Win or lose quotes only after activation.
- Revise a quote to either make changes to the existing quote or create a new version.

## Activating a quote
Activation represents the stage in the quotation process when you want to prevent more changes to the quote. At this stage, you send the quote for internal review or to the customer.

You need to *Activate* the quote to progress the quote by using the **Close quote as won** and **Close quote as lost** buttons on the Action Pane.

Depending on the outcome of the internal or customer review, you can use one of these buttons to close an activated quote. To make negotiations and changes on activated quotes, select **Revise quote**.

## Revising a quote

If you need to make changes to an activated quote, select **Revise quote**. The system closes the quote and uses the **revised** reason code. The system then creates a new quote with the same ID and an incremented revision number. All the details from the original quote are copied to the new quote. The new quote is in draft status and can be edited as required.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
