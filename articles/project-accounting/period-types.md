---
title: Period types
description: This article provides information about how to set up period types for revenue estimation.
author: mukumarm
ms.author: mukumarm
ms.date: 02/26/2026
ms.topic: concept-article
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak

---

# Period types

_**Applies To:** Project Operations Integrated with ERP_

A period type defines how frequently revenue on a project is estimated. This article provides information about how to set up period types for revenue estimation. 

## Create and work with period types
To create and work with period types, complete the following steps:

1. In your Dynamics 365 Finance environment, go to **Project management and accounting** > **Setup** > **Estimates** > **Period types**.
1. Select **New** to create a new period type. Enter a name and description.
1. In the **Frequency** field, select a value:

    - If you select **Week**, **Bi-weekly**, **Semi-monthly**, **Month**, **Day**, **Quarter**, or **Year**, the calendar generates the periods. 
    - If you select **Ledger period**, the system uses ledger periods from the General ledger configuration to generate periods.
    - If you select **Unlimited**, you can specify custom periods.
1. Select the period type record and then select **Generate periods** to create periods for the period type. Based on the period frequency that you selected, you might have the option to specify a start date or the number of periods to generate.
1. Select **Periods** to review generated periods.



[!INCLUDE[footer-include](../includes/footer-banner.md)]
