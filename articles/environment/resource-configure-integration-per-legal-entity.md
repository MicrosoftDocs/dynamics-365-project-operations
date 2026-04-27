---
title: Configure Project Operations integration per legal entity 
description: This article provides information about setting up integration by legal entity in Project Operations.
author: mukumarm
ms.author: mukumarm
ms.date: 02/27/2026
ms.topic: how-to
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak

---

# Configure Project Operations integration per legal entity 

[!INCLUDE[banner](../includes/banner.md)]

_**Applies To:** Project Operations Integrated with ERP_

This article describes how to configure Dynamics 365 Project Operations for each legal entity.

## Enable feature keys in Dynamics 365 Finance

Starting with application version 10.0.39, the **Feature Management** workspace doesn't require any prerequisite features to enable Project Operations. However, you might see features that you can enable to use newly available functionality that extends the base capabilities of Project Operations.

## Define the Project Operations deployment scenario for a legal entity

Enable Project Operations on Dynamics 365 Customer Engagement at the legal entity level. One legal entity can use Project Operations on Dynamics 365 Customer Engagement for Project Operations Integrated with ERP based scenarios. In the same environment, another legal entity can use Project Operations for manufacturing.

1. In Dynamics 365 Finance, go to **Project management and accounting** > **Setup** > **Global project management and accounting parameters**.
1. In the list of available legal entities, select entities where you want to enable multiple contract lines and Project Operations on Dynamics 365 Customer Engagement features. Don't select legal entities that use Project Operations for manufacturing.

> [!NOTE]
> You can select a legal entity only if it doesn't have any existing projects.

## Configure Project management and accounting parameters

Each legal entity that uses Project Operations on Dynamics 365 Customer Engagement needs a set of default parameters. Configure these parameters on the **Project Operations** tab in the **Project management and accounting parameters** page. The parameters are:

  - **Billing type defaults**: Project Operations uses a fixed set of billing type defaults that you map to line properties in Finance. Create a record for each billing type: **Not specified**, **Chargeable**, **Non-chargeable**, **Complimentary**, and **Not available**.
  - **Project category defaults**: Select the default project categories for each transaction type. The **Project Operations Integration journal** and estimates use these defaults when no transaction category is specified for the project actual.
  - **Forecasts**: Select the forecast model to use for time and expense estimates.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
