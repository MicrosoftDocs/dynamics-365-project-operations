---
title: Period types
description: This topic provides information about how to set up period types for revenue estimation.
author: sigitac
ms.date: 11/16/2020
ms.topic: article
ms.reviewer: johnmichalak
ms.author: sigitac
---

# Period types

_**Applies To:** Project Operations for resource/non-stocked based scenarios_

A period type defines how frequently revenue on a project is estimated. This topic provides information about how to set up period types for revenue estimation. 

## Create and work with period types
To create and work with period types, complete the following steps:

1. In your Dynamics 365 Finance environment, go to **Project management and accounting** > **Setup** > **Estimates** > **Period types**.
2. Select **New** to create new period type. Enter a name and description.
3. In the **Frequency** field, select a value:

    - If you select **Week**, **Bi-weekly**, **Semi-monthly**, **Month**, **Day**, **Quarter**, or **Year**, the calendar will be used to generate the periods. 
    - If you select **Ledger period**, ledger periods from the General ledger configuration will be used to generate periods.
    - If you select **Unlimited**, you can specify custom periods.
4. Select the period type record and then select **Generate periods** to create periods for the period type. Based on the period frequency that you selected, you might have the option to specify a start date or the number of periods to generate.
5. Select **Periods** to review generated periods.



[!INCLUDE[footer-include](../includes/footer-banner.md)]