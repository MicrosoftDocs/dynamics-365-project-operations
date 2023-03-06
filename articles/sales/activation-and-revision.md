---
title: Activate and revise a project quote
description: This article provides information about activating and revising quotes in Microsoft Dynamics 365 Project Operations.
author: rumant
ms.date: 09/01/2022
ms.topic: article
ms.reviewer: johnmichalak
ms.author: rumant
---

# Activate and revise a project quote

_**Applies To:** Project Operations for resource/non-stocked based scenarios, Lite deployment - deal to proforma invoicing_

Activation and revision capabilities help you keep track of versioning for project-based quotes during the estimation and negotiation phases. When a draft of a quote is activated, it becomes read-only.

The activation and revision capabilities let you perform the following tasks:

- Win or lose quotes only after activation.
- Revise a quote to either make changes to the existing quote or create a new version.

> [!NOTE]
> After the feature for activation and revision of quotes is enabled, it can't be disabled.

To turn on the ability to activate and revise project-based quotes, follow these steps.

1. Go to **Settings** \> **Parameters**.
1. Open the **Parameters** record.
1. On the Action Pane, on the **Feature Control** tab, select **Enable activation and revision of quotes**.
1. In the confirmation dialog box, select **OK**.
1. After a few moments, refresh your browser. Activation and revision capabilities should now be available. You will know that these capabilities have been enabled if the **Enable activation and revision for quotes** button no longer appears on the Action Pane.

## Activating a quote

After the feature for activation and revision of quotes is enabled, the **Close quote as won** and **Close quote as lost** buttons on the Action Pane aren't available for draft project quotes. They are available only after a quote is activated.

Activation represents the stage in the quotation process when you want to prevent more changes to the quote. At this stage, the quote is sent for internal review or to the customer.

The **Close quote as won** and **Close quote as lost** buttons on the Action Pane are available for activated quotes. Depending on the outcome of the internal or customer review, you can use one of these buttons to close an activated quote. You can make negotiations and changes on activated quotes by selecting **Revise quote**.

## Revising a quote

If you must make changes to an activated quote, select **Revise quote**. The quote is closed, and the **revised** reason code is used. A new quote is then created that has the same ID and an incremented revision number. All the details from the original quote are copied to the new quote. The new quote is in draft status and can be edited as required.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
