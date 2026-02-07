---
title: Set up price lists
description: Learn how to set up cost, sales, and purchase price lists in Dynamics 365 Project Operations. Optimize pricing strategies with step-by-step guidance.
author: rumant
ms.date: 03/26/2024
ms.topic: how-to
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak
ms.author: rumant
---

# Set up price lists

[!INCLUDE[banner](../includes/banner.md)]

_**Applies To:** Project Operations Integrated with ERP, Project Operations Core._

Price lists in Dynamics 365 Project Operations represent a catalog of rates. The rates express cost, sales, and bill rates. Depending on whether the price list expresses cost rates or sales and bill rates, the context of the price list is **Sales**, **Cost**, or **Purchase**.

The following extensions are specific to Project Operations and are applied to price lists from Dynamics 365 Sales.

- **Context**: This field has the supported values, **Cost**, **Sales**, and **Purchase**. Set the context to **Cost** to make a cost price list, set the context to **Sales** for a sales price list, and **Purchase** for a vendor price list. Cost price lists and Purchase price lists resolve the price for the cost type on estimate and actuals records. Sales price lists resolve the price on estimated and actual records of unbilled and billed sales types.
- **Time Unit**: This field is the default unit of time for which the price is set up in the related **Role Price** table for this price List.
- **Price List Entity**: This hidden field is used by Project Operations to differentiate price lists that are quote or contract-specific from those that are standard and globally applicable.

## Price list header

The following table includes the fields on the **General** tab of a price list that are unique to Project Operations or have significant changes in behavior from price lists in Sales.

| Field | Location | Description | Downstream impact |
| --- | --- | --- | --- |
| Name | **General** tab and **Quick Create** forms | The identity of the price list. | The price list shows this value on all list pages and drop-down options.|
| Context | **General** tab and **Quick Create** forms | Set this field to **Cost**, **Sales**, or **Purchase**. | A price list set to **Cost** is used to look up the price for cost estimates and cost actuals. A price list set to **Sales** is used to look up the price for sales estimates and sales actuals. A price list set to **Purchase** is used to look up the price for vendor cost estimates and vendor cost actuals. Only price lists that have the context set to **Sales** can be attached to project price lists for customers, project quotes, and project contracts. |
| Start Date | **General** tab and **Quick Create** forms | The start date of the period in which the price list is effective. | With the **End Date** field, this field is used to determine which price list is applicable for a certain estimate or actual line. |
| End Date | **General** tab and **Quick Create** forms | The end date of the period in which the price list is effective. | With the **Start Date** field, this field is used to determine which price list is applicable for a certain estimate or actual line. |
| Currency | **General** tab and **Quick Create** forms | This field defaults the currency on each role, category, or price list item line related to this price list. | On **Sales** price lists, you can't create roles, categories, or price list item lines in any currency other than this currency. On **Cost** price lists, you can create a role price line in any currency. The currency defined here's used as a default. The user setup that is related role prices can override this value to enable labor cost rate setup in any currency. Category cost rates and price list item costs can be set up only in the currency defined here. |
| Time Unit | **General** tab and **Quick Create** forms | This field defaults the time unit on each role line related to this price list. | This field value is only used on related role price setup. On **Cost**, **Sales**, and **Purchase** price lists, you can create a role price line in any unit of time. The time unit defined here's used as a default. The user setup related role prices can override this value to enable labor cost and bill rate setup in any unit of time. |
| Description | **General** tab and **Quick Create** forms | This text field allows you to provide a multi-line description of the price list. | This field is shown in the **Associated** views on the price list in various entities that have related price lists. |

[!INCLUDE[footer-include](../includes/footer-banner.md)]
