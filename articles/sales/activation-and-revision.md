---
title: Activate and revise a project quote
description: This article provides information about activating and revising quotes in Project Operations.
author: rumant
ms.date: 09/01/2022
ms.topic: article
ms.reviewer: johnmichalak
ms.author: rumant
---

# Activate and revise a project quote

_**Applies To:** Project Operations for resource/non-stocked based scenarios, Lite deployment - deal to proforma invoicing_

**Activation and revision** of quotes helps you keep track of versioning for project quotes during the estimation and negotiation phases. When a draft of a quote is activated, it becomes read-only. Using the **Activation and revision** capability, you're able to: 

- Win or lose quotes only after activation.
- Revise a quote to either make changes to the existing quote or create a new version.

> [!NOTE]
> Enabling the feature for activation and revision of quotes is a one-way operation. Once enabled, the feature can't be disabled.

To turn on the ability to activate and revise project-based quotes, follow these steps:

1. Navigate to **Settings** -> **Parameters**.
1. Open the **Parameters** record, and then open the ribbon menu for **Feature Control**.
1. In the **Feature Control** ribbon menu, select **Enable activation and revision of quotes**.
1. In the confirmation dialog, select **Ok**. 
1. After a few moments, refresh your browser. **Activation and revision** capabilities are now available. It's best to verify that the capability is enabled. Verify this by checking the ribbon menu to ensure the option to **Enable activation and revision for quotes** isn't listed in the menu options. 

## Activating a quote

Once the **Activation and revision** of quotes feature is enabled, **Close quote as Won** and **Close quote as lost** aren't available for draft project quotes. These features are available once a quote is activated. 

Activation represents the stage in the quoting process when you want to prevent any more changes to the quote. At this stage, the quote is sent for internal review or to the customer. 

Activated quotes have the ribbon buttons for **Close quote as Won** and **Close quote as lost**. You can close an activated quote using these buttons based on the outcome of internal or customer reviews. Negotiations and changes can be made on activated quotes using **Revise quote**.

## Revising a quote
If you need to make changes to an activated quote, select **Revise quote**. The quote is closed with the reason code of **revised**, and then a new quote is created with the same ID and an incremented revision number.

All of the details from the original quote are copied to the newly created revision. The newly created quote is in draft status and can be edited as necessary. 





[!INCLUDE[footer-include](../includes/footer-banner.md)]
