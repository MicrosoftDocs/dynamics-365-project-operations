---
title: 
description: 
author: rumant
manager: Annbe
ms.date: 10/15/2020
ms.topic: article
ms.service: dynamics-365-customerservice
ms.reviewer: kfend 
ms.author: rumant
---

# 

_**Applies To:** Project Operations for resource/non-stocked based scenarios, Lite deployment - deal to proforma invoicing_


# Setup of Price lists in Project Operations

Price list in Project operations represent the concept of a catalog of rates. The rates could be expressing cost rates and sales or bill rates. Depending on whether the catalog of rates or the &quot;Price List&quot; is expressing cost rates or sales/bill rates, the Price list context is set to either &quot;Sales&quot; or &quot;Cost&quot;.

The following are Project Operations&#39; extensions to the price list from Dynamics 365 Sales application:

1. Context
  1. This is a field that has the supported values of Cost and Sales. Purchase value exists however, is not supported. Setting the context to &quot;Cost&quot; makes the price list a &quot;Cost&quot; price list and setting the context to &quot;Sales&quot; makes the price list a &quot;Sales&quot; Price list.
  2. Cost price lists are used to resolve price for cost type of estimate and actuals records.
  3. Sales price lists are used to resolve the price on Estimated and Actual records of Unbilled and Billed Sales types.
2. Time Unit
  1. Time unit is used to default the unit of time for which price is being setup in the related Role Price table for this Price List.
3. Price List Entity
  1. This is a hidden field and is used to internally by Project Operations to differentate price lists that are Quote or Contract – specific from those that are standard and globally applicable.

## Price List Header Information

Below are the fields on the General tab on a Price list that are either entirely unique to Project Operations or have some important changes in behavior from D365 Sales Price Lists:

| **Field** | **Location** | **Relevance, purpose, and guidance** | **Downstream impact** |
| --- | --- | --- | --- |
| Name | General tab and Quick create forms | This is a value to identify the price list. | The price list will be shown with this value on all list pages and dropdown options.|
| Context | General tab and Quick create forms | This is an option set with the following supported values:</br>- Cost</br>- Sales | A price list that has the context set to Cost is used to look up price for Cost estimates and Cost actuals.A price list that has the context set to Sales is used to look up price for Sales estimates and Sales actuals.Only Price Lists that have the context set to Sales are allowed to be attached to Project Price lists on Customers, Project Quotes and Project Contracts |
| Start Date | General tab and Quick create forms | Represents that start date of the period in which is price list is effective | Together with End date field below, this is used for determining which Price list is applicable for a certain estimate or actual line. |
| End Date | General tab and Quick create forms | Represents that end date of the period in which is price list is effective | Together with Start date field above, this is used to determine which Price list is applicable for a certain estimate or actual line. |
| Currency | General tab and Quick create forms | This is used for defaulting the currency on each Role, Category or Price list item line related to this price list. | On &quot;sales&quot; price lists, it is not allowed to create a role, category, or price list item line in any currency other than this currency.On &quot;cost&quot; price lists, you can create a role price line in any currency irrespective of what is defined here. The currency defined here is used for defaulting and user setting up related role prices can override this value to enable labor cost rate setup in any currency.Category cost rates and price list item costs however, can be setup only in the currency defined here. |
| Time Unit | General tab and Quick create forms | This is used for defaulting the time unit on each Role line related to this price list. | This field value is only used on related Role prices setup. On &quot;cost&quot; and &quot;sales&quot; price lists, you can create a role price line in any unit of time irrespective of what is defined here. The time unit defined here is used for defaulting and user setting up related role prices can override this value to enable labor cost and bill rate setup in any unit of time. |
| Description | General tab and Quick create forms | This is a text field and allows you to have multi-line description of the price list | This field will be shown in Associated views on Price list in various entities that have related price lists |
