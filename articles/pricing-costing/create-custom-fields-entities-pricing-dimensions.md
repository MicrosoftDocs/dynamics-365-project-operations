---
title: Create custom fields and entities as pricing dimensions
description: This article provides information about how to create custom option sets or entities.
author: mukumarm
ms.author: mukumarm
ms.date: 02/27/2026
ms.topic: how-to
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak

---

# Create custom fields and entities as pricing dimensions

[!INCLUDE[banner](../includes/banner.md)]

_**Applies To:** Project Operations Integrated with ERP, Project Operations Core_

Complete the following steps when you want to create a custom option set or entity for using it as a pricing dimension. For more information, see [Pricing dimensions overview](pricing-dimensions-overview.md).  

> [!IMPORTANT]
> Make all custom pricing dimension changes in a separate solution. This important best practice provides flexibility in the future to update or remove changes as needed. This approach also helps with re-use of your work and makes it easier to port these changes to another instance. When you finish making all of the required changes, export this solution as a **Managed solution** and import it into other instances to reuse your pricing setup.

  
## Create custom fields and option sets in the pricing dimension solution

A pricing dimension can be an option set or an entity. Create both types in your pricing solution. The steps in this procedure explain how to create entity-based dimensions and option set-based dimensions.

### Entity-based dimensions
To create entity-based dimensions, follow these steps:

1. Go to **Settings** > **Solutions**, and then double-click **\<your organization name> pricing dimensions**.
1. In Solution Explorer, in the left navigation pane, select **Entities**.
1. Select **New** to create a new entity called **Standard Title**. 
1. Enter the remaining required information, and then select **Save**.

:::image type="content" source="media/Standard-Title-entity-definition.png" alt-text="Screenshot of the Standard Title entity definition.":::

### Option set-based dimensions 
You can create two option set-based dimensions. 

- Use **Resource Work Location** to track the price of **Home** location work and **Onsite** work. 
- Use **Resource Work hours** with values **Regular** and **Overtime** to apply a markup when the work is complete.

The following graphic provides a view of the **Resource Work Location** dimension. 

:::image type="content" source="media/Option-set-PD-called-Resource-Work-Location.png" alt-text="Screenshot of the option set based pricing dimension called Resource Work Location.":::

The following graphic provides a view of the **Resource Work Hours** dimension. 

:::image type="content" source="media/Option-set-PD-called-Resource-Work-Hours.png" alt-text="Screenshot of the option set based pricing dimension called Resource Work Hours.":::

1. Go to **Settings** > **Solutions**, and double-click  **\<your organization name> pricing dimensions**. 
1. In Solution Explorer, in the left navigation pane, select  **Option Sets**. 
1. Select **New** to create a new option set, enter the remaining required information, and then select **Save**.

## Create data for entity-based dimensions

You can create data for entity-based dimensions manually, or by using Microsoft Excel import or service calls. Use the steps in this procedure to create two standard titles, **Systems Engineer** and **Senior Systems Engineer** from the entity-based dimension, **Standard Title**. If the data that you want to create is small, as in the following example, use a standard form.

1. Select **Advanced Find**.
1. Select the entity **Standard Title**, and then select **Results**. All of the rows in the **Standard Title** entity are shown.
1. Select **New**, and in the **Name** field, enter "Systems Engineer" and then select **Save**.
1. Close the page. 
1. Repeat steps 1-3 to create another standard title for "Senior Systems Engineer".

:::image type="content" source="media/ST-data.png" alt-text="Screenshot of sample data for the Standard Title entity.":::


[!INCLUDE[footer-include](../includes/footer-banner.md)]
