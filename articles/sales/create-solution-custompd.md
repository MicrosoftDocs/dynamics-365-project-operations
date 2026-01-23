--- 
title: Create a solution for custom pricing dimensions 
description:  This article provides information about how to create solutions for custom pricing dimensions.
author: suvaidya
ms.author: nshrivastava 
ms.date: 01/23/2026
ms.topic: how-to 
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak

--- 

# Create a solution for custom pricing dimensions

 _**Applies To:** Project Operations Integrated with ERP, Project Operations Core_

>[!IMPORTANT]
>Add all custom pricing dimension changes to a separate solution. This important best practice gives you the flexibility to update or remove changes as needed, helps you reuse your work, and makes it easier to port changes to other instances. After you make the required changes, export this solution as a **Managed** solution, and then import it into other instances for reuse.

## Create a solution for custom pricing dimensions

1. Select **Settings** > **Solutions**, and then select **New**.
1. Name the solution, _\<your organization name\> pricing dimensions_.
1. Enter the remaining required information, and then select **Save**.

  :::image type="content" source="./media/Creation-of-custom-pricing-dimension-solution.png" alt-text="Screenshot of creation of custom pricing dimension solution.":::

## Add all required entities and related components to the Pricing dimension solution

Add the following Project Service entities to your pricing solution to make important schema changes in the pricing solution. After you complete this procedure, the entities recognize the new pricing dimensions.

1. Select **Settings** > **Solutions**, and then double-click **<_your organization name_> pricing dimensions**.
1. In Solution Explorer, on the left navigation pane, select **Add Existing** > **Entities**.
1. In the **Solution Components** dialog box, select the following entities:

- **Actual**
- **Bookable Resource**
- **Estimate Line**
- **Project Task**
- **Invoice Line Detail**
- **Journal Line**
- **Project Contract Line Detail**
- **Project Team Member**
- **Quote Line Detail**
- **Role Price Markup**
- **Role Price**
- **Time Entry**

   :::image type="content" source="./media/Existing-entities-to-PD-solution.png" alt-text="Screenshot of adding existing entities to custom pricing dimension solution.":::

 1. For each entity, review the components you're adding and the final list of entity assets for each entity.

   > [!NOTE]
   > Include all forms and views for each of the selected entities.

  :::image type="content" source="./media/solution-component-selection.png" alt-text="Screenshot of entities added to the solution.":::

1. When prompted to include any dependent entities for the selected entities, select **No, do not include required components.**

    :::image type="content" source="./media/Do-not-include-required.png" alt-text="Screenshot of including dependent entities dialog.":::

[!INCLUDE[footer-include](../includes/footer-banner.md)]
