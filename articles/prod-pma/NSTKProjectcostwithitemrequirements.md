---
title: Purchase orders for Non-stocked/service items with item requirements.
description: This article provides information about project purchase orders for Non-stock/service items with item requirements.
author: mukumarm
ms.author: mukumarm
ms.reviewer: johnmichalak
ms.topic: conceptual
ms.date: 2/21/2023
ms.custom: bap-template
---

# Purchase order for Non-stock/Service items with item requirements

To use **Non-stocked** or **Service** items with **Item requirements**, enable the **Item requirements** parameter using these steps.

1. From **Project management & accounting parameters**, select **Setup**, **Project management & accounting parameters**, and then the **General** tab.
1. Select **Enable creation of item requirement for non-stocked items**.

When a purchase order is created, **Dynamics 365 Finance** generates the project item requirements. Each purchase order line has a direct relationship with project item requirements, and both lines are linked to each other. Any changes to the purchase order have a direct impact on, and updates the project item requirements.

Item requirements are automatically posted when a purchase order packing slip is posted and the parameter **Item consumption** is set to **Yes.** Otherwise, the system shows the message **Do you want to consume the material**. If **Item consumption** is set to **No**, you can post the item requirements manually as well. Regardless of how an item requirement is posted, manually or automatically, the Project cost is generated.

When a **purchase order invoice** is posted, if there is any change in unit price or a discount, then the project cost is updated during the vendor invoice posting process and the project subledger details are updated accordingly.

## Example scenario

The following example shows the **Purchase order** and **Project transactions** for the **Non-stocked** or **Service** items. The purchase order is created with **Net amount** USD 2,000.00. There is a change in vendor invoice **unit price** USD 2,500.00.

![Screenshot of purchase order](media/NSTKWithIRPurchaseorder.png)

The following screen shows the project posted transactions generated when **Purchase Order Product receipt** is posted.

![Screenshot of project posted transactions after product receipt](media/NSTKWithIRPurchaseProductReceipt.png)

The following screen shows the project posted transactions when purchase order vendor invoice is posted. There is a change in **Unit price** and system has posted an adjustment to the existing project posted transaction.

![Screenshot of project posted transactions after vendor invoice](media/NSTKWithIRProjectPostedTransafterVendorInvoice.png)
