---
# required metadata

title: Project Operations fields as pricing dimensions
description: 
author: rumant
manager: AnnBe
ms.date: 08/11/2020
ms.topic: article
ms.prod: 
ms.service: dynamics-project-operations
ms.technology: 

# optional metadata

# ms.search.form: 
# ROBOTS: 
audience: Application User
# ms.devlang: 
ms.reviewer: kfend
ms.search.scope: 
# ms.tgt_pltfrm: 
ms.custom: 
ms.assetid: 
ms.search.region: Global
ms.search.industry: Service industries
ms.author: suvaidya
ms.dyn365.ops.version: 
ms.search.validFrom: 2020-10-01
---

# Project Operations fields as pricing dimensions

Dynamics 365 Project Operations has many fields on the **Actuals** entity that can be used as pricing dimensions for resource-based pricing in project organizations. For example, one common field is **Bookable Resource**. Smaller companies that have fewer than 20-30 billable resources may find that having bill and cost rates specific to each resource is a simpler approach. However, as the billable workforce grows, this could become unrealistic to maintain as resource cost and bill rates begin to vary as resources get promoted, gain more experience, or acquire a different skill sets. 
Because this approach still works for companies of a certain size, see the topic, [Use a bookable resource as a pricing dimension](bookable-resource-pricing-dimension.md) to understand how an existing Project Operations field can be used as a pricing dimension.

Another example is that of transaction category. Customers and Implementers have used the transaction category to classify work and use the field to price and cost based on the category of work. For more information, see [Use transaction category as a pricing dimension](transaction-category-pricing-dimension.md).
