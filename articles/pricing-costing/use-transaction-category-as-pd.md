--- 
title: Use Transaction Category as a pricing dimension
description:  This article provides information about how to use the Transaction Category field as a pricing dimension.
author:  abriccetti
ms.author: abriccetti
ms.date: 01/09/2025 
ms.topic: how-to
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak
 
--- 

# Use Transaction Category as a pricing dimension

[!INCLUDE[banner](../includes/banner.md)]

_**Applies To:** Project Operations Integrated with ERP, Core deployment - deal to proforma invoicing_


This article explains how to use the **Transaction Category** field as a pricing dimension. 

## Prerequisites
Before you complete the procedures in this article, you must have a new pricing dimension solution for your organization. If you haven't already created one, see [Create custom fields and entities as pricing dimensions](create-custom-fields-entities-pricing-dimensions.md).

## Add the Transaction Category field to forms and views
To make the **Transaction Category** field visible in the pricing dimension solution, you need to add the field to all the forms and views as an entity.

The following table lists all of the out-of-the box forms and views, by entity. You will also need to add the new field to any additional forms or views in your customized entities.

|  Entity        | Forms     |Views        |
| ------------------------------|---------------------------------|----------------------------------|
|  Role Price| Information |- Active Resource Category Prices<br> - Resource Category Price Associated |
|  Role Price Markup| Information|- Active Role Price Markup<br>- Role Price Markup Associated |
|  Quote Line Detail|- Project Information<br>- Project Quick Create| - Active Quote Line Detail<br>- Combined Quote Line Details<br>- Quote Line Detail Associated |
|  Project Contract Line Detail|- Project Information<br>- Project Quick Create|- Combined Contract Line Details<br>- Active Contract Line Details<br>- Contract Line Detail Associated |
|  Project Task|- Information<br>- New Form| &nbsp; |
|  Project Team Member|- Information<br>- New Form|- Active Project Team Members<br>- Project Team Members<br>- Project Team Members Associated |
|  Time Entry|- Information<br>- Create Time Entry|- My Time Entries By Date<br>- My Time Entries for this Week<br>- Time entries for Approval|
|  Journal Line|- Information<br>- Quick Create|- Active Journal Lines<br>- Journal Line Associated|
|  Invoice Line Detail|- Information<br>- Quick Create|- Active Invoice Line Details<br>- Chargeable Invoice Transactions<br>- Complimentary Invoice Transactions<br>- Invoice Line Detail Associated <br>- Non-Chargeable Invoice Transactions|
|  Actual|- Information<br>- Active Actuals| Actual Associated |

## Set up the Transaction Category field as a pricing dimension

1. Go to **Settings** > **Parameters**. 
2. On the **Parameters** page, on the **Amount-Based Pricing Dimensions** tab, verify that the grid shows the records in the **Pricing Dimensions** entity.
3. Add **Transaction Category** to this list and set the **Applicable to Cost** and **Applicable to Sale** fields to **Yes**.
4. In the **Dimension Type** field, select **Amount-based**, and then select the priority for **Transaction Category** as it relates to cost and sales.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
