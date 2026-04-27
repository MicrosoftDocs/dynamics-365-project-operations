--- 
title: Configure standard costs for labor and expenses
description: This article explains how to set up standard costs for labor and expenses for a project. 
author: suvaidya
ms.author: nshrivastava
ms.date: 02/26/2026
ms.topic: how-to
ms.custom: 
  - bap-template  
ms.reviewer: johnmichalak

---
# Configure standard costs for labor and expenses

[!include [banner](../../includes/banner.md)]

This article explains how to set up standard costs for labor and expenses for a project. This task uses the USSI data set.

1. In the navigation pane, go to **Modules > Project management and accounting > Setup > Prices > Cost price (hour)**.
1. Select **New**.
1. In the **Effective date** field, enter a date.
1. In the **Cost price** field, enter a number. You can set up a standard cost price for the project category, or you can set up a cost price by worker number, project number, category, date, or any combination of these. The cost price that is applied is the cost price with the highest level of detail.  
1. Select **Save**.
1. In the navigation pane, go to **Modules > Project management and accounting > Setup > Prices > Sales price (hour)**.
1. Select **New**.
1. In the **Effective date** field, enter a date.
1. In the **Valid for** field, select an option.
1. In the **Pricing** field, enter a number. You can set up a standard sales price for hour transactions or for a project category. You can also set up sales prices by worker number, project number, category, transaction date, or any combination of these. The actual sales price, which is applied when a worker enters a transaction in the Hour journal, is the sales price with the highest level of detail. For example, if both a general sales price and a worker-specific sales price are set up, the worker-specific sales price is used.  
1. Select **Save**.
1. Close the page.
1. In the navigation pane, go to **Modules > Project management and accounting > Setup > Prices > Cost price (expense)**.
1. Select **New**.
1. In the **Effective date** field, enter a date.
1. In the **Cost price** field, enter a number. You can fill in multiple fields, but this field is the minimum needed to save the record.  
1. Select **Save**.
1. In the navigation pane, go to **Modules > Project management and accounting > Setup > Prices > Sales price (expense)**.
1. Select **New**.
1. In the **Effective date** field, enter a date.
1. In the **Valid for** field, select an option.
1. In the **Pricing** field, enter a number. The actual sales price, which is applied when a worker enters transactions in an expense journal, is the sales price with the highest level of detail. For example, if both a general and a worker-specific sales price are set up, the worker-specific sales price is used.  
1. Select **Save**.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
