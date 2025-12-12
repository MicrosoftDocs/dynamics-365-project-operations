---
title: Use an existing field in Project Service as a pricing dimension
description: This article provides information about using existing Project Service fields as pricing dimensions.
author: Rumant
ms.custom: 
  - dyn365-projectservice
  - evergreen
ms.date: 07/07/2025
ms.update-cycle: 1095-days
ms.topic: article
ms.author: rumant
audience: Admin
search.audienceType: 
  - admin
  - customizer
  - enduser
ms.reviewer: johnmichalak
---

# Use an existing field in Project Service as a pricing dimension

[!include [banner](../includes/psa-now-project-operations.md)]

Project Service Automation (PSA) has many fields on the **Actuals** entity that can be used as pricing dimensions for resource-based pricing in project organizations. For example, one common field is **Bookable Resource**. Smaller companies that have fewer than 20-30 billable resources may find that having bill and cost rates specific to each resource is a simpler approach. However, as the billable workforce grows, specific rates could become unrealistic to maintain as resource cost and bill rates begin to vary as resources get promoted, gain more experience, or acquire a different skill set. 
Because this approach still works for companies of a certain size, see [Use a bookable resource as a pricing dimension](bookable-resource-pricing-dimension.md) to understand how an existing Project Service field can be used as a pricing dimension.

Another example is that of transaction category. Customers and Implementers have used the transaction category in PSA to classify work and use the field to price and cost based on the category of work. For more information, see [Use transaction category as a pricing dimension](transaction-category-pricing-dimension.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]
