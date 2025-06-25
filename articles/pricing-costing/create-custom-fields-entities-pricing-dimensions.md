---
title: Create custom fields and entities as pricing dimensions
description: This article provides information about how to create custom option sets or entities.
author: mukumarm
ms.author: mukumarm
ms.date: 05/24/2024
ms.topic: how-to
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak

---

# Create custom fields and entities as pricing dimensions

[!INCLUDE[banner](../includes/banner.md)]

_**Applies To:** Project Operations Integrated with ERP, Core deployment - deal to proforma invoicing_

Complete the following steps when you want to create a custom option set or entity for using it as a pricing dimension. For more information, see [Pricing dimensions overview](pricing-dimensions-overview.md).  

> [!IMPORTANT]
> We recommend that you make all custom pricing dimension changes in a separate solution. This important best practice provides flexibility in the future to update or remove changes as needed. This will also help with re-use of your work and make it easier to port these changes to another instance After you have made all of the required changes, export this solution as a **Managed solution** and import it into other instances to reuse your pricing setup.

  
## Create custom fields and option sets in the pricing dimension solution

A pricing dimension can be an option set or an entity. Both must be created in your pricing solution. The steps in this procedure explain how to create entity-based dimensions and option set-based dimensions.

### Entity-based dimensions
To create entity-based dimensions, follow these steps:

1. Go to **Settings** > **Solutions**, and then double-click **\<your organization name> pricing dimensions**.
2. In Solution Explorer, in the left navigation pane, select **Entities**.
3. Select **New** to create a new entity called **Standard Title**. 
4. Enter the remaining required information, and then select **Save**.

> ![Standard title entity definition.](media/Standard-Title-entity-definition.png)

### Option set-based dimensions 
You can create two option set-based dimensions. 

- Use **Resource Work Location** to track the price of **Home** location work and **Onsite** work. 
- Use **Resource Work hours** with values **Regular** and **Overtime** to apply a markup when the work is complete.

The following graphic provides a view of the **Resource Work Location** dimension. 

> ![Option set based pricing dimension called Resource Work Location.](media/Option-set-PD-called-Resource-Work-Location.png)

The following graphic provides a view of the **Resource Work Hours** dimension. 

> ![Option set based pricing dimension called Resource Work Hours.](media/Option-set-PD-called-Resource-Work-Hours.png)

1. Go to **Settings** > **Solutions**, and double-click  **\<your organization name> pricing dimensions**. 
2. In Solution Explorer, in the left navigation pane, select  **Option Sets**. 
3. Select **New** to create a new option set, enter the remaining required information, and then select **Save**.

## Create data for entity-based dimensions

You can create data for entity-based dimensions manually, or by using Microsoft Excel import or service calls. Use the steps in this procedure to create two standard titles, **Systems Engineer** and **Senior Systems Engineer** from the entity-based dimension, **Standard Title**. If the data that you want to create is small, as in the following example, you can use a standard form.

1. Select **Advanced Find**.
2. Select the entity **Standard Title**, and then select **Results**. All of the rows in the **Standard Title** entity will be shown.
3. Select **New**, and in the **Name** field, enter "Systems Engineer" and then select **Save**.
4. Close the page. 
5. Repeat steps 1-3 to create another standard title for "Senior Systems Engineer".

> ![Sample data for Standard Title entity.](media/ST-data.png)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
