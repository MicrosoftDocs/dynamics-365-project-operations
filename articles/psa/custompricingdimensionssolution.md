---
title: Create custom solutions for pricing dimensions
description: This article explains how to create a custom solution when creating custom pricing dimensions.
author: Rumant
ms.custom: 
  - dyn365-projectservice
  - evergreen
ms.date: 04/09/2024
ms.topic: how-to
ms.author: rumant
audience: Admin
search.audienceType: 
  - admin
  - customizer
  - enduser
ms.reviewer: johnmichalak
---

# Create custom solutions for pricing dimensions

[!include [banner](../includes/psa-now-project-operations.md)]

> [!IMPORTANT]
> All custom pricing dimension changes should be in a separate solution. This important best practice provides flexibility in the future to update or remove changes as needed, will help with re-use of your work, and makes it easier to port these changes to another instance. After you make the required changes, export this solution as a **Managed solution**, and import it into other instances to reuse your pricing setup.

1. Select **Settings** > **Solutions**, and then select **New**. 
2. Name the solution, **\<your organization name> pricing dimensions**, enter the remaining required information, and then select **Save**.

> ![Creating a custom solution for pricing dimensions.](media/Creation-of-custom-pricing-dimension-solution.PNG)
  
## Add all required entities and related components to the Pricing dimension solution
You will need to add the following Project Service entities to your pricing solution. Complete the steps in this procedure to make some important schema changes in the pricing solution so that the entities become aware of the new pricing dimensions.

1. Select **Settings** > **Solutions**, and then double-click **\<your organization name> pricing dimensions**. 
2. In Solution Explorer, on the left navigation pane, select **Add Existing** > **Entities**.
3. In the **Solution Components** dialog box, select the following entities:

- Actual
- Bookable Resource
- Estimate Line
- Project Task
- Invoice Line Detail
- Journal Line
- Project Contract Line Detail
- Project Team Member
- Quote Line Detail
- Role Price Markup
- Role Price 
- Time Entry 

> ![Add existing entities to the pricing dimensions solution.](media/Existing-entities-to-PD-solution.png)

> ![Select solution components.](media/Dimension-Components.png)

> [!NOTE]
> Make sure to include all forms and views for each of the entities selected.

4. When prompted to include any dependent entities for the selected entities, select **No**.

> ![Do not include all related components.](media/Do-not-include-required.png)




[!INCLUDE[footer-include](../includes/footer-banner.md)]
