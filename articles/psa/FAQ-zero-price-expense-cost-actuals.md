---
title: Why is the price defaulting to zero on expense cost actuals?
description: Troubleshooting why a price is defaulting to 0 on expense cost actuals.
author: rumant
ms.custom: 
  - dyn365-projectservice
  - evergreen
ms.date:  07/07/2025
ms.topic: article
ms.author: rumant
audience: Admin
search.audienceType: 
  - admin
  - customizer
  - enduser
ms.reviewer: johnmichalak
---

# Why is the price defaulting to zero on expense cost actuals

[!include [banner](../includes/psa-now-project-operations.md)]

[!INCLUDE[cc-applies-to-psa-app-3.x](../includes/cc-applies-to-psa-app-3x.md)]

This FAQ applies to expense actuals where the transaction class is set to Expense and transaction type is Cost.

## Troubleshooting cost rates on expense cost actuals

Go to the related expense entry and make sure that there’s an amount in the expense entry field. If the originating expense entry didn’t have the amount field filled, then you have isolated the problem.
 
To solve this problem, recreate the expense entry with a valid amount and approve it.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
