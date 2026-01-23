---
title: Set up currency conversion to calculate sales prices from cost rates
description: This article explains how to configure the currency conversion behavior that will be used in Microsoft Dynamics 365 Project Operations when sales transactions are generated from cost transactions.
author: suvaidya
ms.date: 01/23/2026
ms.topic: how-to
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak
ms.author: nshrivastava
---

# Set up currency conversion to calculate sales prices from cost rates

[!INCLUDE[banner](../includes/banner.md)]

_**Applies To:** Project Operations Integrated with ERP_

In Microsoft Dynamics 365 Project Operations, you can set up sales prices for expense categories as numeric values. Or, you can set up sales prices so that they're calculated based on the cost that's incurred.

When you set up sales prices to be calculated based on the incurred cost, you can choose from the following options:

- At cost
- Mark up percentage over cost

If the expense cost is in a different currency than the sales currency for the project contract, you need to convert the currency to calculate the sales price based on the cost.

## Currency conversion behavior that uses native Dataverse exchange rates

By default, Project Operations uses the currency exchange rates stored in the Currency table in Dataverse. To configure Project Operations to use native exchange rates to calculate sales prices from cost, follow these steps:

1. Go to **Project Operations \> Settings \> Parameters**.
1. Open the **Project Parameter** details page.
1. Set the **Currency conversion logic** field to a blank value.

## Currency conversion behavior that uses exchange rates from finance and operations apps

The exchange rates in the Currency table that's natively available in Dataverse aren't date effective. Therefore, they might not always meet your requirements for the calculation of sales prices from cost rates.

You can use exchange rates from the finance and operations environment to calculate the sales price in the sales currency from a cost rate in the cost currency. To configure this currency conversion behavior, follow these steps:

1. On the **Project parameters** page, add the **Currency conversion logic** field. Then save and publish the customization.
1. Go to **Project Operations \> Settings \> Parameters**.
1. Open the **Project Parameter** details page. 
1. Set the **Currency conversion behavior** field to **Extended with fallback to default**.
1. Give the **Dual-write app user** security role **Global Read** permission to the following tables:

    - msdyn\_currencyexchangerates
    - msdyn\_currencyexchangeratepairs
    - msdyn\_exchangeratetypes

1. In your finance and operations environment, run the following dual-write maps with initial synchronization:

    - Exchange rate type (msdyn\_exchangeratetypes)
    - Exchange rate currency pair (msdyn\_currencyexchangeratepairs)
    - CDS Exchange Rates (msdyn\_currencyexchangerates)

After you complete these changes, dual-write makes the exchange rates from the finance and operations environment available in Dataverse. Project Operations then uses those exchange rates to convert cost rates into the contract's sales currency.

> [!NOTE]
> This currency conversion behavior applies only to the calculation of sales prices from cost rates. It isn't used to generically calculate base currency values. Base currency values always use native Dataverse exchange rates, regardless of whether you complete this procedure.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
