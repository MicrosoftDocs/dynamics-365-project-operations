--- 

title: Use a bookable resource as a pricing dimension
description:  This article provides information about how to use a bookable resource as a pricing dimension.
author: poojafandan
ms.author: poojafandan 
ms.date: 06/07/2024  
ms.topic: how-to 
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak

--- 

# Use a bookable resource as a pricing dimension

 _**Applies To:** Project Operations Integrated with ERP, Core deployment - deal to proforma invoicing_ 

This article provides information about how to use a bookable resource as a pricing dimension. If your pricing strategy is set up so that each bookable resource must have a specific price or cost rate, use a bookable resource as a pricing dimension.

## Prerequisites
Before you complete the procedures in this article, you must have a new pricing dimension solution for your organization. If you haven't already created one, see [Create custom fields and entities](../pricing-costing/create-custom-fields-entities-pricing-dimensions.md).

## Add the Bookable Resource field to forms and views
To make the **Bookable Resource** field visible in the pricing dimension solution, you need to add the field to all the forms and views as an entity.

The following table lists all of the out-of-the box forms and views, by entity. You will also need to add the new field to any additional forms or views in your customized entities.

|   Entity        | Forms   |Views        |
| ------------------------------|---------------------------------|----------------------------------|
|  Role Price| Information | - Active Resource Category Prices<br> - Resource Category Price Associated |
|  Role Price Markup| Information| - Active Role Price Markup<br>- Role Price Markup Associated |
|  Quote line detail| - Project Information<br>- Project Quick Create| - Active Quote Line Detail<br>- Combined Quote Line Details<br>- Quote Line Detail Associated |
|  Project Contract line detail| - Project Information<br>- Project Quick Create| - Combined Contract Line Details<br>- Active Contract Line Details<br>- Contract Line Detail Associated |
|  Project Task| - Information<br>- New Form| &nbsp; |
|  Project Team Member| - Information<br>- New Form| - Active Project Team Members<br>- Project Team Members<br>- Project Team members Associated |
|  Time Entry| - Information<br>- Create Time Entry| - My Time Entries By Date<br>- My Time Entries for this Week<br>- Time Entries for Approval|
|  Journal Line| - Information<br>- Quick Create| - Active Journal Lines<br>- Journal Line Associated |
|  Invoice Line Detail| - Information<br>- Quick Create| - Active Invoice Line Details<br>- Chargeable Invoice Transactions<br>- Complimentary Invoice Transactions<br>- Invoice Line Detail Associated <br>- Non-Chargeable Invoice Transactions|
|  Actual| - Information<br>- Active Actuals| Actual Associated |

## Set up a bookable resource as a pricing dimension
To set up a bookable resource as a pricing dimension, follow these steps:

1. Go to **Settings** > **Parameters**. 
2. On the **Parameter** page, on the **Amount-Based Pricing Dimensions** tab, verify that the grid shows the records in the **Pricing Dimensions** entity. 
2. Add **Bookable Resource** to this list of pricing dimensions as **msdyn_bookableresource**. 
3. In **Applicable to cost** and **Applicable to sales**, select a value.
4. In **Dimension Type**, select **Amount-based**. 
5. Select the cost and sales priority for the bookable resource. Typically, a bookable resource has the highest priority when included as a pricing dimension. Set the priority to **1** (or **0** depending on how you count the priority) to ensure this behavior.

## Set up pricing dimension field names

When the field name of a pricing dimension in the **Role Price** table is different from the field name in any of the other entities where the default price is used, the pricing dimension record must be notified of the different names.  

For a bookable resource, the **Project Team Members** entity has a slightly different field name from what it is called on the **Role Price** entity: 

 - **Project Team Members** entity = **msdyn_bookableresourceid**
 - **Role Price** entity = **msdyn_bookableresource**

The pricing dimension record for **msydn_bookableresource** must be notified of this difference.

1. Double-click the row in the **Pricing Dimensions** grid to open the dimension page of **msdyn_bookableresource**.
2. On dimension page, on the **Related** tab, select **Pricing Dimension Field Names**.

  ![Pricing dimension field names tab.](media/PD-fieldname.png)

3. In the associated view that opens, select **Add New Pricing Dimension Field Name**.

  ![Add New Pricing Dimension Field Names.](media/Add-NewPD-fieldname.png)

  This opens the **New Pricing dimension field name** page for **msdyn_bookableresource**. 

4. On the **New Pricing Dimension Field Name** page, add **msdyn_projectteam** to **Entity Locigal Name**.
5. Add  **msdyn_bookableresourceid** to **Field Name**.

 ![New Pricing dimension field name form.](media/PD-fieldname-Added.png)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
