---
title: Activate and revise a project quote
description: This article provides information about activating and revising quotes in Microsoft Dynamics 365 Project Operations.
author: poojafandan
ms.author: poojafandan
ms.date: 06/10/2024
ms.topic: concept-article
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak

---

# Activate and revise a project quote

_**Applies To:** Project Operations Integrated with ERP, Project Operations Core_

Activation and revision capabilities help you keep track of versioning for project-based quotes during the estimation and negotiation phases. When a draft of a quote is activated, it becomes read-only.

The activation and revision capabilities let you perform the following tasks:

- Win or lose quotes only after activation.
- Revise a quote to either make changes to the existing quote or create a new version.

## Activating a quote
Activation represents the stage in the quotation process when you want to prevent more changes to the quote. At this stage, the quote is sent for internal review or to the customer.

You need to *Activate* the quote in order to progress the quote with the **Close quote as won** and **Close quote as lost** buttons on the Action Pane.

Depending on the outcome of the internal or customer review, you can use one of these buttons to close an activated quote. You can make negotiations and changes on activated quotes by selecting **Revise quote**.

## Revising a quote

If you must make changes to an activated quote, select **Revise quote**. The quote is closed, and the **revised** reason code is used. A new quote is then created that has the same ID and an incremented revision number. All the details from the original quote are copied to the new quote. The new quote is in draft status and can be edited as required.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
