---
title: Cancel actuals created from entry journals
description: This article provides information about how to cancel actuals which were created via Entry journals in Microsoft Dynamics 365 Project Operations.
author: abriccetti
ms.author: abriccetti
ms.date: 04/15/2025
ms.topic: how-to
mscustom: 
  - bap-template
ms.reviewer: johnmichalak

---

# Cancel actuals created via entry journals

[!INCLUDE[banner](../includes/banner.md)]

_**Applies To:** Project Operations for resource/non-stocked based scenarios, Lite deployment - deal to proforma invoicing_

Microsoft Dynamics 365 Project Operations provides the ability to create actuals by confirming entry journals instead of entering Time, Expense, or Material usage logs. When a mistkae is made during the creation of an entry journal, there is a process to cancel the actual which was created to assist in rectifying the mistake.

## Selecting and confirming actuals for cancellation

1. In the **Sales** area, in the left navigation pane, under **Transactions**, select **Actuals**.
2. In the **Actuals** list, select the actuals which need to be cancelled
3. On the ribbon select **Cancel**
   ![Select actuals](media/cancel-actuals.png)
   > [!NOTE]
   > Only actuals created via entry journals can be cancelled by this process. If other actuals are selected, they will be ignored when the correction journal is created.
5. This actual will create and navigate to the correction journal
6. The newly created journal will have a tab named **Actuals to Cancel**. Here any 
