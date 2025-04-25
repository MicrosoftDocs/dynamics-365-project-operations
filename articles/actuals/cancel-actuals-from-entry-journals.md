---
title: Cancel actuals created from entry journals
description: Learn about how to cancel actuals that were created via Entry journals in Microsoft Dynamics 365 Project Operations.
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

_**Applies To:** Project Operations for resource/non-stocked based scenarios, Lite deployment - deal to proforma invoicing_

Microsoft Dynamics 365 Project Operations provides the ability to create actuals by confirming entry journals instead of entering Time, Expense, or Material usage logs. When mistakes are made during the creation of entry journals, there's a process to cancel the actuals that were created to help with rectifying the mistake.

## Select and confirm actuals for cancellation

To select and confirm actuals for cancellation, follow these steps.

1. In the **Sales** area of the left navigation pane, in the **Transactions** section, select **Actuals**.
1. In the **Actuals** list, select the actuals that need to be canceled.
1. On the ribbon, select **Cancel**.
   
   ![Select actuals](media/cancel-actuals.png)
   
   > [!NOTE]
   > Only actuals created via entry journals can be canceled using this process. If other actuals are selected, they are ignored when the correction journal is created.

1. This action creates and navigates to the correction journal if one or more of the selected actuals are valid to be canceled. Additionally, the actuals selected for cancellation will have their adjustment status set to **In process**.
1. The newly created journal has a tab named **Actuals to Cancel**. This tab contains a list of all actuals that will be canceled once the entry journal is confirmed.
   
   ![Actuals to cancel](media/cancellation-journal.png)
   
1. Once the list of actuals has been verified, select **Confirm** from the ribbon. This confirmation creates the reversing actuals with an adjustment status of **Unadjustable**, and sets the status of the canceled actuals to **Adjusted**.
   
   > [!NOTE]
   > This process is irreversible and can't be undone once the correction journal is confirmed

[!INCLUDE[footer-include](../includes/footer-banner.md)]
