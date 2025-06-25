---
title: Copy price lists
description: This article provides information about how to copy price lists in Project Operations.
author: abriccetti
ms.author: abriccetti
ms.date: 01/09/2025
ms.topic: how-to
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak

---

# Copy price lists

[!INCLUDE[banner](../includes/banner.md)]

_**Applies To:** Project Operations Integrated with ERP, Core deployment - deal to proforma invoicing_

You can create copies of price lists in Dynamics 365 Project Operations. For example, you can create price lists for the upcoming year using a price list from the current year.  Or, you might copy a price list for bill rates and sales prices from the price lists for cost. 

To make a copy of price list, complete the following steps.

1. Open the price list that you want to make a copy of and select **Copy**.
2. Enter any necessary information to copy the price list. The following table shows considerations to keep in mind when entering information.

| Field | Description | Downstream impact |
| --- | --- | --- |
| Name | The name of the source price list with the **-copy** appended. | The price list includes this value on all list pages and drop-down options. |
| Context | Enter the context that you want for the target price list. | A price list that has the context set to **Cost** is used to look up the price for cost estimates and cost actuals. A price list that has the context set to **Sales** is used to look up price for sales estimates and sales actuals. Only price lists that have the context set to **Sales** can be attached to a project price list for a customer, quotes, or contract. |
| Start Date | The start date of the period in which is price list is effective. | Together with **End Date**, this field is used to determine which price list is applicable for a certain estimate or actual line. |
| End Date | The end date of the period in which is price list is effective. | Together with **Start Date**, this field is used to determine which price list is applicable for a certain estimate or actual line. |
| Currency | The currency of the source price list. This can be changed. | When this is changed, all resulting price lines for labor, expense, and product catalog items are converted to the target price list currency during the copy. |
| Time Unit | The currency of the source price list. This can be changed. | When this is changed, all the resulting price lines for labor items are converted to the target price list unit during the copy. The conversion from the unit setup for the source price list time unit and target price list time unit is used. |
| Description | A description of the source price list with the **-copy** appended. This is a text field and allows you to have multi-line description of the price list. | This field is shown in the **Associated** views on the price list in various entities that have related price lists. |

3. Save the price list. 

## Update a price list by applying a mark-up to all the prices

1. On the **Role**, **Category**, and **Price List Item** tabs of a price list, you can select **Update Prices** to apply a markup for all prices in the subgrid. 
2. On the dialog page that opens, enter a mark-up. You can also enter a negative mark-up percent to decrease prices by a certain percentage. 
3. Select **OK** on the dialog page and then verify that the prices in the subgrid reflect the changes you made.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
