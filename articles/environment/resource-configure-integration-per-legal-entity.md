---
title: Configure Project Operations integration per legal entity 
description: This article provides information about setting up integration by legal entity in Project Operations.
author: mukumarm
ms.author: mukumarm
ms.date: 07/09/2024
ms.topic: how-to
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak

---

# Configure Project Operations integration per legal entity 

[!INCLUDE[banner](../includes/banner.md)]

_**Applies To:** Project Operations Integrated with ERP_

This article walks you through the steps required to configure Dynamics 365 Project Operations per legal entity.

## Enable feature keys in Dynamics 365 Finance

As of the application version 10.0.39, there are no prerequisite features in the **Feature Management** workspace required to enable Project Operations. However, there may be features available to enable newly available functionality that extends the base capabilities of Project Operations.

## Define the Project Operations deployment scenario for a legal entity

You can enable Project Operations on Dynamics 365 Customer Engagement on a legal entity level. You can have one legal entity using Project Operations on Dynamics 365 Customer Engagement for resource/non-stocked based scenarios. In the same environment, you can have another legal entity using Project Operations for manufacturing.

1. In Dynamics 365 Finance, go to **Project management and accounting** > **Setup** > **Global project management and accounting parameters**.
2. In the list of available legal entities, select entities where multiple contract lines and Project Operations on Dynamics 365 Customer Engagement features will be enabled. Leave legal entities that will be using Project Operations for manufacturing unselected.

> [!NOTE]
> A legal entity can be selected only if it doesn't have any existing projects.

## Configure Project management and accounting parameters

Each legal entity using Project Operations on Dynamics 365 Customer Engagement needs a set of default parameters. These parameters are configured on the **Project Operations** tab on the **Project management and accounting parameters** page. The parameters are:

  - **Billing type defaults**: Project Operations uses a fixed set of billing type defaults that must be mapped to line properties Finance. Create a record for each billing type: **Not specified**, **Chargeable**, **Non-chargeable**, **Complimentary**, and **Not available**.
  - **Project category defaults**: Select the default project categories to be used for each transaction type. These defaults will be used in the **Project Operations Integration journal** and in estimates where no transaction category is specified for the project actual.
  - **Forecasts**: Select the forecast model to be used for time and expense estimates.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
