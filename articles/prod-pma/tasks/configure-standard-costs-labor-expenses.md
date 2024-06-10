--- 
title: Configure standard costs for labor and expenses
description: This article explains how to set up standard costs for labor and expenses for a project. 
author: suvaidya
ms.author: suvaidya
ms.date: 06/10/2024
ms.topic: how-to
ms.custom: 
  - bap-template  
ms.reviewer: johnmichalak

---
# Configure standard costs for labor and expenses

[!include [banner](../../includes/banner.md)]

This article explains how to set up standard costs for labor and expenses for a project. This task uses the USSI data set.

1. In the navigation pane, go to **Modules > Project management and accounting > Setup > Prices > Cost price (hour)**.
2. Select **New**.
3. In the **Effective date** field, enter a date.
4. In the **Cost price** field, enter a number. You can set up a standard cost price for the project category, or you can set up a cost price by worker number, project number, category, date, or any combination of these. The cost price that is applied is the cost price with the highest level of detail.  
5. Select **Save**.
6. In the navigation pane, go to **Modules > Project management and accounting > Setup > Prices > Sales price (hour)**.
7. Select **New**.
8. In the **Effective date** field, enter a date.
9. In the **Valid for** field, select an option.
10. In the **Pricing** field, enter a number. You can set up a standard sales price for hour transactions or for a project category. You can also set up sales prices by worker number, project number, category, transaction date, or any combination of these. The actual sales price, which is applied when a worker enters a transaction in the Hour journal, is the sales price with the highest level of detail. For example, if both a general sales price and a worker-specific sales price are set up, the worker-specific sales price is used.  
11. Select **Save**.
12. Close the page.
13. In the navigation pane, go to **Modules > Project management and accounting > Setup > Prices > Cost price (expense)**.
14. Select **New**.
15. In the **Effective date** field, enter a date.
16. In the **Cost price** field, enter a number. Multiple fields can be filled in, but this is the minimum needed to save the record.  
17. Select **Save**.
18. In the navigation pane, go to **Modules > Project management and accounting > Setup > Prices > Sales price (expense)**.
19. Select **New**.
20. In the **Effective date** field, enter a date.
21. In the **Valid for** field, select an option.
22. In the **Pricing** field, enter a number. The actual sales price, which is applied when a worker enters transactions in an expense journal, is the sales price with the highest level of detail. For example, if both a general and a worker-specific sales price are set up, the worker-specific sales price is used.  
23. Select **Save**.



[!INCLUDE[footer-include](../../includes/footer-banner.md)]
