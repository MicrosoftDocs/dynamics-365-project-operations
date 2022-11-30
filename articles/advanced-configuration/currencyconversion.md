---
title: Currency conversion behavior options for calculating sales prices in sales from cost rates 
description: This article provides information about how to configure currency conversion behavior in Project Operations that will be used when generating sales transactions from cost transaction .
author: rumant
ms.date: 11/01/2022
ms.topic: article
ms.reviewer: johnmichalak
ms.author: rumant
---

# Currency conversion behavior options for calculating sales prices in sales from cost rates 

_**Applies To:** Project Operations for resource/non-stocked based scenarios_

In Project Operations, sales prices for Expense categories can be setup as numeric values or setup to be calculated based on the cost incurred. 
The options to calculate based on cost are the following:
1. At cost
2. Mark up percentage over cost
In scenarios where the expense cost is incurred in a currency that is different from the sales currency for that project contract, 
currency conversion is required to calculate the sales price based on the cost.

## Currency conversion behavior using native Dataverse exchange rates
Project Operations by default uses the currency exchange rates stored in the Currency table in Dataverse. To configure that Project Operations is using native exchange rates for claculating sales prices from cost, follow these steps:
1. Navigate to **Project Operations -> Settings->Parameters**. Open the **Project Parameter** details page. 
2. Set the field **Currency conversion Logic** to the blank value. 

## Currency conversion behavior using exchange rates from Finance and Operations
The exchange rates in the Currency table that is available natively in Dataverse are not date effective and therefore may not always be scale to the requirements you may have around calculating sales prices from cost rates. 
You can use excahnge rates from Finance and Operations to calcualte the sales price in sales currency from a cost rate in cost currency. Follow these steps to configure this currency conversion behavior:

1. On the project parameters form, add the field **Currency conversion logic** to the form. Save and publish this customization.
2. Navigate to **Project Operations -> Settings->Parameters**. Open the **Project Parameter** details page. 
3. Set the field **Currency conversion behavior** to  **Extended with fallback to default**.
4. Make sure to give Dual-write app user security role **Global Read** permission to the following tables:
      msdyn_currencyexchangerates
      msdyn_currencyexchangeratepairs
      msdyn_exchangeratetypes
5. In your Finance and Operations environment, run the following Dual write maps  with initial sync:
      Exchange rate type (msdyn_exchangeratetypes)
      Exchange rate currency pair (msdyn_currencyexchangeratepairs)
      CDS Exchange Rates (msdyn_currencyexchangerates)
 
 Once these settings are completed, Project Operations application will use the exchange rates from Finance and Operations that are made available in Dataverse by Dual write to convert cost rate into the contract's sales currency. 
 
 >[!Note]
 >This currency conversion behaivor is only applicable to calculate sales prices from cost rates and will not be used to generically calculate base currency values. 
 >Base currency amounts will always use native dataverse exchange rates irrespective of this setting. 


[!INCLUDE[footer-include](../includes/footer-banner.md)]
