---
title: Currency conversion setup for calculating sales prices from cost rates
description: This article provides information about how to configure currency conversion behavior in Project Operations that will be used when generating sales transactions from cost transaction .
author: rumant
ms.date: 11/01/2022
ms.topic: article
ms.reviewer: johnmichalak
ms.author: rumant
---

# Currency conversion setup for calculating sales prices from cost rates

_**Applies To:** Project Operations for resource/non-stocked based scenarios_

In Microsoft Dynamics 365 Project Operations, sales prices for Expense categories can be set up as numeric values or set up to be calculated based on the cost incurred. 

When set up to be calculated based on the cost incurred, the following options are available:
- At cost.
- Mark up percentage over cost.

In scenarios where the expense cost is incurred in a currency that is different from the sales currency for that project contract, 
currency conversion is required to calculate the sales price based on the cost.

## Currency conversion behavior using native Dataverse exchange rates

Project Operations by default uses the currency exchange rates stored in the Currency table in Dataverse. To configure Project Operations to use native exchange rates for claculating sales prices from cost, follow these steps:

1. Navigate to **Project Operations -> Settings -> Parameters**. 
1. Open the **Project Parameter** details page. 
1. Set the field **Currency conversion Logic** to the blank value. 

## Currency conversion behavior using exchange rates from Finance and Operations

The exchange rates in the Currency table that is available natively in Dataverse are not date effective and therefore may not always be scaled to the requirements you may have around calculating sales prices from cost rates. 

You can use exchange rates from the finance and operations environment to calculate the sales price in sales currency from a cost rate in cost currency. To configure this currency conversion behavior, follow these steps:

1. On the **Project parameters** form, add the field **Currency conversion logic**. Save and publish this customization.
1. Navigate to **Project Operations -> Settings -> Parameters**. 
1. Open the **Project Parameter** details page. 
1. Set the field **Currency conversion behavior** to  **Extended with fallback to default**.
1. Make sure to give the Dual-write app user security role **Global Read** permission to the following tables:
      msdyn_currencyexchangerates
      msdyn_currencyexchangeratepairs
      msdyn_exchangeratetypes
1. In your finance and operations environment, run the following Dual-write maps with initial sync:
      Exchange rate type (msdyn_exchangeratetypes)
      Exchange rate currency pair (msdyn_currencyexchangeratepairs)
      CDS Exchange Rates (msdyn_currencyexchangerates)
 
After these changes are completed, the Project Operations application will use the exchange rates from the finance and operations environment that are made available in Dataverse by Dual write to convert cost rate into the contract's sales currency. 
 
 >[!Note]
 >This currency conversion behavior is only applicable to calculate sales prices from cost rates and will not be used to generically calculate base currency values. 
 >Base currency amounts will always use native Dataverse exchange rates irrespective of this setting. 


[!INCLUDE[footer-include](../includes/footer-banner.md)]
