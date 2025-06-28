---
title: Cancel actuals created from entry journals
description: Learn about how to cancel actuals that were created via entry journals in Microsoft Dynamics 365 Project Operations.
author: abriccetti
ms.author: abriccetti
ms.date: 04/25/2025
ms.topic: how-to
mscustom: 
  - bap-template
ms.reviewer: johnmichalak

---

# Cancel actuals created via entry journals

[!INCLUDE[banner](../includes/banner.md)]

_**Applies To:** Project Operations Integrated with ERP, Core deployment - deal to proforma invoicing_

In Microsoft Dynamics 365 Project Operations, you can create actuals by confirming entry journals instead of entering Time, Expense, or Material usage logs. If mistakes are made during the creation of entry journals, use the following procedure to cancel the actuals that were created. In this way, you can correct the mistakes.

## Select and confirm actuals for cancellation

To select and confirm actuals for cancellation, follow these steps.

1. In the left pane, in the **Sales** area, in the **Transactions** section, select **Actuals**.
1. In the grid, select the actuals that must be canceled.
1. On the Action Pane, select **Cancel**.

    :::image type="content" source="media/cancel-actuals.png" alt-text="Screenshot of the Active Actuals page, where one actual is selected in the grid and the Cancel button is highlighted.":::

    > [!NOTE]
    > You can use this procedure to cancel only actuals that were created via entry journals. Any other actuals that you select are ignored when the correction journal is created.

     If one or more of the selected actuals are valid for cancellation, the correction journal is created and opened. Additionally, the adjustment status of the selected actuals is set to **In process**.

1. The newly created journal includes an **Actuals to Cancel** tab. Select this tab to review the list of all actuals that will be canceled after you confirm the entry journal.

    :::image type="content" source="media/cancellation-journal.png" alt-text="Screenshot of the Actuals to Cancel tab on the New Journal page, showing the list of actuals that will be canceled.":::

1. After you finish reviewing the list of actuals, select **Confirm** on the Action Pane.

    The reversing actuals are created, and their adjustment status is set to **Unadjustable**. Additionally, the status of the canceled actuals is set to **Adjusted**.

    > [!IMPORTANT]
    > This process is irreversible. It can't be undone after you confirm the correction journal.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
